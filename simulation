#include <iostream>
#include <iomanip>
#include <cmath> 
#include <cstring> 
#include <cctype>
#include<stdio.h> 
#include<stdlib.h> 
#include <queue>
#include<fstream>
#include <string>  
using namespace std;

//the functions that I used
string parseName(string line);
int parseNumber(string line);
int parseTime(string line);

int main(){
//this is where I initialize my queue
queue<string> myQueue;
//this is the variable for calculating my individual wait times
float waitTime=0;
//variable used for averaging out the customers
float customerCount=0;
//main while loop time calculation variable
int currentTime= 900;
//military time variable
int reach60=0;
int individualWaitTime;
//bool determaines when the store is open and closed
bool isopen= true;
//ends the loop
int leavestore=0;
//line of the text file
string test;
//reads in line from file
ifstream customers("line.txt");
//gets line from file
bool teller=false;


getline(customers, test);
//testing parse lines
// cout<<parseName(test) << endl;
// cout<<parseNumber(test) << endl;
// cout<<parseTime(test) << endl;
//the variable for the average time waited in line

     
     
   
  

int Time=999;
//////////////////////////////////////////////////

while(isopen==true){
    
if(currentTime==parseNumber(test)){
    if(myQueue.empty()==true){
    teller=true;
}
     cout<<parseName(test)<<" got in line at "<<currentTime<<"."<<endl;
     myQueue.push(test);
     getline(customers, test);
     
customerCount++;

}


 if(Time==0  && myQueue.empty()==false){
     
      cout<<parseName(myQueue.front())<<" is done at "<<currentTime<<"."<<endl;
      myQueue.pop();
      if(myQueue.empty()==false){
     teller=true;
      }
 }
 
 
 if(teller==true){
     Time= parseTime(myQueue.front());
    individualWaitTime= currentTime-parseNumber(myQueue.front()); 
     waitTime+=individualWaitTime;
    
     teller=false;
    //cout<<parseName(myQueue.front())<<"transaction time"<<Time<<endl;
}





Time--;
 currentTime++;
 
 if(currentTime>1700 &&myQueue.empty()==true){
 
     isopen=false;
     
     }
     reach60++;
 if(reach60==60 ){
    currentTime+=40;
    reach60=0;
}
 
     
      
 
 
 
}

float average=waitTime/customerCount;
    
         
    
     cout<<"Average wait time is "<<average<<" minutes."<<endl;
     
 
        
    //           if(customers==NULL){
    // cout<<"file does not exist"<<endl;
     
    //     }

return 0;

}

//this function is used to parse the names inside of the file
string parseName(string line){
    string temp;
    int index;
       temp =line; 
index= line.find(" ");
temp = line.substr(0,index);
    return temp;
    
}


//this function is used to parse the time that the individual enters into the store
int parseNumber(string line){
  int index;
  int convert;
  if(!line.empty()){
  
  string temp;
  index=line.find(" ");
  line.erase(0, index+1);
  index=line.find(" ");
  temp=line.substr(0,index);
  convert=stoi(temp);
  }
  return convert;


}


//this time is used to parse the amount of time the person spends with the teller
int parseTime(string line){
  int convert;
  int index;
  if(!line.empty()){
  index = line.find(" ");
  line.erase(0, index+1);
  index = line.find(" ");
  line.erase(0, index+1);
  
  convert=stoi(line);
  }
  return convert;
}
