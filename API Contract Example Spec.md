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
  Content-Type: application/json  
* **Success Response:**  
* **Code:** 200 <br />
  **Content:**  
```
{
  users: [
           {<user_object>},
           {<user_object>},
           {<user_object>}
         ]
}
```

**GET /users/:id**
----
  Returns the specified user.
* **URL Params**  
  *Required:* `id=[integer]`
* **Data Params**  
  None
* **Headers**  
  Content-Type: application/json  
  Authorization: Bearer `<OAuth Token>`
* **Success Response:**  
* **Error Response:**  
  * **Code:** 404  
  **Content:** `{ error : "User doesn't exist" }`  
  OR  
  * **Code:** 401  
  **Content:** `{ error : error : "You are unauthorized to make this request." }

**GET /users/:id/orders**
----
  Returns all Orders associated with the specified user.
* **URL Params**  
  *Required:* `id=[integer]`
* **Data Params**  
  None
* **Headers**  
  Content-Type: application/json  
  Authorization: Bearer `<OAuth Token>`
* **Success Response:**  
* **Error Response:**  
  * **Code:** 404  
  **Content:** `{ error : "User doesn't exist" }`  
  OR  
  * **Code:** 401  
  **Content:** `{ error : error : "You are unauthorized to make this request." }

**POST /users**
----
  Creates a new User and returns the new object.
* **URL Params**  
  None
* **Headers**  
  Content-Type: application/json  
* **Data Params**  
```
  {

  }
```
* **Success Response:**  

**PATCH /users/:id**
----
  Updates fields on the specified user and returns the updated object.
* **URL Params**  
  *Required:* `id=[integer]`
* **Data Params**  
```
  {

  }
```
* **Headers**  
  Content-Type: application/json  
  Authorization: Bearer `<OAuth Token>`
* **Success Response:**  
* **Error Response:**  
  * **Code:** 404  
  **Content:** `{ error : "User doesn't exist" }`  
  OR  
  * **Code:** 401  
  **Content:** `{ error : error : "You are unauthorized to make this request." }

**DELETE /users/:id**
----
  Deletes the specified user.
* **URL Params**  
  *Required:* `id=[integer]`
* **Data Params**  
  None
* **Headers**  
  Content-Type: application/json  
  Authorization: Bearer `<OAuth Token>`
* **Success Response:**  
* **Error Response:**  
  * **Code:** 404  
  **Content:** `{ error : "User doesn't exist" }`  
  OR  
  * **Code:** 401  
  **Content:** `{ error : error : "You are unauthorized to make this request." }

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
  Content-Type: application/json  
* **Success Response:**  

**GET /products/:id**
----
  Returns the specified product.
* **URL Params**  
  *Required:* `id=[integer]`
* **Data Params**  
  None
* **Headers**  
  Content-Type: application/json  
  Authorization: Bearer `<OAuth Token>`
* **Success Response:**  
* **Error Response:**  
  * **Code:** 404  
  **Content:** `{ error : "Product doesn't exist" }`  
  OR  
  * **Code:** 401  
  **Content:** `{ error : error : "You are unauthorized to make this request." }

**GET /products/:id/orders**
----
  Returns all Orders associated with the specified product.
* **URL Params**  
  *Required:* `id=[integer]`
* **Data Params**  
  None
* **Headers**  
  Content-Type: application/json  
  Authorization: Bearer `<OAuth Token>`
* **Success Response:**  
* **Error Response:**  
  * **Code:** 404  
  **Content:** `{ error : "Product doesn't exist" }`  
  OR  
  * **Code:** 401  
  **Content:** `{ error : error : "You are unauthorized to make this request." }

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
  Content-Type: application/json  
* **Success Response:**  

**PATCH /products/:id**
----
  Updates fields on the specified product and returns the updated object.
* **URL Params**  
  *Required:* `id=[integer]`
* **Data Params**  
```
  {

  }
```
* **Headers**  
  Content-Type: application/json  
  Authorization: Bearer `<OAuth Token>`
* **Success Response:**  
* **Error Response:**  
  * **Code:** 404  
  **Content:** `{ error : "Product doesn't exist" }`  
  OR  
  * **Code:** 401  
  **Content:** `{ error : error : "You are unauthorized to make this request." }

**DELETE /products/:id**
----
  Deletes the specified product.
* **URL Params**  
  *Required:* `id=[integer]`
* **Data Params**  
  None
* **Headers**  
  Content-Type: application/json  
  Authorization: Bearer `<OAuth Token>`
* **Success Response:**  
* **Error Response:**  
  * **Code:** 404  
  **Content:** `{ error : "Product doesn't exist" }`  
  OR  
  * **Code:** 401  
  **Content:** `{ error : error : "You are unauthorized to make this request." }

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
  Content-Type: application/json  
* **Success Response:**  

**GET /orders/:id**
----
  Returns the specified order.
* **URL Params**  
  *Required:* `id=[integer]`
* **Data Params**  
  None
* **Headers**  
  Content-Type: application/json  
  Authorization: Bearer `<OAuth Token>`
* **Success Response:**  
* **Error Response:**  
  * **Code:** 404  
  **Content:** `{ error : "Order doesn't exist" }`  
  OR  
  * **Code:** 401  
  **Content:** `{ error : error : "You are unauthorized to make this request." }

**GET /orders/:id/products**
----
  Returns all Products associated with the specified order.
* **URL Params**  
  *Required:* `id=[integer]`
* **Data Params**  
  None
* **Headers**  
  Content-Type: application/json  
  Authorization: Bearer `<OAuth Token>`
* **Success Response:**  
* **Error Response:**  
  * **Code:** 404  
  **Content:** `{ error : "Order doesn't exist" }`  
  OR  
  * **Code:** 401  
  **Content:** `{ error : error : "You are unauthorized to make this request." }

**GET /orders/:id/user**
----
  Returns all Users associated with the specified order.
* **URL Params**  
  *Required:* `id=[integer]`
* **Data Params**  
  None
* **Headers**  
  Content-Type: application/json  
  Authorization: Bearer `<OAuth Token>`
* **Success Response:**  
* **Error Response:**  
  * **Code:** 404  
  **Content:** `{ error : "Order doesn't exist" }`  
  OR  
  * **Code:** 401  
  **Content:** `{ error : error : "You are unauthorized to make this request." }

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
  Content-Type: application/json  
* **Success Response:**  

**PATCH /orders/:id**
----
  Updates fields on the specified order and returns the updated object.
* **URL Params**  
  *Required:* `id=[integer]`
* **Data Params**  
```
  {

  }
```
* **Headers**  
  Content-Type: application/json  
  Authorization: Bearer `<OAuth Token>`
* **Success Response:**  
* **Error Response:**  
  * **Code:** 404  
  **Content:** `{ error : "Order doesn't exist" }`  
  OR  
  * **Code:** 401  
  **Content:** `{ error : error : "You are unauthorized to make this request." }

**DELETE /orders/:id**
----
  Deletes the specified order.
* **URL Params**  
  *Required:* `id=[integer]`
* **Data Params**  
  None
* **Headers**  
  Content-Type: application/json  
  Authorization: Bearer `<OAuth Token>`
* **Success Response:**  
* **Error Response:**  
  * **Code:** 404  
  **Content:** `{ error : "Order doesn't exist" }`  
  OR  
  * **Code:** 401  
  **Content:** `{ error : error : "You are unauthorized to make this request." }