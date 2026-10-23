# Browser-History-Management-Using-Stack
This C++ program implements browser history management using a stack data structure. It allows users to visit new web pages, navigate back by removing the current page, and display browsing history. The program demonstrates stack operations such as push and pop using an array, providing a simple menu-driven browser history simulation.
#include<iostream>
using namespace std;
class stack
{
    string page[10];
    int top;
public:
    stack()
    {
        top=-1;
    }
    void push(string);
    string pop();
    void display();
};
void stack::push(string value)
{
    top++;
    page[top]=value;
}
string stack::pop()
{
    string temp;

    if(top==-1)
    {
        cout<<"No history";
        exit(1);
    }

    temp=page[top];
    top--;

    return(temp);
}
void stack::display()
{
    int i;

    if(top==-1)
    {
        cout<<"No browser history";
        return;
    }

    cout<<"Browser history:";

    for(i=top;i>=0;i--)
    {
        cout<<"\n"<<page[i];
    }
}
int main()
{
    stack s;

    int ch;
    string page1,page2;

    do
    {
        cout<<"\n\n1.Visit page";
        cout<<"\n2.Back";
        cout<<"\n3.Display history";
        cout<<"\n4.Exit";

        cout<<"\nEnter your choice:";
        cin>>ch;

        switch(ch)
        {
            case 1:
                cout<<"Enter the page:";
                cin>>page1;

                s.push(page1);

                cout<<"Page visited";
                break;

            case 2:
                page2=s.pop();

                cout<<"Back from page:"<<page2;
                break;

            case 3:
                s.display();
                break;

            case 4:
                exit(0);
        }

    }while(ch!=4);
    return 0;
}
