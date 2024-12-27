## Unit tests vs. system tests
Classify the characteristics of unit tests and system tests.

**Instructions**

- Drag the characteristics to the proper category.

| Unit Tests | System Tests |
| ---------- | ------------ |
| Validate code block | Require running application |
| Require isolated environment | Use `pytest` with `TestClient` |
| Use `pytest` | Validate system function |

> Well done! You've learned the difference between unit and system tests.

<br>

## System test
You've built your FastAPI application and added unit tests to verify code functionality. Writing a system test for an API endpoint will ensure that the endpoint works on the running application.

We can't run the FastAPI server directly with "Run this file" - see the instructions for how to run the server and test your code from the terminal.

**Ide Exercise Instruction**

- Review the GET endpoint defined in `main.py`.
- Complete the following system test in `system_test.py`
- In the terminal, run `pytest`. 

``` python
from fastapi.testclient import TestClient
from main import app

client = TestClient(app)

def test_main():
    response = client.get("/items?name=scissors")
    assert response.status_code == 200
    assert response.json() == {"name": "scissors",
                               "quantity": 100}
```

```
pytest system_test.py
```

> Great work! You've created and tested your system test for FastAPI.

<br>

## 

> 

<br>

## 

> 

<br>

## 

> 

<br>

## 

> 

<br>

## 

> 
