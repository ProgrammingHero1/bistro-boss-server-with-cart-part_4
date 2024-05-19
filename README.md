# Bistro Boss Server with Cart
Client Repo Link - [bistro-boss-client-with-Cart](https://github.com/ProgrammingHero1/bistro-boss-client-with-cart-part_4)


## Overview
BistroBoss is a comprehensive restaurant management system designed to streamline operations, enhance customer experience, and improve overall efficiency. The system leverages modern web technologies to provide a robust, scalable, and high-performance solution for managing complex data structures and interactions within a restaurant environment.

## API End Points
### Cart 
- **GET /cart:** Retrieve all cart items.
```js
app.get('/carts', async (req, res) => {
      const email = req.query.email;
      const query = { email: email };
      const result = await cartCollection.find(query).toArray();
      res.send(result);
    });
```
- **POST /cart:** insert into  all cart collection.
 ```js
  app.post('/carts', async (req, res) => {
      const cartItem = req.body;
      const result = await cartCollection.insertOne(cartItem);
      res.send(result);
    });
 ```
- **DELETE /cart:** Delete a  specific cart item from   cart collection.
 ```js
  app.delete('/carts/:id', async (req, res) => {
      const id = req.params.id;
      const query = { _id: new ObjectId(id) }
      const result = await cartCollection.deleteOne(query);
      res.send(result);
    })
 ```
### Menu
- **GET /menu:** Retrieve all menu items.
  ```js
  app.get('/menu', async (req, res) => {
      const result = await menuCollection.find().toArray();
      res.send(result);
  });

