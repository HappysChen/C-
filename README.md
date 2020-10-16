# C-
关于C++学习的笔记
1、类模板
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

模板的使用：有三种
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
