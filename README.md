 
#include <iostream>

#include <string>

using namespace std; 

int main(){

    string amax = "-1";
    
    string a;
    
    cin >> a;
    
    for (int i = 1; i<a.size()-1; i++){
    
        if((a[i-1]==a[i])&&(a[i]==a[i+1])){ //ищем три одинаковых символа подряд
        
            string c;
            
            c = a[i];
            
            if (c>amax){    //если найдем новый максимум, то запоминаем его
            
                amax=c;
                
            }
            
        }
        
    }
    
    if (amax>="0"){  //проверяем найдена ли вообще подстрока вида "ххх"
    
        cout<<amax<<amax<<amax;
        
    }
    
    else{   //если подстроки нет, то сообщаем
    
        cout<<"not found\n";
    }
    system("pause");
    return 0;
} 

