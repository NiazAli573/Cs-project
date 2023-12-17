# Cs-project
#include <iostream>
#include <string>
#include <vector>
#include <fstream>
using namespace std;

void data_display(vector<string> name, vector<int> reg_no, vector<string> faculty, vector<string> contact_no){
    
    cout<<endl;
    for(int i = 0; i < 26; i++){
            cout<<char(178);
        }
        cout<<endl;    
        
    for(int i = 0; i < name.size(); i++){
        cout<<"Student Name "<<i+1<<" : "<<name[i]<<endl;
        cout<<"Registration # "<<" "<<reg_no[i]<<endl;
        cout<<"Faculty : "<<faculty[i]<<endl;
        cout<<"Contact no : "<<contact_no[i]<<endl;
        for(int i = 0; i < 26; i++){
            cout<<char(178);
        }
        cout<<endl;

    }    
}

int main(){
    char save;
    int choice;
    int size;
    vector<string> name;
    vector<int> reg_no;
    vector<string> faculty;
    vector<string> contact_no;

    initialisation(name, reg_no, faculty, contact_no);

do{
    cout<<endl;
    cout<<"*****************STUDENT MANAGEMENT SYSTEM***************\n\n";
    cout<<"1. Data Entry \n";
    cout<<"2. Data display \n";
    cout<<"3. Search and Update \n";
    cout<<"4. Delete student record \n";
    cout<<"5. Exit and Save Changes \n\n";

    cout<<"Enter function : \n";
    cin>>choice;
    
    switch(choice){
        case 1:
           enter_data(name, reg_no, faculty, contact_no);
        break;

        case 2 :
           data_display(name, reg_no, faculty, contact_no);
           break;

        case 3:
           update_data(name, reg_no, faculty, contact_no);
           break;

        case 4:
           del(name, reg_no, faculty, contact_no);
           break;

        case 5:
           break;
              
        default:
           cout<<"Invalid Function!\n";  
    }

}while(choice != 5);
cout<<endl;

cout<<"Do you want to save the changes (y/n) : \n";
cin>>save;
save = toupper(save);
cout<<endl;

if(save == 'Y'){
    record_updation(name, reg_no, faculty, contact_no);
    cout<<"Changes saved succesfully!\n";
}
cout<<endl;
cout<<"************SAYONARA**************\n";  
}

