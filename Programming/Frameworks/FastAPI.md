Asyncronous, based on Starlette and Pydantic for validations.

Install
pip install "fastapi[standard]"

```Python
# Basic program
from fastapi import FastAPI

api = FastAPI()

@api.get('/')

def index():
    return {"message": "Hello World"}


@api.get("/getdata")
def get_data_from_db():

```
Get Random
```Python
@router.get("/random/{number}")
async def get_random(number: int):
    try:
        # Make sure the number is positive
        if number <= 0:
            raise HTTPException(status_code=400, detail="Number must be greater than 0")
        data_cursor = collection.aggregate([{"$sample": {"size": number}}])
        data = list(data_cursor)
        if list_serializer:
            return list_serializer(data)
        return [serializer(d) for d in data]
    except Exception as e:
        raise HTTPException(status_code=500, detail=f"Some error occurred:{e}")

```
