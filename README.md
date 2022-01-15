# FastAPI_CRUD

Introduction to FastAPI

- FastAPI is a modern and fast web framework for bulding APIs
- FastAPI supports concurrency and coroutines without importing asyncio package
- One of the fastest Python frameworks available
- Designed to be easy to use and learn.

# FastAPI Features

- OpenAPI(Swagger) for API creation, including declarations of path operations, parameters, body requests etc.
- Automatic data model documentation with JSON Schema (as OpenAPI itself is based on JSON Schema).
- Automatic docs: Interactive API documentation (OpenAPI)
- No new syntax to learn. Just standard modern Python.

Before We Start need to install:

Install FastAPI:
> pip install fastapi

Install Uvicorn:
> pip install uvicorn

Install Starlette:
> pip install starlette

  Or
  
> pip install fastapi uvicorn starlette

# File structure
![HTTP Methods](https://github.com/Mithlesh-Navlakhe/FastAPI_CRUD/blob/main/asset/Snap001.png)

# Create model from base model

```
class City(BaseModel):
    name: str
    pincode: int
```    

# Post method

```
@app.post('/cities')
def create_city(city: City):
    db.append(city.dict())
    return db[-1]
```
# Get method
```
@app.get('/cities')
def get_cities():
    return db
```
# Delete method
```
@app.delete('/cities/{city_id}')
def delete_city(city_id: int):
    db.pop(city_id-1)
    return {}
```
# Get selected record
```
@app.get('/cities/{city_id}')
def get_city(city: int):
    return db[city-1]
```
# Run it
```
python main.py
```
Now, this is the additional function from FastAPI that really makes me excited which is the automated generated docs (Swagger UI). To access the Swagger UI enter the API endpoint /docs and there you go — an interactive GUI to test your API endpoints. Having a Swagger UI makes it easier to explain your program to others as well.

![HTTP Methods](https://github.com/Mithlesh-Navlakhe/FastAPI_CRUD/blob/main/asset/Snap002.png)

# Get method
![HTTP Methods](https://github.com/Mithlesh-Navlakhe/FastAPI_CRUD/blob/main/asset/Snap003.png)
