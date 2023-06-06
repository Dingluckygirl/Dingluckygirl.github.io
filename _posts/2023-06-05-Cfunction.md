# 3 函数提高
# 3.1 函数默认参数
语法：函数返回类型 函数名（参数 = 默认值）{}

形参可以给默认值

1、 如果某个位置已经有了默认参数，那么从这个位置往后，就必须都有默认值

2、 如果函数声明有默认参数了，函数实现就不能有默认参数了。（声明和实现只能有一个默认参数）

    int func(int a, int b = 20 ,int c = 30){
        return a+b+c;
    }
    int main(){
        cout << func(10) << endl;
        system ("pause");
        return 0 
    }
 
# 3.2 函数占位参数
语法：函数返回类型 函数名（数据类型）{}

    void func(int a, int){}

    //调用  要写一个int类型的数传进去，虽然目前这个10用不上
    func(20，10){}
    
占位参数还可以有默认参数，这样调用的时候就不用写10了

    void func(int a, int = 10){}


# 3.2 函数重载
3.3.1 函数重载概述

作用：函数名可以相同，提高复用性

条件：同一个作用域下；

函数名相同；

函数参数  类型不同  或者  个数不同  或者 顺序不同；

注意：函数的返回值不可以作为函数重载的条件

    # include <iostream>
    using namespace std;
    
    void func()
    {   
        cout << "func调用" << endl;    
    } 
    
    void func(int a)
    {   
        cout << "func(int a)的调用" << endl;    
    } 
    
    void func(double a)  //void 改为int  不能发生重载
    {   
        cout << "func(int a)的调用" << endl;    
    } 
    
    int main()
    {
        func();  // 会调用上面的函数
        func(10);  //调用下面的 
        func(3.14); //调用第三个的 
    }

3.3.1 函数重载注意事项
引用作为重载条件

函数重载碰到默认参数
