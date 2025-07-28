# Pet
(*pet*)

## Overview

Everything about your Pets

Find out more
<http://swagger.io>

### Available Operations

* [updatePet](#updatepet) - Update an existing pet
* [addPet](#addpet) - Add a new pet to the store
* [findPetsByStatus](#findpetsbystatus) - Finds Pets by status
* [findPetsByTags](#findpetsbytags) - Finds Pets by tags
* [getPetById](#getpetbyid) - Find pet by ID
* [deletePet](#deletepet) - Deletes a pet
* [uploadFile](#uploadfile) - uploads an image

## updatePet

Update an existing pet by Id

### Example Usage

<!-- UsageSnippet language="typescript" operationID="updatePet" method="put" path="/pet" -->
```typescript
import { AutheletePro } from "authelete-pro";

const autheletePro = new AutheletePro({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const result = await autheletePro.pet.updatePet({
    id: 10,
    name: "doggie",
    category: {
      id: 1,
      name: "Dogs",
    },
    photoUrls: [
      "<value 1>",
    ],
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteProCore } from "authelete-pro/core.js";
import { petUpdatePet } from "authelete-pro/funcs/petUpdatePet.js";

// Use `AutheleteProCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheletePro = new AutheleteProCore({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const res = await petUpdatePet(autheletePro, {
    id: 10,
    name: "doggie",
    category: {
      id: 1,
      name: "Dogs",
    },
    photoUrls: [
      "<value 1>",
    ],
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("petUpdatePet failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [models.Pet](../../models/pet.md)                                                                                                                                              | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.Pet](../../models/pet.md)\>**

### Errors

| Error Type                      | Status Code                     | Content Type                    |
| ------------------------------- | ------------------------------- | ------------------------------- |
| errors.ApiErrorInvalidInput     | 400                             | application/json                |
| errors.ApiErrorUnauthorized     | 401                             | application/json                |
| errors.ApiErrorNotFound         | 404                             | application/json                |
| errors.AutheleteProDefaultError | 4XX, 5XX                        | \*/\*                           |

## addPet

Add a new pet to the store

### Example Usage

<!-- UsageSnippet language="typescript" operationID="addPet" method="post" path="/pet" -->
```typescript
import { AutheletePro } from "authelete-pro";

const autheletePro = new AutheletePro({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const result = await autheletePro.pet.addPet({
    id: 10,
    name: "doggie",
    category: {
      id: 1,
      name: "Dogs",
    },
    photoUrls: [
      "<value 1>",
      "<value 2>",
      "<value 3>",
    ],
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteProCore } from "authelete-pro/core.js";
import { petAddPet } from "authelete-pro/funcs/petAddPet.js";

// Use `AutheleteProCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheletePro = new AutheleteProCore({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const res = await petAddPet(autheletePro, {
    id: 10,
    name: "doggie",
    category: {
      id: 1,
      name: "Dogs",
    },
    photoUrls: [
      "<value 1>",
      "<value 2>",
      "<value 3>",
    ],
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("petAddPet failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [models.Pet](../../models/pet.md)                                                                                                                                              | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.Pet](../../models/pet.md)\>**

### Errors

| Error Type                      | Status Code                     | Content Type                    |
| ------------------------------- | ------------------------------- | ------------------------------- |
| errors.AutheleteProDefaultError | 4XX, 5XX                        | \*/\*                           |

## findPetsByStatus

Multiple status values can be provided with comma separated strings

### Example Usage

<!-- UsageSnippet language="typescript" operationID="findPetsByStatus" method="get" path="/pet/findByStatus" -->
```typescript
import { AutheletePro } from "authelete-pro";

const autheletePro = new AutheletePro({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const result = await autheletePro.pet.findPetsByStatus({});

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteProCore } from "authelete-pro/core.js";
import { petFindPetsByStatus } from "authelete-pro/funcs/petFindPetsByStatus.js";

// Use `AutheleteProCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheletePro = new AutheleteProCore({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const res = await petFindPetsByStatus(autheletePro, {});
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("petFindPetsByStatus failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.FindPetsByStatusRequest](../../models/operations/findpetsbystatusrequest.md)                                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.Pet[]](../../models/.md)\>**

### Errors

| Error Type                      | Status Code                     | Content Type                    |
| ------------------------------- | ------------------------------- | ------------------------------- |
| errors.ApiErrorInvalidInput     | 400                             | application/json                |
| errors.ApiErrorUnauthorized     | 401                             | application/json                |
| errors.ApiErrorNotFound         | 404                             | application/json                |
| errors.AutheleteProDefaultError | 4XX, 5XX                        | \*/\*                           |

## findPetsByTags

Multiple tags can be provided with comma separated strings. Use tag1, tag2, tag3 for testing.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="findPetsByTags" method="get" path="/pet/findByTags" -->
```typescript
import { AutheletePro } from "authelete-pro";

const autheletePro = new AutheletePro({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const result = await autheletePro.pet.findPetsByTags();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteProCore } from "authelete-pro/core.js";
import { petFindPetsByTags } from "authelete-pro/funcs/petFindPetsByTags.js";

// Use `AutheleteProCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheletePro = new AutheleteProCore({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const res = await petFindPetsByTags(autheletePro);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("petFindPetsByTags failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.FindPetsByTagsRequest](../../models/operations/findpetsbytagsrequest.md)                                                                                           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.Pet[]](../../models/.md)\>**

### Errors

| Error Type                      | Status Code                     | Content Type                    |
| ------------------------------- | ------------------------------- | ------------------------------- |
| errors.ApiErrorInvalidInput     | 400                             | application/json                |
| errors.ApiErrorUnauthorized     | 401                             | application/json                |
| errors.ApiErrorNotFound         | 404                             | application/json                |
| errors.AutheleteProDefaultError | 4XX, 5XX                        | \*/\*                           |

## getPetById

Returns a single pet

### Example Usage

<!-- UsageSnippet language="typescript" operationID="getPetById" method="get" path="/pet/{petId}" -->
```typescript
import { AutheletePro } from "authelete-pro";

const autheletePro = new AutheletePro({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const result = await autheletePro.pet.getPetById({
    petId: 311674,
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteProCore } from "authelete-pro/core.js";
import { petGetPetById } from "authelete-pro/funcs/petGetPetById.js";

// Use `AutheleteProCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheletePro = new AutheleteProCore({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const res = await petGetPetById(autheletePro, {
    petId: 311674,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("petGetPetById failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetPetByIdRequest](../../models/operations/getpetbyidrequest.md)                                                                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.Pet](../../models/pet.md)\>**

### Errors

| Error Type                      | Status Code                     | Content Type                    |
| ------------------------------- | ------------------------------- | ------------------------------- |
| errors.ApiErrorInvalidInput     | 400                             | application/json                |
| errors.ApiErrorUnauthorized     | 401                             | application/json                |
| errors.ApiErrorNotFound         | 404                             | application/json                |
| errors.AutheleteProDefaultError | 4XX, 5XX                        | \*/\*                           |

## deletePet

Deletes a pet

### Example Usage

<!-- UsageSnippet language="typescript" operationID="deletePet" method="delete" path="/pet/{petId}" -->
```typescript
import { AutheletePro } from "authelete-pro";

const autheletePro = new AutheletePro({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const result = await autheletePro.pet.deletePet({
    petId: 818965,
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteProCore } from "authelete-pro/core.js";
import { petDeletePet } from "authelete-pro/funcs/petDeletePet.js";

// Use `AutheleteProCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheletePro = new AutheleteProCore({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const res = await petDeletePet(autheletePro, {
    petId: 818965,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("petDeletePet failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.DeletePetRequest](../../models/operations/deletepetrequest.md)                                                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.Pet](../../models/pet.md)\>**

### Errors

| Error Type                      | Status Code                     | Content Type                    |
| ------------------------------- | ------------------------------- | ------------------------------- |
| errors.ApiErrorInvalidInput     | 400                             | application/json                |
| errors.ApiErrorUnauthorized     | 401                             | application/json                |
| errors.ApiErrorNotFound         | 404                             | application/json                |
| errors.AutheleteProDefaultError | 4XX, 5XX                        | \*/\*                           |

## uploadFile

uploads an image

### Example Usage

<!-- UsageSnippet language="typescript" operationID="uploadFile" method="post" path="/pet/{petId}/uploadImage" -->
```typescript
import { AutheletePro } from "authelete-pro";

const autheletePro = new AutheletePro({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const result = await autheletePro.pet.uploadFile({
    petId: 150516,
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteProCore } from "authelete-pro/core.js";
import { petUploadFile } from "authelete-pro/funcs/petUploadFile.js";

// Use `AutheleteProCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheletePro = new AutheleteProCore({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const res = await petUploadFile(autheletePro, {
    petId: 150516,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("petUploadFile failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.UploadFileRequest](../../models/operations/uploadfilerequest.md)                                                                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ApiResponse](../../models/apiresponse.md)\>**

### Errors

| Error Type                      | Status Code                     | Content Type                    |
| ------------------------------- | ------------------------------- | ------------------------------- |
| errors.AutheleteProDefaultError | 4XX, 5XX                        | \*/\*                           |