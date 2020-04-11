# Music-Store
A menu-driven program written in C++ that uses binary files to manage sales for a music store.

It uses a class product to store details about the various instruments available for sale. All the records are stored in a binary file. 
A customer can view the catalogue and place an order by searching for the name of the product. An invoice is automatically generated and the quantity in stock is reduced. The Admin staff can also view the catalogue and modify the records in whatever way they deem fit.

The welcome page of the programme has two main components: the Admin Menu, and the Customer Menu. 
The Admin Menu:
The Admin Menu allows the user to view, create, modify, and delete products from the records.
The Customer Menu: 
The Customer Menu allows the user to view catalogue and place orders. 

The role of the functions in the class is as follows:
void pcreate(): used to create a record in the binary file.
void pdisp(): used to display all records in a binary file.
int retpid(), int retqty(), long int retprice(): Accessor functions used to return the Product ID (pid), Quantity in stock (qty), and Price (price) respectively to the calling function.
int retname (char uname[]): returns 0 if the string passed as argument matches the original string in the binary file. This function is invoked when the customer searches for the product when placing an order. 
void update(int): Used to update (reduce) the quantity in store after a customer places an order.
void bill(int): Used to generate the invoice after the customer places an order, depending on the quantity ordered.

The list of variables used is as follows:
int pid			product id of product in records
int qty			quantity of product in records
long int price		price of the product
char name[50]		name of product
char brand[50]		brand of product 
