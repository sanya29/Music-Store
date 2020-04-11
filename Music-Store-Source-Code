#include<iostream.h>
#include<conio.h>
#include<iomanip.h>
#include<stdio.h>
#include<string.h>
#include<ctype.h>
#include<fstream.h>
#include<process.h>
class product
{
	int pid, qty;
   long int price;
   char name[50], brand[50];
public:
	void pcreate();
   void pdisp();
   int retpid();
   int retqty();
   long int retprice();
   void update(int );
   int retname(char uname[]);
   void bill(int);
}p1;

int product::retqty()
{
	return qty;
}
int product::retname( char uname[])
{
	return strcmpi(name,uname);
}
int product::retpid()
{
	return pid;
}

long int product::retprice()
{
	return price;
}

void product::update(int quantity)
{
	qty=qty-quantity;
}
void product::bill(int quantity)
{
	int totamt;
	cout<<"\n\t\t\tI.N.V.O.I.C.E\n\n";
   p1.pdisp();
   totamt=p1.retprice()*quantity;
   cout<<"\nTotal price :\t"<<totamt;
   getch();
}
void product::pcreate()
{
	cout<<"Enter Product Name\n";
   gets(name);
   cout<<"Enter Product ID\n";
   cin>>pid;
   cout<<"Enter Quantity in Store\n";
   cin>>qty;
   cout<<"Enter Price of Product\n";
   cin>>price;
   cout<<"Enter Brand\n";
   gets(brand);
}

void product::pdisp()
{
	cout<<"Product Name: "<<name<<endl;
   cout<<"Product ID  : "<<pid<<endl;
   cout<<"Quantity    : "<<qty<<endl;
   cout<<"Price       : "<<price<<endl;
   cout<<"Brand       : "<<brand<<endl;
}

void wlc_screen()
{
	clrscr();
   cout<<"(*-*)(*-*)(*-*)(*-*)(*-*)(*-*)(*-*)(*-*)(*-*)(*-*)(*-*)(*-*)(*-*)(*-*)(*-*)(*-*)(*-*)(*-*)(*-*)(*-*)(*-*)(*-*)(*-*)(*-*)(*-*)(*-*)(*-*)(*-*)(*-*)(*-*)(*-*)(*-*)(*-*)(*-*)";
   gotoxy(75,11);
   	cout<<"C.O.M.P.U.T.E.R. P.R.O.J.E.C.T.";
   gotoxy(85,14);
   	cout<<"Done By:";
   gotoxy(82,16);
   	cout<<"RIA KAUR";
   gotoxy(82,17);
      cout<<"SANYA SRIVASTAVA";
   gotoxy(82,18);
      cout<<"SARA MANU";
  	gotoxy(78,24);
   	cout<<"Press any key to continue";
   	getch();

}

void menu()
{
	clrscr();
   cout<<"\n\t\t\t\t\t\t\tWELCOME TO T.R.E.B.L.E.M.A.K.E.R.S. M.U.S.I.C. S.T.O.R.E.";
   cout<<"\n\nPick from a wide variety of options at only the best online music store.";
   cout<<"\n\nM.A.I.N. M.E.N.U.\n\n";
   cout<<"1. About\n";
   cout<<"2. Customer Menu\n";
   cout<<"3. Admin Menu\n";
   cout<<"4. Exit\n";
}

void about()
{
   clrscr();
   cout<<"\n\t\t\t\t\t\tA.B.O.U.T.";
	cout<<"\n\n\nThis is an online sales management software with both a customer menu ";
   cout<<"as well as a staff menu.\n\n\tCustomers may use the program to place orders.";
   cout<<" The staff may use it to modify or delete products from the catalogue.";
   cout<<"\n\n\tThe company policy does not allow exchanges or refunds. An order once placed is considered terminal.\n\n";
   cout<<"Thank you.";
   getch();
}

void catalogue()
{
   clrscr();
   ifstream i1;
   cout<<"\n\nC.A.T.A.L.O.G.U.E.\n\n";
   i1.open("r2.dat",ios::binary);
   while(i1.read((char*)&p1, sizeof(p1)))
   {
   	p1.pdisp();
      cout<<"\n\n=========================================\n\n";
   }
   i1.close();
   getch();
}

void order()
{
	clrscr();
   char uname[50];
   int quantity;
   int c, flag=0;
   ifstream i1;
   ofstream o1;
   i1.open("r2.dat", ios::binary);
   o1.open("r2.dat", ios::binary|ios::ate);
   c=0;
   cout<<"\nWelcome. Please enter the name of the product you want to buy\n";
   gets(uname);
   cout<<"\nPlease enter the quantity you want to purchase\n";
   cin>>quantity;
   while(i1.read((char*)&p1,sizeof(p1)))
   {
      c++;
      if (p1.retname(uname)==0)
      {
			if (quantity<=p1.retqty())
         {
         o1.seekp((c-1)*sizeof(p1),ios::beg);
         p1.update(quantity);
         o1.write((char*)&p1,sizeof(p1));
         p1.bill(quantity);
         }
         flag=1;
         if (quantity>p1.retqty())
         {
            o1.seekp((c-1)*sizeof(p1),ios::beg);
         	if (p1.retqty()==0)
            	cout<<"Sorry we're all out\n";
            else cout<<"\nWe only have "<<p1.retqty()<<" in store.\n";
         }
      }
   }  getch();
   if (flag==0)
   	cout<<"\aName invalid. Are you sure you've got the right name? Please check your spelling and try again :)\n";
   o1.close();
   i1.close();
}


void customer()
{
   int custch;
   clrscr();
   cout<<"Welcome, Customer!\n";
  	cout<<"\n1. View Catalogue";
  	cout<<"\n2. Place Order";
  	cout<<"\n3. Back to Main Menu";
   cout<<"\n\nEnter Choice\n";
   cin>>custch;
   switch(custch)
   {
   	case 1: catalogue();
         	  break;
      case 2: order();
         	  break;
      case 3: break;
      default: cout<<"\a";
   }
}

void modify()
{
   clrscr();
   int prodid;
   cout<<"\nEnter Product ID of product you want to modify\n";
   cin>>prodid;
   ofstream o1;
   o1.open("r2.dat",ios::binary|ios::ate);
   o1.seekp((prodid-1)*sizeof(p1), ios::beg);
   p1.pcreate();
   o1.write((char*)&p1,sizeof(p1));
   o1.close();
   cout<<"Record modified successfully\n";
   o1.close();
   getch();
}

void deleteprod()
{
	clrscr();
   int prodid;
   cout<<"\nEnter Product ID of product you want to delete\n";
   cin>>prodid;
   int flag=0;
   ifstream i1;
   ofstream o1;
   i1.open("r2.dat",ios::binary);
   o1.open("r3.dat",ios::binary);
   while (i1.read((char*)&p1,sizeof(p1)))
   {
   	if (p1.retpid()!=prodid)
      {
      	o1.write((char*)&p1,sizeof(p1));
         flag=1;
      }
      if (p1.retpid()==prodid)
      {
      	cout<<"Deleted Record is: \n";
         p1.pdisp();
      }
   }
   i1.close();
   o1.close();
   remove("r2.dat");
   rename("r3.dat","r2.dat");
   if (flag==0)
   	cout<<"Product not found. Are you sure you've got the right ID? Please check and try again\n";
   getch();
}

void create()
{
   clrscr();
   ofstream o1;
   o1.open("r2.dat",ios::binary|ios::app);
   char addrec;
   do
   {
   	p1.pcreate();
      o1.write((char*)&p1, sizeof(p1));
      cout<<"\nTo add another record, enter y. Else, n\n\n";
   	cin>>addrec;
   }
   while (addrec=='y');
   o1.close();
   cout<<"\n\nProduct(s) created successfully\n";
   getch();
}

void admin()
{
   int adminch;
   clrscr();
	cout<<"\nA.D.M.I.N. M.E.N.U.";
   cout<<"\n1. View Catalogue";
   cout<<"\n2. Create Product";
   cout<<"\n3. Modify Product";
   cout<<"\n4. Delete Product";
   cout<<"\n5. Back to Menu";
   cout<<"\n\nEnter Choice\n";
   cin>>adminch;
   switch(adminch)
   {
      case 1: catalogue();
      		  break;
   	case 2: create();
      		  break;
      case 3: modify();
      		  break;
      case 4: deleteprod();
      		  break;
      case 5: break;
      default: cout<<"\a";
   }
}

void main()
{
	int ch;
   wlc_screen();
   do
   {
   	menu();
      cout<<"\nEnter Choice\n";
      cin>>ch;
      switch(ch)
      {
      	case 1: about();
         		  break;
         case 2: customer();
         		  break;
         case 3: admin();
         		  break;
         case 4: exit(0);
         default: cout<<"\a";
      }
   }
   while (ch!='4');
	getch();
}


