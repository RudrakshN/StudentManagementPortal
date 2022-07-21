#include <bits/stdc++.h>
using namespace std;

//Node Class 

class node
{

public:
	int Roll_Number ;
	string Name ;
	string Department ;
	int Marks_Obtained ;
	node* next ;

};

node* head = new node() ;

//Function to check if the roll number already exists 

bool check(int x)
{
	//checking for existance of list 
	if(head==NULL)
	  return false;

	node *t = new node ;
	t = head ;

	//traversing the linked list 

	while(t!=NULL)
	{
		if(t->Roll_Number==x)
		  return true;
		t = t->next;  
	}  
	
	return false;
}

//Insertion of a new record 

void Insert_Record(int Roll_Number , string Name , string Department , int Marks)
{
	//if Record Already Exists 
	if(check(Roll_Number))
	{
		cout<<"Student with this"<<"record already exists"<<endl; 
		return ;
	}

	//create new node to insert record 
	node* t =new node();
	t->Roll_Number = Roll_Number ;
	t->Name = Name ;
	t->Department = Department ;
	t->Marks_Obtained = Marks ;
	t->next = NULL ;

	//inserting at the beginning 

	if(head == NULL||head->Roll_Number>=t->Roll_Number)
	{
		t->next = head ;
		head = t ;
	}

	//inserting in the middle or end 

	else
	{
		node *p = head ;
		while(p->next!=NULL && p->next->Roll_Number < t->Roll_Number)
        {
			p = p->next ;
		}
		t->next = p->next ;
		p->next = t ;  	
	}

	cout<<"Record Inserted Successfully"<<endl;

}

//Function to search record for any 
//students Record with Roll Number 

void Search_Record(int roll)
{
	//if head is null 
	if(!head)
	{
		cout<<"No such record available"<<endl;
		return ;
	}

	//otherwise
	else
	{
	    node * m = head ;
		while(m)
		{
			if(m->Roll_Number == roll)
			{
				cout << "Roll Number\t"
                     << m->Roll_Number<< endl;
                cout << "Name\t\t"
                     << m->Name << endl;
                cout << "Department\t"
                     << m->Department << endl;
                cout << "Marks\t\t"
                     << m->Marks_Obtained << endl;
                return;
			}
			m = m->next ;
		}

		if(m==NULL)
		  cout << "No such Record Available" <<endl ;
                 
	}
}

//Function to delete record of a student with a given 
//Roll Number if it exists 

int Delete_Record(int roll)
{
	node* t = head ;
	node* p = NULL ;

	//Deletion at Beginning 
	if(t!=NULL && t->Roll_Number == roll)
	{
		head = t->next ;
		delete t ;

		cout<< "Record Deleted Successfully"<<endl;

		return 0 ;
    }

	//Deletion other than at beginning 
	while(t!=NULL && t->Roll_Number != roll)
	{
		p = t ;
		t = t->next;
    }
	if(t == NULL)
	{
		cout << "Record does not Exist\n";
        return -1;
	}
	p->next = t->next ;
	delete t ;

	cout << "Record Deleted Successfully" <<endl;
    return 0;         
 
   

}

//Function to Display All the Student's Record 

void Show_Record()
{
    node* p = head ;
	if(p == NULL)
	{
		cout<<"No Record Available"<<endl;
	}
	else
	{
		cout << "Index\tName\tCourse\tMarks"<<endl;
        
		//till all students have been printed
		while(p != NULL)
		{
			cout<< p->Roll_Number <<"  \t"
			    << p->Name <<"\t"
				<< p->Department << "\t"
                << p->Marks_Obtained << endl;
            p = p->next;
		}
             
 
	}
}

//Driver Code

int main()
{
	head = NULL ;
	string Name , Course ;
	int Roll , Marks ;

	//Menu Driven Program 
	while(true)
	{
		cout<<"\n\t\t Welcome to Student Record Management System\n\n\tPress\n\t"
		      "1 to create a new Record\n\t"
		      "2 to delete a student record\n\t"
			  "3 to search a Student Record\n\t"
			  "4 to view all students record\n\t"
			  "5 to exit\n";

		cout<<"\nEnter your Choice\n";
		int choice ;

		//Enter Choice 

		cin>>choice ;

		if(choice == 1)
		{
			cout << "Enter Name of Student\n";
            cin >> Name;
            cout << "Enter Roll Number of Student\n";
            cin >> Roll;
            cout << "Enter Course of Student \n";
            cin >> Course;
            cout << "Enter Total Marks of Student\n";
            cin >> Marks;
            Insert_Record(Roll, Name, Course, Marks);
		}

		else if(choice == 2)
		{
			cout<< "Enter Roll Number of Student whose record is to be deleted\n";
			cin >> Roll ;
			Delete_Record(Roll);
		}

		else if(choice == 3)
		{
			cout << "Enter Roll Number of Student whose record you want to Search\n";
			cin>>Roll;
			Search_Record(Roll);
		}
        
		else if(choice == 4)
		{
			Show_Record();
		}

		else if(choice == 5)
		{
			exit(0);
		}

		else
		{
			cout<<"Invalid Choice Try Again\n" ;
		}
		}

		return 0;	  
	}


