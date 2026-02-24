## How to install:
```bash
  git clone https://github.com/gufi2115/Microservice-to-save-files.git
```

```bash
  cd Microservice-to-save-files/
```

```bash
  nano .env
```
 
paste it:
```.dotenv
SECRET_KEY=
DATABASE_NAME=
DATABASE_USER=
DATABASE_PASSWORD=
DATABASE_HOST=
DATABASE_PORT=
API_KEY=
HOST=
API_PORT=
DEBUG=true/false
SWAGGER_DOCUMENTATION=true/false
```

```bash
  docker compose up --build 
```

## Endpoints

#### Post file

```http
 Post /api/file/
```

| Name   | Type   | Required                                                    |
|:-------|:-------|:------------------------------------------------------------|
| `file` | `file` | **Required in header**. Authorization: f"api-key {API_KEY}" |

#### Get item

```http
  GET /api/file/{id}/
```

| Name   | Type   | Required                                                    |
|:-------|:-------|:------------------------------------------------------------|
| `file` | `file` | **Required in header**. Authorization: f"api-key {API_KEY}" |


#### Delete item

```http
  DELETE /api/file/{id}/
```

#### Docs OpenAPI

If you have SWAGGER_DOCUMENTATION on True

```http
    /api/docs/swagger/
    /api/docs/redoc/
```


