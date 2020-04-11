# Music-Store
A menu-driven program written in C++ that uses binary files to manage sales for a music store.

It uses a class product to store details about the various instruments available for sale. All the records are stored in a binary file. 
A customer can view the catalogue and place an order by searching for the name of the product. An invoice is automatically generated and the quantity in stock is reduced. The Admin staff can also view the catalogue and modify the records in whatever way they deem fit. <br>

The welcome page of the programme has two main components: the Admin Menu, and the Customer Menu. <br>
The Admin Menu:<br>
The Admin Menu allows the user to view, create, modify, and delete products from the records.<br>
The Customer Menu: <br>
The Customer Menu allows the user to view catalogue and place orders.<br> 

The role of the functions in the class is as follows:<br>
void pcreate(): used to create a record in the binary file. <br>
void pdisp(): used to display all records in a binary file.<br>
int retpid(), int retqty(), long int retprice(): Accessor functions used to return the Product ID (pid), Quantity in stock (qty), and Price (price) respectively to the calling function.<br>
int retname (char uname[]): returns 0 if the string passed as argument matches the original string in the binary file. This function is invoked when the customer searches for the product when placing an order. <br>
void update(int): Used to update (reduce) the quantity in store after a customer places an order.<br>
void bill(int): Used to generate the invoice after the customer places an order, depending on the quantity ordered.<br>

The list of variables used is as follows:<br>
int pid:			product id of product in records<br>
int qty:			quantity of product in records<br>
long int price:		price of the product<br>
char name[50]:		name of product<br>
char brand[50]:		brand of product <br>
