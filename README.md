1 задача. 
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
2 задача.
#include <iostream>
using namespace std;
int match(int n){
    if (n==1){
        return 0;} //если осталась одна команда, то раундов больше не будет =>0
    else{
        if (n%2==0){ //если n четное, то возвращаем количество матчей в которые будут + те, которые на этом раунде
            return match(n/2)+n/2; 
        }
        else{   //аналогично для нечетного количества команд, только формула другая 
            return match((n-1)/2+1)+(n-1)/2;
        }
    }
}
int main(){
    int n;
    cin>>n;
    cout<<match(n);
    system("pause");
    return 0;
}
 
2.1 задача
Заметим, что количество матчей всегда на 1 меньше, чем количество команд, поэтому задачу можно решить за O(1):

#include <iostream>
using namespace std;
int main(){
    int n;
    cin>>n;
    cout<<n-1;
    system("pause");
    return 0;
}



3 задача 
#include <iostream>
#include <string>
#include <vector>
using namespace std;
int main(){
    string s;
    getline(cin,s); //считываем строку целиком
    int len=0;
    for (int i=0;i<s.size();i++){ //перебираем по строку
        if (s[i]==' '){ //если слово заканчивается, то обнуляем счетчик
            len=0;
        }
        else{
            len++; 
        }
    }
    cout<<len; //выводим найденную длину посл слова
}   
 
4 задача 
#include <iostream>
#include <string>
#include <vector>
using namespace std;
int main(){
    int n,i=0; //i предполагаемый корень
    cin>>n;
    while (i*i<=n){  //пока i^2<=n равносильно условию i<=sqrt(n)
        i++;
    }
    cout<<i-1; //программа с предусловием делает один лишний заход в цикл, поэтому вычитаем единицу
}   
