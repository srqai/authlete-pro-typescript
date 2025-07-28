# User
(*user*)

## Overview

Operations about user

### Available Operations

* [createUser](#createuser) - Create user
* [createUsersWithListInput](#createuserswithlistinput) - Creates list of users with given input array
* [loginUser](#loginuser) - Logs user into the system
* [logoutUser](#logoutuser) - Logs out current logged in user session
* [getUserByName](#getuserbyname) - Get user by user name
* [updateUser](#updateuser) - Update user
* [deleteUser](#deleteuser) - Delete user

## createUser

This can only be done by the logged in user.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="createUser" method="post" path="/user" -->
```typescript
import { AutheletePro } from "authelete-pro";

const autheletePro = new AutheletePro({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const result = await autheletePro.user.createUser({
    id: 10,
    username: "theUser",
    firstName: "John",
    lastName: "James",
    email: "john@email.com",
    password: "12345",
    phone: "12345",
    userStatus: 1,
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteProCore } from "authelete-pro/core.js";
import { userCreateUser } from "authelete-pro/funcs/userCreateUser.js";

// Use `AutheleteProCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheletePro = new AutheleteProCore({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const res = await userCreateUser(autheletePro, {
    id: 10,
    username: "theUser",
    firstName: "John",
    lastName: "James",
    email: "john@email.com",
    password: "12345",
    phone: "12345",
    userStatus: 1,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("userCreateUser failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [models.User](../../models/user.md)                                                                                                                                            | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.User](../../models/user.md)\>**

### Errors

| Error Type                      | Status Code                     | Content Type                    |
| ------------------------------- | ------------------------------- | ------------------------------- |
| errors.AutheleteProDefaultError | 4XX, 5XX                        | \*/\*                           |

## createUsersWithListInput

Creates list of users with given input array

### Example Usage

<!-- UsageSnippet language="typescript" operationID="createUsersWithListInput" method="post" path="/user/createWithList" -->
```typescript
import { AutheletePro } from "authelete-pro";

const autheletePro = new AutheletePro({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const result = await autheletePro.user.createUsersWithListInput([
    {
      id: 10,
      username: "theUser",
      firstName: "John",
      lastName: "James",
      email: "john@email.com",
      password: "12345",
      phone: "12345",
      userStatus: 1,
    },
  ]);

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteProCore } from "authelete-pro/core.js";
import { userCreateUsersWithListInput } from "authelete-pro/funcs/userCreateUsersWithListInput.js";

// Use `AutheleteProCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheletePro = new AutheleteProCore({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const res = await userCreateUsersWithListInput(autheletePro, [
    {
      id: 10,
      username: "theUser",
      firstName: "John",
      lastName: "James",
      email: "john@email.com",
      password: "12345",
      phone: "12345",
      userStatus: 1,
    },
  ]);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("userCreateUsersWithListInput failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [models.User[]](../../models/.md)                                                                                                                                              | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.User](../../models/user.md)\>**

### Errors

| Error Type                      | Status Code                     | Content Type                    |
| ------------------------------- | ------------------------------- | ------------------------------- |
| errors.AutheleteProDefaultError | 4XX, 5XX                        | \*/\*                           |

## loginUser

Logs user into the system

### Example Usage

<!-- UsageSnippet language="typescript" operationID="loginUser" method="get" path="/user/login" -->
```typescript
import { AutheletePro } from "authelete-pro";

const autheletePro = new AutheletePro({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const result = await autheletePro.user.loginUser();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteProCore } from "authelete-pro/core.js";
import { userLoginUser } from "authelete-pro/funcs/userLoginUser.js";

// Use `AutheleteProCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheletePro = new AutheleteProCore({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const res = await userLoginUser(autheletePro);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("userLoginUser failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.LoginUserRequest](../../models/operations/loginuserrequest.md)                                                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.LoginUserResponse](../../models/operations/loginuserresponse.md)\>**

### Errors

| Error Type                      | Status Code                     | Content Type                    |
| ------------------------------- | ------------------------------- | ------------------------------- |
| errors.ApiErrorInvalidInput     | 400                             | application/json                |
| errors.ApiErrorUnauthorized     | 401                             | application/json                |
| errors.ApiErrorNotFound         | 404                             | application/json                |
| errors.AutheleteProDefaultError | 4XX, 5XX                        | \*/\*                           |

## logoutUser

Logs out current logged in user session

### Example Usage

<!-- UsageSnippet language="typescript" operationID="logoutUser" method="get" path="/user/logout" -->
```typescript
import { AutheletePro } from "authelete-pro";

const autheletePro = new AutheletePro({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  await autheletePro.user.logoutUser();


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteProCore } from "authelete-pro/core.js";
import { userLogoutUser } from "authelete-pro/funcs/userLogoutUser.js";

// Use `AutheleteProCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheletePro = new AutheleteProCore({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const res = await userLogoutUser(autheletePro);
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("userLogoutUser failed:", res.error);
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

**Promise\<void\>**

### Errors

| Error Type                      | Status Code                     | Content Type                    |
| ------------------------------- | ------------------------------- | ------------------------------- |
| errors.AutheleteProDefaultError | 4XX, 5XX                        | \*/\*                           |

## getUserByName

Get user by user name

### Example Usage

<!-- UsageSnippet language="typescript" operationID="getUserByName" method="get" path="/user/{username}" -->
```typescript
import { AutheletePro } from "authelete-pro";

const autheletePro = new AutheletePro({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const result = await autheletePro.user.getUserByName({
    username: "Edyth10",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteProCore } from "authelete-pro/core.js";
import { userGetUserByName } from "authelete-pro/funcs/userGetUserByName.js";

// Use `AutheleteProCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheletePro = new AutheleteProCore({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const res = await userGetUserByName(autheletePro, {
    username: "Edyth10",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("userGetUserByName failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetUserByNameRequest](../../models/operations/getuserbynamerequest.md)                                                                                             | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.User](../../models/user.md)\>**

### Errors

| Error Type                      | Status Code                     | Content Type                    |
| ------------------------------- | ------------------------------- | ------------------------------- |
| errors.ApiErrorInvalidInput     | 400                             | application/json                |
| errors.ApiErrorUnauthorized     | 401                             | application/json                |
| errors.ApiErrorNotFound         | 404                             | application/json                |
| errors.AutheleteProDefaultError | 4XX, 5XX                        | \*/\*                           |

## updateUser

This can only be done by the logged in user.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="updateUser" method="put" path="/user/{username}" -->
```typescript
import { AutheletePro } from "authelete-pro";

const autheletePro = new AutheletePro({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  await autheletePro.user.updateUser({
    username: "Alison.Cassin",
    user: {
      id: 10,
      username: "theUser",
      firstName: "John",
      lastName: "James",
      email: "john@email.com",
      password: "12345",
      phone: "12345",
      userStatus: 1,
    },
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteProCore } from "authelete-pro/core.js";
import { userUpdateUser } from "authelete-pro/funcs/userUpdateUser.js";

// Use `AutheleteProCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheletePro = new AutheleteProCore({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const res = await userUpdateUser(autheletePro, {
    username: "Alison.Cassin",
    user: {
      id: 10,
      username: "theUser",
      firstName: "John",
      lastName: "James",
      email: "john@email.com",
      password: "12345",
      phone: "12345",
      userStatus: 1,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("userUpdateUser failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.UpdateUserRequest](../../models/operations/updateuserrequest.md)                                                                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<void\>**

### Errors

| Error Type                      | Status Code                     | Content Type                    |
| ------------------------------- | ------------------------------- | ------------------------------- |
| errors.AutheleteProDefaultError | 4XX, 5XX                        | \*/\*                           |

## deleteUser

This can only be done by the logged in user.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="deleteUser" method="delete" path="/user/{username}" -->
```typescript
import { AutheletePro } from "authelete-pro";

const autheletePro = new AutheletePro({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const result = await autheletePro.user.deleteUser({
    username: "Rita_Schuppe",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteProCore } from "authelete-pro/core.js";
import { userDeleteUser } from "authelete-pro/funcs/userDeleteUser.js";

// Use `AutheleteProCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheletePro = new AutheleteProCore({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const res = await userDeleteUser(autheletePro, {
    username: "Rita_Schuppe",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("userDeleteUser failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.DeleteUserRequest](../../models/operations/deleteuserrequest.md)                                                                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.User](../../models/user.md)\>**

### Errors

| Error Type                      | Status Code                     | Content Type                    |
| ------------------------------- | ------------------------------- | ------------------------------- |
| errors.ApiErrorInvalidInput     | 400                             | application/json                |
| errors.ApiErrorUnauthorized     | 401                             | application/json                |
| errors.ApiErrorNotFound         | 404                             | application/json                |
| errors.AutheleteProDefaultError | 4XX, 5XX                        | \*/\*                           |