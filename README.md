PHP-MySQL-Assignment
====================
In this assignment you will make a simple interface to work with a database.

Database Requirements
---------------------
The database will be a single table database that tracks a grocery store's inventory. It will have the following attributes:
  - id - an auto incrementing integer which is the primary key/
  - name - the name of the product, this should be a variable length string with a maximum length of 255 characters. This is a required field and must be unique.
  - category - the category the product belongs to (fruit, cereal, dairy etc), this should be a variable length string with a maximum length of 255 characters.
  - price - the amount charged, this should be a decimal with a maximum value of $999.99. This is a required field.

Interface Requirements
----------------------
The interface should have the following pieces:
  - Add product
    - There should be text fields for the name, category and price.
    - There should be a button for adding a product
      - When the button is clicked it should attempt to add the product to the list of products. If there are any invalid values it should say what value was invalid in user readable language. It should not output the standard MySQL or PHP error message.
  - There should be a table of products that list the name, category and price
    - Each row should have a "Delete" button
      - When clicked, this should delete that product from the table.
  - There should be a form to alter the price of a category
    - This should have a drop down of all categories currently existing in the products table
    - It should have a field to enter a percent
    - It should have a button labeled "Alter prices"
      - When clicked, it should adjust the price of all products in that category by multiplying the product price with the percentage.
  - There should be a button labeled "Delete All Products". This is mainly to facilitate testing. When clicked, all products in the table should be deleted.
      
