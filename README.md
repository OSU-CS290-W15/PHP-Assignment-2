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
      
Rough Testing Protocol
----------------------
- Locate and click the "Delete All Products" button.
- All products should have been removed.
- Locate the form to alter the price of a category.
  - Is the category form empty?
- Locate the portion of the interface that is used for adding products.
  - Does there exist clearly marked fields to enter the name, category and price?
  - Is there a button to add a product?
  - Input 'foo' in the category field, input 1.00 in the price field.
  - Click the add product button.
    - Are you notified that name is a required field?
    - Was a product added? (A new item should not have been added)
  - Input 'Apple' into the name field and 'bar' into the price field and attempt to add the product
    - Are you notified that the price must be a number?
    - Was a product added? (It should not have been)
  - Input 'Banana' into the name field, 'Fruit' into the category field and 2.00 into the price field and attempt to add the product
    - Was a 'Banana' added with a category of 'Fruit' and a price of 2.00?
    - Does the category menu now list 'Fruit' as a category?
  - Input 'Apple' into the name field, 'Fruit' into the category field and 1.00 into the price field and attempt to add the product 
    - Was a 'Apple' added with a category of fruit and a price of 1.00?
    - Does the category menu still only list a single entry for fruit?
  - Input 'Frosted Flakes' into the name field, 'Breakfast' into the category field and 5.50 into the price field.
    - Was 'Frosted Flakes' added with a category of 'Breakfast' and a price of 5.50?
    - Is 'Breakfast' now listed in the category menu?
- Locate the form to alter the price of a category.
  - Enter 200% into the field.
  - Select the fruit category.
  - Click the 'Alter Price' button.
    - Is the price of a Banana now 4.00 and an apple 2.00?
    - Is the price of 'Frosted Flakes' still 5.50?
- Does each entry in the table have a 'delete' button?
- Click the delete button for the Banana.
  - Was the Banana entry deleted?
  - Did all other entries remain the same?
- Close the browser.
- Reopen the browser and navigate back to the page.
  - Are the Apple and Frosted Flakes still listed?
