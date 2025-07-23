# API Endpoints

OOGY API Integration Using Postman

The OOGY service comprises seven distinct APIs. Below is a detailed explanation of each API, demonstrated using Postman for clarity and ease of understanding.

## 1. Login API

The **Login API** is used to authenticate users by verifying their credentials. Upon successful authentication, it returns a session token (`session_key`) which is required for subsequent API calls.

- **Method**: `POST`  
- **Endpoint**: `(API URL)/login`

### Headers

| Key           | Value              |
|---------------|--------------------|
| Content-Type  | application/json   |

### Body Configuration

In the **Body** tab:

1. Select **raw**.
2. Set the format to **JSON (application/json)**.

### JSON Payload Parameters

Provide the following fields in the request body:

| Field       | Description                                                           |
|-------------|-----------------------------------------------------------------------|
| `serverid`  | The MOCA server ID used to determine the connection URL and credentials. |
| `username`  | MOCA server connection username.                                       |
| `password`  | MOCA server connection password.                                       |

### Response

Upon a successful request, a JSON response will be returned with the following structure:

| Field              | Description                                                                  |
|--------------------|------------------------------------------------------------------------------|
| `MocaStatusCode`   | Returns `0` if the login is successful.                                      |
| `ErrorMessage`     | Returns an error message if the login fails.                                 |
| `StatusDescription`| Service message (e.g., `"User logged in successfully"`), otherwise empty.    |
| `session_key`      | A session token used in subsequent API requests (e.g., execute, logout).     |
| `Results`          | Will be `null` in the login response.                                        |



## 2. Execute API

The **Execute API** is used to run queries or commands and returns the output in JSON format.

- **Method**: `POST`  
- **Endpoint**: `(API URL)/execute`

### Headers

| Key           | Value              |
|---------------|--------------------|
| Content-Type  | application/json   |

### Body Configuration

In the **Body** tab:

- Select **raw**.
- Set the format to **JSON (application/json)**.

#### JSON Payload Parameters

| Field        | Description                                                                 |
|--------------|-----------------------------------------------------------------------------|
| `command`    | The command or query to be executed.                                        |
| `serverid`   | The command or MOCA server ID to determine the connection URL and credentials. |
| `username`   | *(Optional)* Username for MOCA server authentication.                       |
| `password`   | *(Optional)* Password for MOCA server authentication.                       |
| `session_key`| *(Optional)* Session key returned from the Login API.                       |

You may provide either:

- `username` and `password`,  
- `session_key`,  
- or all credentials together, depending on the authentication method.

### Response

When the request is successfully sent, a JSON response will be returned with the following structure:

| Field             | Description                                                                 |
|------------------|-----------------------------------------------------------------------------|
| `MocaStatusCode`  | Returns `0` if the execution is successful.                                 |
| `ErrorMessage`    | Contains error details if the execution fails.                              |
| `StatusDescription` | Message from the service (e.g., `User logged in successfully`).           |
| `session_key`     | A session key for use in subsequent API calls such as command execution or logout. |
| `Results`         | Contains the data returned from the executed query.                         |



## 3. Logout API

The **Logout API** is used to terminate an active session. It requires a valid session key that was obtained from the Login API, which authenticates user credentials and returns the token required for subsequent requests.

- **Method**: `POST`  
- **Endpoint**: `(API URL)/logout`

### Required Query Parameters

Pass the following parameters in the query string:

| Parameter     | Description                                           |
|---------------|-------------------------------------------------------|
| `username`    | MOCA server connection username.                      |
| `session_key` | Session key returned by the Login API.               |
| `serverid`    | MOCA server identifier used to determine the connection URL. |



## 4. Hello World API

The **Hello World API** is typically used to verify connectivity and authentication with the MOCA server. It requires valid credentials and returns a basic response indicating successful communication.

- **Method**: `POST`  
- **Endpoint**: `(API URL)/helloworld`

### Headers

| Key           | Value              |
|---------------|--------------------|
| Content-Type  | application/json   |

### Body Configuration

In the **Body** tab:

1. Select **raw**.  
2. Set the format to **JSON (application/json)**.

### JSON Payload Parameters

Provide a JSON object in the request body with the following fields:

| Field         | Description                                                                 |
|----------------|-----------------------------------------------------------------------------|
| `serverid`     | The MOCA server ID used to determine the connection URL and credentials.   |
| `username`     | *(Optional)* Username for MOCA server authentication.                      |
| `password`     | *(Optional)* Password for MOCA server authentication.                      |
| `session_key`  | *(Optional)* Session key obtained from the Login API.                      |

You can authenticate using either:

- `username` and `password`,  
- `session_key`,  
- or all credentials together.



## 5. API Router

The **API Router** is a generic proxy service designed to forward and execute requests to any given URL, including MOCA APIs. It enables secure communication with external systems and serves as a workaround for environments with outdated TLS support.

### Use Cases

- **TLS Compatibility**: When Java 6 is installed on the RP server (which does not support TLS 1.1 or higher), the API Router can be used as an intermediary. Since it supports TLS 1.0 and above, it can forward requests on behalf of the RP server using the required TLS version.
- **Centralized Routing**: Consolidate logic by implementing a single method in the RP layer to route all third-party API calls through the API Router, improving maintainability and consistency.

### Request Details

- **Method**: `POST`  
- **Endpoint**: `(API URL)/apirouter`

### Body Configuration

In the **Body** tab:

1. Select **raw**.
2. Set the format to **JSON (application/json)**.

### JSON Payload Parameters

| Field              | Description                                                                 |
|--------------------|-----------------------------------------------------------------------------|
| `URL`              | The target URL of the external API to be called.                            |
| `httpmethod`       | The HTTP method to be used for the request (e.g., GET, POST, PUT).          |
| `queryparameters[]`| An array of key-value pairs representing query string parameters.           |
| `headerparameters[]`| An array of key-value pairs for the request headers.                       |
| `Body`             | The request payload to be sent to the target URL.                           |



## 6. Post Download API

The **Post Download API** is used to send data to the server and initiate a download process. It requires valid credentials for authentication and returns a structured JSON response.

- **Method**: `POST`  
- **Endpoint**: `(API URL)/postdownload`

### Query Parameters

Pass the following parameters in the query string:

| Parameter     | Description                                           |
|---------------|-------------------------------------------------------|
| `username`    | *(Optional)* MOCA server connection username.         |
| `session_key` | *(Optional)* Session key returned from the Login API. |
| `serverid`    | MOCA server ID to determine connection URL and credentials. |

You may authenticate using:
- `username` and `password`,
- `session_key`, or
- all credentials together.

### Headers

| Key           | Value              |
|---------------|--------------------|
| Content-Type  | application/json   |

### Body Configuration

In the **Body** tab:

1. Select **raw**.
2. Set the format to **JSON (application/json)**.

### JSON Payload Parameters

| Field           | Description                                                                 |
|------------------|-----------------------------------------------------------------------------|
| `serverid`       | MOCA server ID used to determine the connection URL.                        |
| `username`       | *(Optional)* MOCA server connection username.                               |
| `password`       | *(Optional)* MOCA server connection password.                               |
| `session_key`    | *(Optional)* Session key from the Login API.                                |
| `data`           | The data to be submitted.                                                   |
| `dwnld_info`     | Metadata or configuration related to the download.                          |
| `run_tran_flg`   | A flag indicating whether the transaction should be executed.               |

### Response

Upon successful request, a JSON response will be returned with the following fields:

| Field              | Description                                                                  |
|--------------------|------------------------------------------------------------------------------|
| `MocaStatusCode`   | Returns `0` if the operation is successful.                                  |
| `ErrorMessage`     | Returns an error message if the request fails.                               |
| `StatusDescription`| Message from the service (e.g., "User logged in successfully").              |
| `session_key`      | Session key to be used in subsequent requests (e.g., execute or logout).     |
| `Results`          | Contains the results or data returned from the operation.                    |



## 7. Post Download XML API

The **Post Download XML API** is used to send XML-formatted data to the server for processing and initiating a download transaction. It requires valid authentication credentials and returns a structured response.

- **Method**: `POST`  
- **Endpoint**: `(API URL)/postdownloadxml`

### Query Parameters

Pass the following parameters in the query string:

| Parameter     | Description                                           |
|---------------|-------------------------------------------------------|
| `username`    | *(Optional)* MOCA server connection username.         |
| `session_key` | *(Optional)* Session key returned from the Login API. |
| `serverid`    | MOCA server ID to determine the connection URL and credentials. |

Authentication can be provided using:
- `username` and `password`,
- `session_key`, or
- all credentials together.

### Headers

| Key           | Value              |
|---------------|--------------------|
| Content-Type  | application/xml    |

### Body Configuration

In the **Body** tab:

1. Select **raw**.
2. Set the format to **XML (application/xml)**.

### XML Payload Structure

The body of the request must contain a well-formed XML structure with the following fields:

| Field           | Description                                                                 |
|------------------|-----------------------------------------------------------------------------|
| `serverid`       | MOCA server ID used to determine the connection URL and credentials.        |
| `username`       | *(Optional)* MOCA server connection username.                               |
| `password`       | *(Optional)* MOCA server connection password.                               |
| `session_key`    | *(Optional)* Session key obtained from the Login API.                       |
| `data`           | XML data content to be submitted.                                           |
| `dwnld_info`     | Information related to the download process.                                |
| `run_tran_flg`   | Flag indicating whether to execute the transaction.                         |

> **Note**: The full XML payload must be included in the body of the request.

