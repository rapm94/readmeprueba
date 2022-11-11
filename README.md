# OpenAPI Petstore
This is a sample server Petstore server. For this sample, you can use the api key `special-key` to test the authorization filters.

## Version: 1.0.0

**License:** [Apache-2.0](https://www.apache.org/licenses/LICENSE-2.0.html)

[Find out more about Swagger](http://swagger.io)
### /pet

#### POST
##### Summary:

Add a new pet to the store

##### Description:



##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 405 | Invalid input |

##### Security

| Security Schema | Scopes | |
| --- | --- | --- |
| petstore_auth | write:pets | read:pets |

#### PUT
##### Summary:

Update an existing pet

##### Description:



##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid ID supplied |
| 404 | Pet not found |
| 405 | Validation exception |

##### Security

| Security Schema | Scopes | |
| --- | --- | --- |
| petstore_auth | write:pets | read:pets |

### /pet/findByStatus

#### GET
##### Summary:

Finds Pets by status

##### Description:

Multiple status values can be provided with comma separated strings

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| status | query | Status values that need to be considered for filter | Yes | [ string ] |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid status value |

##### Security

| Security Schema | Scopes |
| --- | --- |
| petstore_auth | read:pets |

### /pet/findByTags

#### GET
##### Summary:

Finds Pets by tags

##### Description:

Multiple tags can be provided with comma separated strings. Use tag1, tag2, tag3 for testing.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| tags | query | Tags to filter by | Yes | [ string ] |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid tag value |

##### Security

| Security Schema | Scopes |
| --- | --- |
| petstore_auth | read:pets |

### /pet/{petId}

#### GET
##### Summary:

Find pet by ID

##### Description:

Returns a single pet

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| petId | path | ID of pet to return | Yes | long |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid ID supplied |
| 404 | Pet not found |

##### Security

| Security Schema | Scopes |
| --- | --- |
| api_key | |

#### POST
##### Summary:

Updates a pet in the store with form data

##### Description:



##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| petId | path | ID of pet that needs to be updated | Yes | long |

##### Responses

| Code | Description |
| ---- | ----------- |
| 405 | Invalid input |

##### Security

| Security Schema | Scopes | |
| --- | --- | --- |
| petstore_auth | write:pets | read:pets |

#### DELETE
##### Summary:

Deletes a pet

##### Description:



##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| api_key | header |  | No | string |
| petId | path | Pet id to delete | Yes | long |

##### Responses

| Code | Description |
| ---- | ----------- |
| 400 | Invalid pet value |

##### Security

| Security Schema | Scopes | |
| --- | --- | --- |
| petstore_auth | write:pets | read:pets |

### /pet/{petId}/uploadImage

#### POST
##### Summary:

uploads an image

##### Description:



##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| petId | path | ID of pet to update | Yes | long |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |

##### Security

| Security Schema | Scopes | |
| --- | --- | --- |
| petstore_auth | write:pets | read:pets |

### /store/inventory

#### GET
##### Summary:

Returns pet inventories by status

##### Description:

Returns a map of status codes to quantities

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |

##### Security

| Security Schema | Scopes |
| --- | --- |
| api_key | |

### /store/order

#### POST
##### Summary:

Place an order for a pet

##### Description:



##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid Order |

### /store/order/{orderId}

#### GET
##### Summary:

Find purchase order by ID

##### Description:

For valid response try integer IDs with value <= 5 or > 10. Other values will generated exceptions

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| orderId | path | ID of pet that needs to be fetched | Yes | long |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid ID supplied |
| 404 | Order not found |

#### DELETE
##### Summary:

Delete purchase order by ID

##### Description:

For valid response try integer IDs with value < 1000. Anything above 1000 or nonintegers will generate API errors

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| orderId | path | ID of the order that needs to be deleted | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 400 | Invalid ID supplied |
| 404 | Order not found |

### /user

#### POST
##### Summary:

Create user

##### Description:

This can only be done by the logged in user.

##### Responses

| Code | Description |
| ---- | ----------- |
| default | successful operation |

##### Security

| Security Schema | Scopes |
| --- | --- |
| api_key | |

### /user/createWithArray

#### POST
##### Summary:

Creates list of users with given input array

##### Description:



##### Responses

| Code | Description |
| ---- | ----------- |
| default | successful operation |

##### Security

| Security Schema | Scopes |
| --- | --- |
| api_key | |

### /user/createWithList

#### POST
##### Summary:

Creates list of users with given input array

##### Description:



##### Responses

| Code | Description |
| ---- | ----------- |
| default | successful operation |

##### Security

| Security Schema | Scopes |
| --- | --- |
| api_key | |

### /user/login

#### GET
##### Summary:

Logs user into the system

##### Description:



##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| username | query | The user name for login | Yes | string |
| password | query | The password for login in clear text | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid username/password supplied |

### /user/logout

#### GET
##### Summary:

Logs out current logged in user session

##### Description:



##### Responses

| Code | Description |
| ---- | ----------- |
| default | successful operation |

##### Security

| Security Schema | Scopes |
| --- | --- |
| api_key | |

### /user/{username}

#### GET
##### Summary:

Get user by user name

##### Description:



##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| username | path | The name that needs to be fetched. Use user1 for testing. | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid username supplied |
| 404 | User not found |

#### PUT
##### Summary:

Updated user

##### Description:

This can only be done by the logged in user.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| username | path | name that need to be deleted | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 400 | Invalid user supplied |
| 404 | User not found |

##### Security

| Security Schema | Scopes |
| --- | --- |
| api_key | |

#### DELETE
##### Summary:

Delete user

##### Description:

This can only be done by the logged in user.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| username | path | The name that needs to be deleted | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 400 | Invalid username supplied |
| 404 | User not found |

##### Security

| Security Schema | Scopes |
| --- | --- |
| api_key | |
