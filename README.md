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
三、查看类模板的类型
  用typeid().函数来查看类型
  例如查看T1中的类型：
  typeid(T1).name()
