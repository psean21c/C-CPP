
#

###
```cpp
#include <cmath>
#include <iostream>
#include <exception>
#include <stdexcept>
using namespace std;

// 

int main()
{
    Calculator myCalculator=Calculator();
    int T,n,p;
    cin>>T;
    while(T-->0){
      if(scanf("%d %d",&n,&p)==2){
         try{
               int ans=myCalculator.power(n,p);
               cout<<ans<<endl; 
         }
         catch(exception& e){
             cout<<e.what()<<endl;
         }
      }
    }
    
}
```

input
```
4
3 5
2 4
-1 -2
-1 3
```

output
```
243
16
n and p should be non-negative
n and p should be non-negative
```

---

```cpp
// My solution
class myexception: public exception{
  virtual const char* what() const throw() {
    return "n and p should be non-negative";
  }
} myex;

class Calculator{

public:
	Calculator(){}
	int power(int n,int p){
		if(n <0 or p<0) throw myex;
		int result = 1;
		for(int i=0;i<p;i++) {
			result *= n;
		}

		return result;
	}
};

// Other 1
struct negException : public exception 
    {
    const char* what() const throw()
        { return "n and p should be non-negative"; }
};

class Calculator
{
public:
    int power(int n, int p)
        {
        if (n < 0 || p < 0)
            {
            throw negException();
        }
        return pow(n, p);
    }
};

// Other-2
class Calculator
{
public:
    
    Calculator() // empty constructor
    {}
    
    int power(int n, int p)
    {
        if(n < 0 || p < 0)
            throw std::invalid_argument("n and p should be non-negative");
     
        return pow(n, p);
        
    }
};

```


