# GUVI - DAY 35

## MongoDB Day 1 Exercises

1. About MongoDB.

   > - MongoDB is a No-SQL database.
   > - It is a document oriented database that utilizes JSON like documents.
   > - Unlike MySQL, where data is split as tables, here data is classified into collections and documents.
   > - To infer directly from MySQL, we can say that _Collections_ are equivalent to _MySQL Tables_ and Documents are equivalent to _MySQL Rows_.
   > - Unlike MySQL, MongoDB documents are unstructured, which makes it more scalable.

2. About the Task.

   > - In this task, we are given a data file URL.
   > - The data from that URL is downloaded and uploaded to our mongodb database. [Source](./product.json)
   > - This data is to be queried as per the given 10 questions and their solutions are to be attached.
   > - The complete solution is compiled into a single document. [Source](./Document.pdf)

3. Setup

   > - First, we download the data from the task document specified URL.
   > - we create a database, using the MongoDB Compass UI.
   > - We create a database named `zenTask35` and a collection named `products`.
   > - We click on `add data` option, and upload our `product.json` file.
   > - On refreshing the collection, the data get populated.

4. Solution

   > - In this section, the query solutions for our given 10 questions are discussed. The solution snippets, with the data output are attached in the solution document. [Document URL](./Document.pdf)

   1. Find all the information about each products.

      ```
      db.products.find()
      ```

   2. Find the product price which are between 400 to 800.

      ```
      db.products.find({product_price:{$gte:400,$lte:800}})
      ```

   3. Find the product price which are not between 400 to 600.

      ```
      db.products.find({product_price:{$not:{$gte:400, $lte:600}}})
      ```

   4. List the four product which are greater than 500 in price.

      ```
      db.products.find({product_price:{$gt:500}},{}).limit(4)
      ```

   5. Find the product name and product material of each products.

      ```
      db.products.find({},{product_name:1, product_material:1})
      ```

   6. Find the product with a row id of 10.

      ```
      db.products.find({id:"10"},{})
      ```

   7. Find only the product name and product material.

      ```
      db.products.find({},{product_name:1, product_material:1})
      ```

   8. Find all products which contain the value of soft in product material.

      ```
      db.products.find({product_material:"Soft"})
      ```

   9. Find products which contain product color indigo and product price 492.00.

      ```
      db.products.find({product_color:"indigo",product_price:492.00})
      ```

   10. Delete the products which product price value are 28.

       ```
       db.products.deleteOne({product_price:28})
       ```
