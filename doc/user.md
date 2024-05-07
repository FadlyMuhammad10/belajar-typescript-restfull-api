# User API Spec

## Register User

Endpoint : POST /api/users

Request Body :

```json
{
  "username": "aizen",
  "password": "rahasia",
  "name": "Aizen Sosuke"
}
```

Response (Success)

```json
{
  "data": {
    "username": "aizen",
    "name": "Aizen Sosuke"
  }
}
```

Response Body (Failed) :

```json
{
  "errors": "Username must not blank, ..."
}
```

## Login User

Endpoint : POST /api/users/login

Request Body :

```json
{
  "username": "aizen",
  "password": "rahasia"
}
```

Response (Success)

```json
{
  "data": {
    "username": "aizen",
    "name": "Aizen Sosuke",
    "token": "uuid"
  }
}
```

Response Body (Failed) :

```json
{
  "errors": "Username or password wrong, ..."
}
```

## Get User

Endpoint : GET /api/users/current

Request Header :

- X-API-TOKEN : token

Response Body (Success)

```json
{
  "data": {
    "username": "aizen",
    "name": "Aizen Sosuke"
  }
}
```

Response Body (Failed) :

```json
{
  "errors": "Unauthorized, ..."
}
```

## Update User

Endpoint : PUT /api/users/current

Request Header :

- X-API-TOKEN : token

Request Body :

```json
{
  "password": "rahasia", // tidak wajib
  "name": "Aizen Sosuke" // tidak wajib
}
```

Response Body (Success)

```json
{
  "data": {
    "username": "aizen",
    "name": "Aizen Sosuke"
  }
}
```

Response Body (Failed) :

```json
{
  "errors": "Unauthorized, ..."
}
```

## Logout User

Endpoint : DELETE /api/users/current

Request Header :

- X-API-TOKEN : token

Response Body (Success)

```json
{
  "data": "OK"
}
```

Response Body (Failed) :

```json
{
  "errors": "Unauthorized, ..."
}
```
