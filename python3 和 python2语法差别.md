### 1

1. python3 中   3/2  结果为 1.5   python3 中 整数除以整数即便可以整除结果仍然为浮点数   ，python2 中   3/2   结果为 1 ，3.0/2  结果 为 1.5

2. python3 使用 input函数获得用户输入，python2 使用raw_input函数获得用户输入，将input函数的输入解读为python代码。

3. python3 创建类  class Create():      python2 创建类  class Create(object):

4. python中继承 

   ~~~python
   # python2
   class Parent_2(object):
       def __init__(self,age):
           self.age=age
         
    class Son_2(Parent_2):
       def __init__(self,age,name):
           super(Son_2,self).__init__(age) 
           self.name=name
    # pthon3
   class Parent_3():
       def __init__(self,age):
           self.age=age
           
   class Son_3(Parent_3):
        def __init__(self,name,age):
           super().__init__(age)
           self.name=name
   ~~~

   

