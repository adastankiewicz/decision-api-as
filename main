from fastapi import FastAPI, Request
from pydantic import BaseModel
from typing import Optional

app = FastAPI()


class InputData(BaseModel):
    num1: Optional[float] = 0.0
    num2: Optional[float] = 0.0


@app.post("/api/v1.0/predict")
async def predict(data: InputData):
    num1 = data.num1 or 0.0
    num2 = data.num2 or 0.0
    result = 1 if (num1 + num2) > 5.8 else 0

    return {
        "prediction": result,
        "features": {
            "num1": num1,
            "num2": num2
        }
    }
