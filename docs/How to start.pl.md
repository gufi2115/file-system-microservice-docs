## Jak uruchomić
```bash
  git clone https://github.com/gufi2115/Microservice-to-save-files.git
```

```bash
  cd Microservice-to-save-files/
```

```bash
  nano .env
```
 
Wklej to:
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

## Punkty końcowe

#### Post file

```http
 Post /api/file/
```

| Nazwa | Typ     | Wymagane                                                     |
| :-------- | :------- |:-------------------------------------------------------------|
| `file` | `file` | **Wymagane w nagłówku**. Authorization: f"api-key {API_KEY}" |

#### Get item

```http
  GET /api/file/{id}/
```

| Nazwa | Typ    | Wymagane                                                    |
| :-------- | :------- |:------------------------------------------------------------|
| `file`      | `file` | **Wymagane w nagłówku**. Authorization: f"api-key {API_KEY}"                   |


#### Delete item

```http
  DELETE /api/file/{id}/
```

#### Dokumentacja API

Jeżeli masz SWAGGER_DOCUMENTATION na True

```http
    /api/docs/swagger/
    /api/docs/redoc/
``` 


