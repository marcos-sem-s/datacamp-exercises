## PUT operation in action
You've been asked to create a PUT endpoint `/items` that accepts parameters `name` and `description` and updates the `description` based on the `name` in a key-value store called `items`.

You can't run the FastAPI server directly with "Run this file" - see the instructions for how to run the server and test your code from the terminal.

**Ide Exercise Instruction**

- Define pydantic model Item so that parameters `name` and `description` can be passed into the PUT body.
- Update `description` in `items` based on the key `name`.
- Run the live server from the terminal: fastapi dev main.py.
- Open a new terminal (top-right of terminal) and test your code with the following command:
```
curl -X PUT \
  -H 'Content-Type: application/json' \
  -d '{"name": "bananas", "description": "Delicious!"}' \
  http://localhost:8000/items
```

``` python
from fastapi import FastAPI
from pydantic import BaseModel

class Item(BaseModel):
    name: str
    description: str

items = {"bananas": "Yellow fruit."}

app = FastAPI()


@app.put("/items")
def update_item(item: Item):
    name = item.name
    items[name] = item.description
    return item
```

```
fastapi dev main.py

curl -X PUT \
  -H 'Content-Type: application/json' \
  -d '{"name": "bananas", "description": "Delicious!"}' \
  http://localhost:8000/items
```

> Great work! You've created and tested your first PUT endpoint. Now you can build endpoints that traditionally update existing objects.

<br>

## DELETE operation in action
You've been asked to create a DELETE endpoint that accepts parameter `name` and deletes the item called `name` from a key store called `items`.

You can't run the FastAPI server directly with "Run this file" - see the instructions for how to run the server and test your code from the terminal.

**Ide Exercise Instruction**

- Define pydantic model `Item` with parameter `name`.
- Delete from `items` based on the key `name`.
- Run the live server from the terminal: `fastapi dev main.py`.
- Open a new terminal (top-right of terminal) and test your code with the following command:

```
curl -X DELETE \
  -H 'Content-Type: application/json' \
  -d '{"name": "bananas"}' \
  http://localhost:8000/items
```

``` python
from fastapi import FastAPI
from pydantic import BaseModel

# Define model Item
class Item(BaseModel):
    name: str

# Define items at application start
items = {"apples", "oranges", "bananas"}

app = FastAPI()


@app.delete("/items")
def delete_item(item: Item):
    name = item.name
    # Delete the item
    items.remove(name)
    return {}
```

```
fastapi dev main.py

curl -X DELETE \
  -H 'Content-Type: application/json' \
  -d '{"name": "bananas"}' \
  http://localhost:8000/items
```

> Great work! You've created and tested your first DELETE endpoint. Now you can build endpoints that traditionally delete existing objects.

<br>

## Status code classification
Classify the status codes by whether or not they indicate success.

**Instructions**

Drag the status codes to the proper category.

| Success | Not Success |
| ------- | ----------- |
| 200 | 400 |
| 201 | 404 |
| 202 | 500 |

> Well done! You can classify common status code as success or not.

<br>

## Handling a client error
You've been asked to create a DELETE endpoint that accepts parameter `name` and deletes the item called `name` from a key store called `items`. If the item is not found, the endpoint should return an appropriate status code and detailed message.

You can't run the FastAPI server directly with "Run this file" - see the instructions for how to run the server and test your code from the terminal.

**Ide Exercise Instruction**

- Import `HTTPException` from `FastAPI`.
- Raise `HTTPException` if an item is not in `items`.
- Specify the appropriate status code for "not found."
- Run the live server from the terminal: `fastapi dev main.py`.
- Open a new terminal (top-right of terminal) and test your code with the following command:

```
curl -X DELETE \
  -H 'Content-Type: application/json' \
  -d '{"name": "bananas"}' \
  http://localhost:8000/items
```

``` python
from fastapi import FastAPI, HTTPException
from pydantic import BaseModel

# Define model Item
class Item(BaseModel):
    name: str

# Define items at application startup
items = {"apples", "oranges"}

app = FastAPI()


@app.delete("/items")
def delete_item(item: Item):
    name = item.name
    if name in items:
        items.remove(name)
    else:
        # Raise HTTPException with status code for "not found"
        raise HTTPException(status_code=404, detail="Item not found.")
    return {}
```

```
fastapi dev main.py

curl -X DELETE \
  -H 'Content-Type: application/json' \
  -d '{"name": "bananas"}' \
  http://localhost:8000/items
```

> Great work! You've created and tested your first endpoint with error handling. Now you can build endpoints that can communicate status within the application.

<br>

## When should we use async?
When should we use async in FastAPI? Select one answer

- [ ] When we want our application to run faster
- [ ] When our application communicates with a database
- [x] When all the functions within our endpoint can be called with await

> Perfect! You know exactly when to use async.

<br>

## Asynchronous DELETE operation
You've been asked to create an API endpoint that deletes items managed by your API. To accomplish this, create an endpoint `/items` that serves HTTP DELETE operations. Make the endpoint asynchronous, so that your application can continue to serve requests while maintaining any long-running deletion tasks.

We can't run the FastAPI server directly with "Run this file" - see the instructions for how to run the server and test your code from the terminal.

**Ide Exercise Instruction**

- Make the delete operation asynchronous.
- Validate the existence of `item.name` in list `items`.
- Return the appropriate status code for "not found."
- Run the live server from the terminal: `fastapi dev main.py`.
- Open a new terminal (top-right of terminal) and test your code with the following command:
```
curl -X DELETE \
  -H 'Content-Type: application/json' \
  -d '{"name": "rock"}' \
  http://localhost:8000/items

curl -X DELETE \
  -H 'Content-Type: application/json' \
  -d '{"name": "roll"}' \
  http://localhost:8000/items
```

``` python
from fastapi import FastAPI, HTTPException
from pydantic import BaseModel

# Define model Item
class Item(BaseModel):
    name: str

app = FastAPI()

items = {"rock", "paper", "scissors"}


@app.delete("/items")
# Make asynchronous
async def root(item: Item):
    name = item.name
    # Check if name is in items
    if item not in items:
        # Return the status code for not found
        raise HTTPException(status_code=404, detail="Item not found.")
    items.remove(name)
    return {"message": "Item deleted"}
```

```
fastapi dev main.py

curl -X DELETE \
  -H 'Content-Type: application/json' \
  -d '{"name": "rock"}' \
  http://localhost:8000/items

curl -X DELETE \
  -H 'Content-Type: application/json' \
  -d '{"name": "roll"}' \
  http://localhost:8000/items
```

> Great work! You've created and tested your first asynchronous DELETE endpoint. This is the traditional operation for endpoints that delete data managed by the API, and the final operation you need to build an application with a CRUD (Create, Read, Update & Delete) API.
