
# FastAPI

* Structure
```
FastAPI
├── model_name
    ├── main.app
```    

### Quick start
1. Create FastAPI main.py
```
from enum import Enum

from fastapi import FastAPI

class ModelName(str,Enum):
    alexnet ='alexnet'
    resnet ='resnet'
    lenet ='lenet'

app = FastAPI()

@app.get("/models/{model_name}")
async def get_model(model_name:ModelName):
    if model_name == ModelName.alexnet:
        return{"model_name":model_name,"message":"Deep Learning FTW!"}
    if model_name.value == "lenet":
        return{"model_name":model_name,"message":"LeCNN all the images"}
    return{"model_name":model_name,"message":"Have some residuals"}

```


2. run main.py
> Open Terminal in main.py path

```
$ uvicorn main:app --reload
```

3. see the url

* http://localhost:8000/models/alexnet
* http://localhost:8000/models/resnet
* http://localhost:8000/models/lenet
* http://localhost:8000/docs
* http://localhost:8000/redoc


4. see the terminal INFO
