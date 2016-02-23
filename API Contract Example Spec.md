##Users
* User object
```
{
  id: integer
  username: string
  email: string
  created_at: datetime(iso 8601)
  updated_at: datetime(iso 8601)
}
```
**GET /users**
----
  Returns all users in the system.
* **URL Params**
  None
* **Data Params**
  None
* **Headers**
  None
* **Success Response:**
* **Error Response:**
  OR 

**GET /users/:id**
----
  Returns the specified user.
* **URL Params**
  **Required:** `id=[integer]`
* **Data Params**
  None
* **Headers**
  None
* **Success Response:**
* **Error Response:**
  OR 

**GET /users/:id/orders**
----
  Returns all Orders associated with the specified user.
* **URL Params**
  **Required:** `id=[integer]`
* **Data Params**
  None
* **Headers**
  None
* **Success Response:**
* **Error Response:**
  OR 

**POST /users**
----
  Creates a new User and returns the new object.
* **URL Params**
  None
* **Headers**
  None
* **Data Params**
```
  {

  }
```
* **Success Response:**
* **Error Response:**
  OR 

**PATCH /users/:id**
----
  Updates fields on the specified user and returns the updated object.
* **URL Params**
  **Required:** `id=[integer]`
* **Data Params**
```
  {

  }
```
* **Headers**
  None
* **Success Response:**
* **Error Response:**
  OR 

**DELETE /users/:id**
----
  Deletes the specified user.
* **URL Params**
  **Required:** `id=[integer]`
* **Data Params**
  None
* **Headers**
  None
* **Success Response:**
* **Error Response:**
  OR 

##Products
* Product object
```
{
  id: integer
  name: string
  cost: float(2)
  available_quantity: integer
  created_at: datetime(iso 8601)
  updated_at: datetime(iso 8601)
}
```
**GET /products**
----
  Returns all products in the system.
* **URL Params**
  None
* **Data Params**
  None
* **Headers**
  None
* **Success Response:**
* **Error Response:**
  OR 

**GET /products/:id**
----
  Returns the specified product.
* **URL Params**
  **Required:** `id=[integer]`
* **Data Params**
  None
* **Headers**
  None
* **Success Response:**
* **Error Response:**
  OR 

**GET /products/:id/orders**
----
  Returns all Orders associated with the specified product.
* **URL Params**
  **Required:** `id=[integer]`
* **Data Params**
  None
* **Headers**
  None
* **Success Response:**
* **Error Response:**
  OR 

**POST /products**
----
  Creates a new Product and returns the new object.
* **URL Params**
  None
* **Data Params**
```
  {

  }
```
* **Headers**
  None
* **Success Response:**
* **Error Response:**
  OR 

**PATCH /products/:id**
----
  Updates fields on the specified product and returns the updated object.
* **URL Params**
  **Required:** `id=[integer]`
* **Data Params**
```
  {

  }
```
* **Headers**
  None
* **Success Response:**
* **Error Response:**
  OR 

**DELETE /products/:id**
----
  Deletes the specified product.
* **URL Params**
  **Required:** `id=[integer]`
* **Data Params**
  None
* **Headers**
  None
* **Success Response:**
* **Error Response:**
  OR 

##Orders
* Order object
```
{
  id: integer
  user_id: <user_id>
  total: float(2)
  products: [
              { 
                product: <product_id>,
                quantity: integer 
              },
              { 
                product: <product_id>,
                quantity: integer 
              },
              { 
                product: <product_id>,
                quantity: integer 
              },
            ]
  created_at: datetime(iso 8601)
  updated_at: datetime(iso 8601)
}
```
**GET /orders**
----
  Returns all users in the system.
* **URL Params**
  None
* **Data Params**
  None
* **Headers**
  None
* **Success Response:**
* **Error Response:**
  OR 

**GET /orders/:id**
----
  Returns the specified order.
* **URL Params**
  **Required:** `id=[integer]`
* **Data Params**
  None
* **Headers**
  None
* **Success Response:**
* **Error Response:**
  OR 

**GET /orders/:id/products**
----
  Returns all Products associated with the specified order.
* **URL Params**
  **Required:** `id=[integer]`
* **Data Params**
  None
* **Headers**
  None
* **Success Response:**
* **Error Response:**
  OR 

**GET /orders/:id/user**
----
  Returns all Users associated with the specified order.
* **URL Params**
  **Required:** `id=[integer]`
* **Data Params**
  None
* **Headers**
  None
* **Success Response:**
* **Error Response:**
  OR 

**POST /orders**
----
  Creates a new Order and returns the new object.
* **URL Params**
  None
* **Data Params**
```
  {

  }
```
* **Headers**
  None
* **Success Response:**
* **Error Response:**
  OR 

**PATCH /orders/:id**
----
  Updates fields on the specified order and returns the updated object.
* **URL Params**
  **Required:** `id=[integer]`
* **Data Params**
```
  {

  }
```
* **Headers**
  None
* **Success Response:**
* **Error Response:**
  OR 

**DELETE /orders/:id**
----
  Deletes the specified order.
* **URL Params**
  **Required:** `id=[integer]`
* **Data Params**
  None
* **Headers**
  None
* **Success Response:**
* **Error Response:**
  OR 