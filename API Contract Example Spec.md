**Users**
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
**Product**
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
**Order**
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
