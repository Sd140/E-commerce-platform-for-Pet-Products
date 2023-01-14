# PetOzone.github.io

PetOzone is an ecommerce website that allows user to select and buy pet accessories,food,medicines,etc from the comfort of their homes.User can book can appointment of veterinarian for their pets from the information provided on website.

The website is made using HTML,CSS,Javascript,Bootstrap,Tailwind for frontend and Flask as a beckedn language with MySQL for database. 

Website Flow:

When a user first visits the website they will be asked to register and provide their details.
User can then log in to view the homepage of the website.
On products page user can view products and add to their cart various accessories,food,etc for their pets.
User can also enter an item to search in the searchbox and view all products related to the term they entered.
User can visit their cart to see the products they want to buy and can also remove them.
Check Out and see the final price to pay along with the items bought.
User can view their previously bought items in Orders page.


**MySQL**
MySQL server is used as databse to store the data required in making this website. The various tables used are:

Customer: In this table, we will be storing users data such as cust_id, username, contact_no, password, email. We will be storing this information when a user registers on the website & we will be using this information when a user wants to log in .

Product : The details and stock of products available on our website will be stored in this table. Following are the attributes: , prod_id , pet_id , price , stock_quantity , product_sub_category.

Prod_category: Categories of products available like food,medicine,clothes and accessories in product table are stored here. Following are the attributes: , prod_category_id , prod_name.

Prod_sub_category : Names of categories of products in product_categories are stored here. For example, pedigree in the food category. Following are the attributes: , prod_sub_category_id , name , prod_category_id.

Cart :Products chosen by customers to buy are added to carts. Following are the attributes: , prod_id , cust_id , quantity .

Order : All the details of customers’ final order are stored here. Following are the attributes: , order_id , order_date , payment_mode , payment_date , invoice_amt , quantity , delivery_location_id , cust_id.

Shipment: Order shipment details will be stored in this table. Following are the attributes: , shipment_id , shipment_date , shipment_status , delivery_date , order_id , cust_id.

Delivery Location : Delivery locations entered by users are stored here. Following are the attributes: , delivery_location_id , location_name , address , cust_id.

Pets : Pets with their id are stored here , pet_id , pet_type.

Relatonal Database Schema

app.py
This is where Flask is used to create the website. Its various functions are:

login_required() is a decorator that ensures that only logged in users can access a part of the website.

rupees() is a Flask filter that will convert the value passed to it to a float with 2 decimal places and add a ruppee sign in front of it.

login() function depicts the login route where a form will be displayed to the user via login.html template. On submitting the form if the user is present in the database then they will be successfully logged in and redirected to the index page otherwise an appropiate error message will be displayed to them.

The logout() functions depicting the logout route will log the user out.

the register() route will display a form to the user via the register.html template which if correctly submitted will register the user to the website and add their details to the databse. They will then be redirected to the login page.

The index() depicts the homepage of the website via index.html which will show dogs and cats as 2 options and on clicking either of them the suers will be redirected to the respective pages.

dogs() function depicts the dogs route which will display the products for dogs with title, image, price on each product. Users have an option to add the product to their carts. The appropiate changes are done in the database.

cats() function depicts the cats route which will display the products for cats with title, image, price on each product. Users have an option to add the product to their carts. The appropiate changes are done in the database.

The cart() function depicting cart route shows the user the products in their cart. Users can remove a product or confirm their order. They will then be redirected to a confirmation page.

address() route displays a form for the user to input their address where the order will be delivered. The address is stored in the databse the first time and displayed to the user on multiple uses.

order() function depicting order route shows the users the status of their orders, i.e. the orders that have delivered already, are being processed, are on the way,etc.

search() function takes input from search box and displays all products that are in the category of the input, start with the input and have the input in the product.

layout.html
This html file contains the layout of the page from which all other html files extend. The page has a navbar at the top and a footer at bottom which will be applied to all the pages in the website.
