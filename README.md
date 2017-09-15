# assn2
ShaunMicheal Bartschi

1. Excerise 2 from the Textbook:
(f(x0+h)-f(x0-h))/ (2*h)
Since this function is an approximation of the Taylor series, the error is equivalent to the expansion of terms that we neglected to include.
Thus, when f'''(x0) doesn't =0, the leading term of the error must be -h^2/6f'''(x0).

2. Given that the derivative of the function is 4/((e^(-x) + e^x)^2), as x is near zero, the conditioning of the problem is relatively small as the derivative at 0 is 1 when c=1. As c grows however, the derivative at 0 is c, and thus becomes more ill-conditioned the larger it becomes.

3. Incomplete:
a)y_(n-1) = y_n(1) - y_n(0)
b)
c)
d)

4. Implementing the bisection method:

The following algorithm assumes that 'f' is the hardcoded function with takes a real input and delivers a real output
```C++
    double bisect(double a, double b, double tol, int maxIters){
      double error = 10.0*tol;
      fa=f(a);
      fb=f(b);
      if(fa*fb>0){
        std::cout<<"Error"<<std::endl;
      }
      int cnt = 0;
      int c; int fc;
      while(error>tol && cnt<maxIters){
        c=0.5*(a+b);
        fc=f(c);
        if(fa*fc)<0){
          b=c;
          fb=fc;
        }else{
          a=c;
          fa=fc;
        }
        error=b-a;
        cnt++;
      }
      return c;
    }
```
