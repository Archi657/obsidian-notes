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