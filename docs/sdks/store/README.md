# Store
(*store*)

## Overview

Access to Petstore orders

Find out more about our store
<http://swagger.io>

### Available Operations

* [getInventory](#getinventory) - Returns pet inventories by status
* [placeOrder](#placeorder) - Place an order for a pet
* [getOrderById](#getorderbyid) - Find purchase order by ID
* [deleteOrder](#deleteorder) - Delete purchase order by ID

## getInventory

Returns a map of status codes to quantities

### Example Usage

<!-- UsageSnippet language="typescript" operationID="getInventory" method="get" path="/store/inventory" -->
```typescript
import { AutheletePro } from "authelete-pro";

const autheletePro = new AutheletePro({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const result = await autheletePro.store.getInventory();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteProCore } from "authelete-pro/core.js";
import { storeGetInventory } from "authelete-pro/funcs/storeGetInventory.js";

// Use `AutheleteProCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheletePro = new AutheleteProCore({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const res = await storeGetInventory(autheletePro);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("storeGetInventory failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[{ [k: string]: number }](../../models/.md)\>**

### Errors

| Error Type                      | Status Code                     | Content Type                    |
| ------------------------------- | ------------------------------- | ------------------------------- |
| errors.ApiErrorUnauthorized     | 401                             | application/json                |
| errors.ApiErrorNotFound         | 404                             | application/json                |
| errors.AutheleteProDefaultError | 4XX, 5XX                        | \*/\*                           |

## placeOrder

Place a new order in the store

### Example Usage

<!-- UsageSnippet language="typescript" operationID="placeOrder" method="post" path="/store/order" -->
```typescript
import { AutheletePro } from "authelete-pro";

const autheletePro = new AutheletePro({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const result = await autheletePro.store.placeOrder({
    id: 10,
    petId: 198772,
    quantity: 7,
    status: "approved",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteProCore } from "authelete-pro/core.js";
import { storePlaceOrder } from "authelete-pro/funcs/storePlaceOrder.js";

// Use `AutheleteProCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheletePro = new AutheleteProCore({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const res = await storePlaceOrder(autheletePro, {
    id: 10,
    petId: 198772,
    quantity: 7,
    status: "approved",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("storePlaceOrder failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [models.Order](../../models/order.md)                                                                                                                                          | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.Order](../../models/order.md)\>**

### Errors

| Error Type                      | Status Code                     | Content Type                    |
| ------------------------------- | ------------------------------- | ------------------------------- |
| errors.ApiErrorUnauthorized     | 401                             | application/json                |
| errors.ApiErrorNotFound         | 404                             | application/json                |
| errors.AutheleteProDefaultError | 4XX, 5XX                        | \*/\*                           |

## getOrderById

For valid response try integer IDs with value <= 5 or > 10. Other values will generate exceptions.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="getOrderById" method="get" path="/store/order/{orderId}" -->
```typescript
import { AutheletePro } from "authelete-pro";

const autheletePro = new AutheletePro({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const result = await autheletePro.store.getOrderById({
    orderId: 728529,
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteProCore } from "authelete-pro/core.js";
import { storeGetOrderById } from "authelete-pro/funcs/storeGetOrderById.js";

// Use `AutheleteProCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheletePro = new AutheleteProCore({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const res = await storeGetOrderById(autheletePro, {
    orderId: 728529,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("storeGetOrderById failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetOrderByIdRequest](../../models/operations/getorderbyidrequest.md)                                                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.Order](../../models/order.md)\>**

### Errors

| Error Type                      | Status Code                     | Content Type                    |
| ------------------------------- | ------------------------------- | ------------------------------- |
| errors.ApiErrorInvalidInput     | 400                             | application/json                |
| errors.ApiErrorUnauthorized     | 401                             | application/json                |
| errors.ApiErrorNotFound         | 404                             | application/json                |
| errors.AutheleteProDefaultError | 4XX, 5XX                        | \*/\*                           |

## deleteOrder

For valid response try integer IDs with value < 1000. Anything above 1000 or nonintegers will generate API errors

### Example Usage

<!-- UsageSnippet language="typescript" operationID="deleteOrder" method="delete" path="/store/order/{orderId}" -->
```typescript
import { AutheletePro } from "authelete-pro";

const autheletePro = new AutheletePro({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const result = await autheletePro.store.deleteOrder({
    orderId: 690575,
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteProCore } from "authelete-pro/core.js";
import { storeDeleteOrder } from "authelete-pro/funcs/storeDeleteOrder.js";

// Use `AutheleteProCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheletePro = new AutheleteProCore({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const res = await storeDeleteOrder(autheletePro, {
    orderId: 690575,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("storeDeleteOrder failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.DeleteOrderRequest](../../models/operations/deleteorderrequest.md)                                                                                                 | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.Order](../../models/order.md)\>**

### Errors

| Error Type                      | Status Code                     | Content Type                    |
| ------------------------------- | ------------------------------- | ------------------------------- |
| errors.ApiErrorInvalidInput     | 400                             | application/json                |
| errors.ApiErrorUnauthorized     | 401                             | application/json                |
| errors.ApiErrorNotFound         | 404                             | application/json                |
| errors.AutheleteProDefaultError | 4XX, 5XX                        | \*/\*                           |