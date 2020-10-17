# C-
关于C++学习的笔记
一、类模板
语法：template<class typename>:例如：template<class T>
类模板在类中的使用：
template<class T>
class person
{
public:
  person(T& a,T& b);
private:
  T a; 
  T b;
}；
//构造函数的定义：
template<T>person::person(int A,string B)
{
  this->a=A;
  this->b=B;
}

二、模板的使用：有三种
1、指定类型传入
person<int ,string>P(17,"huan");
2、参数模板化
template<class T1,class T2>
void test(person<int,string>&p)
或者
void test(person<T1,T2>&p)
3、整个类模板化
template<class T>
void test(T&p)
三、查看类模板的类型(小知识点)
  用typeid().函数来查看类型
  例如查看T1中的类型：
  typeid(T1).name()
四、成员函数类外实现
  template<class T1,class T2>
  void person<T1,T2>::test()
  {}
五、类模板的分文件编写
  1、直接包含源文件（包含cpp）
  2、将.h和.cpp写在一起，文件后缀改为.hpp，使用时直接包含.hpp文件
六、类模板与友元
  友元在类模板中的实现，有两种：
  1、类内实现：
     直接在类内和public域之前声明和定义：
     例如：template<class T1,class T2>
           class person
           {
            friend void show(person<T1,T2>p)
            {
              //实现语句
             }
            public:
            private:
           };
  2、类外实现：
     类外实现要复杂些,例如：
     class person;
     template<class T1,class T2>
     friend void show2(person<T1,T2>p) //全局函数，不用加作用域
      {
              //实现语句
      }
     template<class T1,class T2>
     class person 
     {
      friend void show2(person<T1,T2>p);
      public:
      private:
     };
