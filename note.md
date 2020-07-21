### 一  python3  

1. python 跨平台，解释型语言

2. python 中定义变量时，慎用 l 和 o ，容易被当作 1 和 0

3. python中字符串既可以是单引号也可以是双引号

4.  字符串 :  进行一下方法字符串本身并不发生变化
   1.  title() 首字母大写
   2. upper() 全变为大写
   3. lower()  全变为小写
   4. strip()  除去两端空白
   5. lstrip()除去左边空白
   6. rstrip()除去右边空白
   7.  split() 以空格为分隔符，返回一个列表
   
5. 数值
   1. 整数  ** 表示 乘方 ，即 3**4 为81
   2. 将 数值和字符串进行拼接时，需要使用str(数值) 将数值转为字符串。
   3. **python3 中   3/2  结果为 1.5   python3 中 整数除以整数即便可以整除结果仍然为浮点数   ，python2 中   3/2   结果为 1 ，3.0/2  结果 为 1.5**
   4. % 求模运算符
   
6. 注释   **#** 后面的内容为注释

#### 7.列表

   1. python中列表用  **[ ] ** 表示，并用逗号来分隔其中的元素 。message = [ "0","test1" ,"test2"]，**以下 message均表示该列表**
   
   2. message[0]  获得 message中的第一个元素
   
   3. python中的索引从**0**开始 ， 如果想要获得最后一个元素 可以指定索引为 -1，以此类推得到 倒数第二个元素 可以指定索引为-2。**无论是负数索引，还是正数索引，只要该索引相应位置没有元素就会包 索引越界异常**
   
   4. 修改列表  ：**除非特别指明，否则以下修改操作都会修改原列表本身**
      - message[0] = " 修改 0 号的值 "
      - message.append(" 向列表末尾添加一个值 ")
      - message.insert(0,"  将元素插入到 0号索引处，其他元素后移一个位置")
      - del  message[2]    删除指定位置处的元素，**被删除的元素不会返回**
      - last_element =  message.pop() 删除末尾的元素**并将其 返回,** 也可以在pop方法中指定索引弹出指定位置处的元素。  second_element = message.pop(1)    
      - message.remove("test1")  ,将 message列表中的test1元素删除， ！！！remove方法无返回值， 除此之外 如果列表中有多个 元素与指定的元素相同，那么  remove方法只会删除第一个符合条件的元素。
      - message.sort() ,使用sort方法 对列表进行从小到大进行排序，也可以使用 message.sort(reverse=**True**) 从大到小进行排序 。 sort会改变列表本身里面的元素的排列顺序
      -  temp = sorted(message) ，sorted方法会将列表中的元素按照从小到大进行排列然后返回一个新的列表，**原列表不会发生改变**。temp =  sorted(message,reverse=True) 从大到小排列
      - message.reverse() ， reverse 方法将会使得列表中元素的位置发生反转，即第一个元素将会变为最后一个元素
      - len(message) , len 方法会返回指定列表的长度
      
   5. 操作列表
   
      1. 遍历
      
         ~~~python
         # 使用for 元素变量  in  列表变量 :  , 实现对列表的遍历,
         # !!!! 不要忘记在列表变量后加冒号
         for  message_element in message: 
          	print(message_element)
         
          # range函数 range(begin,end+1),range函数可以产生一些列的数字， 从 begin到end
          # 1,2,3,4,5 ， ！！begin如果省略，则表示begin为 0
          # test_rt_value = range(1,6) ,test_rt_value 为 'range(1,6)'
         for value in range( 1, 6):
             print(value)
          
          #list函数，mylist = list(range(1,6)) 将 range(1,6)作为参数传给 list函数从而
          # 得到一个 [1,2,3,4,5] 的列表。  
          
          # 调用range函数时指定步长，  1,3,5
         for value in range(1,7,2): # beign 不断地加 step，直至大于或等于end时停止
         	print(value) # value 小于 end，
          
         ~~~
      
      2. 计算
      
         ~~~python
          # min函数，min_value =  min(mylist) 计算列表中的最小值，
          # max函数, max_value = max(mylist) 计算列表中的最大值
          # sum函数，total = sum(mylist)  计算列表中各个元素的总和
         mylist = [1,2,4,5,2,6]
         min_value = min(mylist)  # min_value = 1
         max_value = max(mylist)  # max_value = 6
         total = sum(mylist)  # total = 20
         
         ~~~
      
      3. 列表解析
      
         ~~~python
         # 通过列表解析创建一个列表
         mylist = [value**2 for value in range(1,6)]
         print(mylist) # [1, 4, 9, 16, 25]
         ~~~
      
      4. 使用列表的一部分 ： 切片
      
         ~~~python
         #创建 切片 ，通过 mylist[start : end +1] ,获得从start到end位置处的元素组成的列表
         # 省去 start ，则从 0 位置处开始，省去 end+1 ，则到 列表的最后一个元素结束
         # start 和 end 也可以为负数 ，当为负数时相当于从后往前数 ，-1 为最后一个元素
         mylist = [1,2,3,4,5,6]
         slice_list =  mylist[1 : 5]  # slice_list = [2,3,4,5]
         slice_list = mylist[ : 5]  # 0,1,2,3,4
         slice_list = mylist[1 : ] #[2,3,4,5,6]
         
         slice_list = mylist[5:1]  #[]
         slice_list = mylist[111 : 1] #[]
         slice_list = [1:111] #[2,3,4,5,6]
         
         slice_list = mylist[ : ]  #！！复制切片 [1,2,3,4,5,6]，slice_list 和 mylist关联的不是同一个列表
         
         same_list = mylist  # same_list 和 mylist 关联到同一个列表
         same_list.append("列表中元素类型可以不同") # mylist关联的列表同样会增加该元素
         
         slice_list = mylist[-2 : ] #[5,6]
         slice_list = mylist[-3 : -1] #[4,5]
         
         slice_list = mylist[-1 : -3 ] #[]
         #  ====> 只有 当 start  到 end+1 之间有元素时 
         # 才会将 start 至 end 所对应的元素组成列表返回， 
         # 在创建切片时 索引越界不会报错
         #---------------------------------->
         
         #遍历切片
         mylist = [0,1,2,3,4]
         for temp in mylist[ :3]:
             print(temp)  # 将 依次得到 0,1,2
             
          
         	
         ~~~
      
      5. 元组：不可变的列表 **这里的不可变，仅仅指 变量关联的元组中的元素不能变，但可以给关联元组的变量重新赋值**
      
         ~~~python
         #使用() 而不是  [ ] 来创建一个元组， 使用[] 来访问元组中的数据
         constants  = (1,2,3)
         print(constants[0]) # 1
         constants[1]=111 # 报错
         constants = (3,4,5) # constants 变为  (3,4,5)
         #遍历元组 
         for constant in constants
         	print(constant)
          
         ~~~

#### 8.if语句

   1. 语法

      ~~~python
      age = 1
      if age>3:   #  不要忘记 冒号 : 
          print("age 》3")
      else:       #  不要忘记 冒号 : 
          print("age<3")
      #------------
      
      if age >3:
         print("age>3")
      elif age>2:
          print("age>2")
       else:
          print("age<2")
      ~~~

   2. 关系运算符 

      ~~~
      > ,  <  , >= ,<= , == , !=
      ~~~

   3. 逻辑运算符  and  ，or

   4.  in  ，关键字，检查 一个元素 是否在列表中。  not   in   检查 一个元素是否不在列表中

      ~~~python
      mylist = [2,4,6,3,5]
      if 999 not in mylist:
      	print("999不在列表中")
      if 2 in mylist :
          print("2 在列表中")
      ~~~

   5. **if  ,      if-else     ,    if-elif-else   ,     if-elif-elif    **

   6. 当一个没有任何元素的列表作为条件表达式时将返回False，否则 返回 True

      **python 将 非0数字，非空字符串，非空列表解读为True，None 为False**
      
      ~~~python
      mylist = []
      if mylist:
      	print("mylist 中含有元素")
      else :
      	print(" mylist 中没有元素")
      ~~~

#### 9.字典

   1. 创建字典，添加，删除，修改字典中的信息
   
      ~~~python
      # 创建（类似于JS中的JSON对象)
      	# 创建一个 空字典
      my_empty_dictionary = {} 
      	# 字典中的信息以键值对的形式存储，键是一个字符串，值则可以数字，字符串，甚至字典类型
      my_dictionary = {'name':'非空字典','age':111} 
      
      #访问及添加
      my_name = my_dictionary['name'] # 访问字典中的元素
      my_dictionary['name'] = '修改'  # 修改字典中元素的值
      my_dictionary['add'] = '添加'   # 向列表中添加元素
      
      #删除
      del my_dictionary['name']	    # 删除字典中指定的键值对
      ~~~
   
   2. 遍历字典(遍历顺序和存储顺序不一定相同)
   
      ~~~python
      #遍历字典中所有的键值对
      for key,value in my_dictionary: # key，value 表示键，值，当然也可以使用其他变量名代替
          print(key,value)
          
      #调用字典变量的keys方法获得由字典中所有的键组成的列表，从而实现遍历
      for key in my_dictionary.keys():
          print(key,my_dictionary[key])
          #遍历字典时会默认遍历字典中所有的键
      for key in my_dictionary:
          print(key)
          #使用 sorted方法按照顺序遍历字典中所有的键
       for key in sorted(my_dictionary.keys()):
          print(key)
       
      #调用字典变量的values方法得到由字典中所有的value组成的列表。！！列表中可以由重复元素
      for value in my_dictionary.values():
          print(value)
      	#调用set方法获得没有重复元素的set集合
      for value in set(my_dictionary.values()):
          print(value)
          
       
      ~~~
   
   3. 嵌套 ：字典中的列表，列表中的字典，字典中的字典
   
      ~~~python
      #字典列表:由字典组成的列表
      dictionary_1 = {
          'name' : 'dic1'
      }
      dictionary_2 = {
          'name' : 'dic2'
      }
      dic_list = [dictionary_1,dictionary_2] # 字典列表
      dic_dynamic_list = []
      for num in range(0,30):
          new_dic = {'name' : 'dic'+str(num+2)}
          dic_dynamic_list.append(new_dic)  #动态的向列表中添加字典
      
      #将列表存储在字典中
      list_1 = ['1','tet']
      dic_li = {'list':list_1,age:33}
      
      #字典中存储字典 
      users = {
          'user1':{
              'age':33,
          },
          'user2':{
              'age':44
          }
      }
      
      ~~~

#### 10.用户输入和while循环

1. 用户输入 :  input函数

   ~~~python
   #input函数，通过调用input函数得到用户输入的信息，返回值是字符串
   message = input("提示信息，输入名字: ") 
   print(message)
   #int函数将数字字符串变为数字， float将字符串转为浮点数
   age = int('88')
   ~~~

2. while循环

   ~~~python
   #语法
   num=0
   while num<5:
       num+=1
       
   # break 关键字
   while num<9:
       if num == 8:
           break
       else:
           print(num)
    #countinue 关键字
   while num<9:
       if num == 8:
           continue
        else:
           print(num)
   ~~~

#### 11.函数

1. 定义函数

   ~~~python
   # def关键字,使用def关键字定义一个函数 ，使用三对引号""""""添加文档字符串
   # 文档字符串是一种注释，它可以生成函数的文档
   #  函数名 最好全是小写字母组成，不同单词之间用下划线隔开
   
   #无参函数
   def my_function():  
      """定义一个函数"""
   	print("my_function")
   	#调用函数
   my_function()
   
   #有参函数
   def my_function1(name):
       print(name)
       #调用有参函数
   my_function1("arg")
   ~~~

2. 传参：位置实参 ，关键字实参 ,  默认值

   ~~~python
   
   def my_function(ar1,arg2):
       print(arg1,arg2)
       
   # 位置实参 ： 实参与形参通过实参的位置进行关联
   my_function("arg1-1","arg2-2") # arg1="arg1-1" ,arg2="arg2-2"
   
   #关键字实参 ： 以键值对的形式进行传参
   my_function(arg2="arg2-2",arg1="arg1-1") # arg2="arg2-2" ,arg1="arg1-1"
   
   #默认值，在定义函数的时候如果给形参指定了默认值，那么在调用函数时如果不给形参传值，则形参的值为
   #定义函数时指定的默认值，为了让python能够准确识别  位置实参  ，有默认值得形参应该放在后面
   def default_value(arg1,arg2='arg222'):
       print(arg1,arg2)
   default_value("arg1---11")  # arg1 = 'arg1--11',arg2 = 'arg222'
   
   # 以下定义是错的
   def default_value(arg1=111,arg2): #含有默认值的形参必须放在后面
       print(arg1,arg2)
   ~~~

3. 返回值

   ~~~python
   # return关键字， 在函数中使用return关键字返回相应的结果，返回值可以是任意类型
   def test_return(name):
       print(name)
       return name.title()
   test_result = test_return('liu')# test_result = Liu
   print(test_result) 
   ~~~

4. 实参为 列表

   ~~~python
   # 可以将一个列表传给一个函数，此时形参和实参将关联到同一个列表,
   # 函数内部对列表的修改会同时导致原列表发生改变
   # 如果不想使得函数内部对列表的修改也会导致原列表发生改变，则可以使用切片 列表[ : ],向函数传递列表的副本
   my_list = ['test1','test2','test3']
   def list_arg(args):
      while args:
       arg = args.pop()
       print(arg)
   list_arg(my_list[:])
   print(my_list) #  ['test1','test2','test3']
   list_arg(my_list) 
   print(my_list) # []
   ~~~

5. 传递任意数量的实参

   ~~~python
   # 形参前面加一个*，使得该形参可以接收任意数量的 **位置实参**
   # ！！ 该形参最好放在形参列表最后，该种类的形参只能有一个， 该形参其实是一个元组
   
   def indeterminacy(arg1,*args): # args 可以接收任意数量的位置实参
       print(arg1,args)
   indeterminacy('test1') # test1 ()
   indeterminacy('test1','test2','test3') # test1 (test2,test3)
   # 如果 能够接收任意数量的实参的形参不放在 形参列表 的末尾 ，则在传值是需要对 该形参后面的形参传递关键字实参
   def  test(arg1,*args,arg2):
       print(arg1)
       print(args)
       print(arg2)
   test("arg1---arg1",'arg--s','arg--ss',arg2='arg2-2') # 必须这么传递实参 否则将会出错
   
   
   #在形参前面加两个*,使得形参可以接收任意数量的关键字实参，该形参会成为一个字典
   def keywords_arguments(arg1,*arg2,**arg3):
       print(arg1)
       print(arg2)
       print(arg3)
   # 此处 传递实参的时候，传参方式必须与定义函数时，形参列表的格式相对应
   # arg1
   # ('arg2-2', 'arg2-3', 'arg2-33')
   # {'name': 'arg3-3', 'age': 'arg3-4'}
   keywords_arguments('arg1','arg2-2','arg2-3','arg2-33',name='arg3-3',age='arg3-4')
   
   # 以下函数定义是错误的
   def error_format(arg1,**key_value_dictionary,arg2):
       print("这中定义是错误的")
   ~~~

6.  模块

   ~~~python
   # 1. import关键字，可以将函数存储在被称为模块的独立的文件中，然后在主程序中通过import将模块导入到主程序中.   **  如果文件没有注释对文件的进行描述，则import 语句应该放在文件开头 **
   	#创建 module_1.py
 def test_module_fun0(name):
       	print(name)
    def test_module_fun1(name):
       print(name)
    def test_module_fun2(name):
       print(name)
   	#创建主程序 main_program.py
    import module_1   #导入模块
    module_1.test_module_fun0("在主程序中调用模块中的方法")
       
   # 2. 使用 from 和 import 关键字，从指定的模块中导入指定的函数，由于指定了导入的函数，所以在调用函数时只需要使用函数名就可以调用函数，而不再需要使用 module_name.function_name(args) 的方式调用函数
   	#创建 main_program_1.py
   from module_1  import test_module_fun1 , test_module_fun2 # 函数名之间用逗号隔开
   test_module_fun1("导入指定的函数")
   
   # 3. 从指定模块中导入所有的函数，！！ 最后不要使用这种方式，因为当python遇到多个名称相同的函数或变量时会进行覆盖。
   from module_1 import *
   test_module_fun1("使用 import *  导入，所有模块中所有函数后，可以直接通过函数名调用函数")
   
   
   # 4. as关键字，使用 as 关键字 给函数起别名，从而解决函数名冲突 和 函数名过长的问题
   	#创建 main_program_2.py
   from module_1  import test_module_fun1 as m_fun1,test_module_fun2 as m_fun2
   m_fun1("使用as 给函数起别名， *** 之后调用该函数时必须使用该函数的别名 ****")
   
   # 5. as关键字，使用as关键字给模块起别名
   import module_1 as m_alias
   m_alias.test_module_fun1(" 使用 as 关键字 给模块起别名")
   ~~~

#### 12. 类

1. 定义类和使用类

   ~~~python
   # 1.class 关键字，创建类
   class Test():# 类的名字首字母大写，采用驼峰命名法
      # self 形参必须写 而且必须为是第一个形参，每个与类关联的方法在调用时都会自动传入实参self
      # self 指向当前被创建的实例，使得实例能够访问类的属性和方法
       
       def _init_(self,name1,age1):#__init__ 方法如果不写则默认为无参构造函数
           """初始化方法，python中的默认方法以**两个**下划线开始和结束 由python自动调用"""
           self.name=name1 
           # 为类增加两个属性 name，age，所有以self开头的变量，都可以被类中所有的方法使用
           self.age=age1
       def test_name(self):
           print("test_name")
           print(self.name,self.age)
           
   # 创建类的实例
   case_1 = Test('name-1','age1-1')
   case_1.test_name()
   ~~~

2. 继承

   ~~~python
   # 1. 在python 中 子类将继承父类所有的属性和方法。 语法 class Son(Parent): 
   class Test_Parent():
       def __init__(self,name):
           self.name=name
       def test_out(self):
           print(self.name)
   class Test_Son(Test_Parent):
       def __init__(self,age,name):
       # super(),  要带() ，该句不一定要放在首行，
       # 如果父类的__init__方法中没有属性要初始化，也可以不调用父类的该方法
           super().__init__(name)   
           self.age=age
       def test_son_out(self):
           super().test_out()    # super() ，要带()
           print("son"+self.age)  #self.age  要带 self
   son = Test_Son("33","ssss")
   son.test_son_out()
   son.test_out()
   ~~~

3. 重写父类的方法

   ~~~python
   class Parent():
       def __init__(self):#  如果该类没有属性要初始化，则可以省略该方法
           print("parent")
       def test(self,age):
           print("parent  "+ age)
   class Son(Parent):
       def __init__(self):
          # super().__init__(); 父类的该方法没有属性要初始化，所以可以不调用父类的该方法
           print("son")
       def test(self): # 重写父类的方法
           print("son")
   s = Son()
   s.test() # 该子类将调用自己的test方法
   ~~~

4. 导入类

   ~~~python
   # 导入类
   	#创建 module_1.py
      """此处为文档字符串描述该文件的功能 ： 创建一个文件"""
    class Test_import_class():
       def __init__(self):
           print("该module_1.py 只用来定义类")
     class Test_import_2():
       def __init__(self):
           print("该模块中的两个类")
           
        #创建 main_program.py
     from module_1 import Test_import_class  #导入单个类，如果导入多个类，则类名之间用逗号隔开。
     test = Test_import_class()  
     
     # 导入整个模块
   import module_1  # 导入整个模块
   test = module_1.Test_import_class(); # 如果是导入整个模块那么在使用类时，需要在使用句点表示法
   
   # 导入所有类的语法  from module_name import *
   ~~~

5. 在模块中导入模块

   ~~~python
     # m_1
     class Car():
       def __init__(self,age):
           print("car--car")
           self.age=age
       def test(self):
           print(self.age)
    # m_2
   from m_1 import Car
   class Scar(Car):
       def __init__(self,age,name):
           super().__init__(name)
           self.age=age
   
       def test(self):
           print(self.age)
   # m_3
   from m_2 import Scar   # 如果该模块需要使用 Car，则还需要导入 m_1
   sc = Scar("age",'dfdf')
   sc.test()
   ~~~

####  13. 文件和异常

1.  从文件中读取数据

   ~~~python
   # with 关键字，保证在文件不再使用时，关闭文件
   # open方法 可以打开文件，  使用with关键字保证文件在不需要时有python关闭文件，而不宜使用close方法关闭文件，是因为程序在执行过程中可能会遇到异常从而到值close方法不能被调用
   #文件路径 ：可以输入相对路径或绝对路径 ， 在Linux中路径分隔符是 /  , 在windows下 pycharm IDE 中是 \ 或 /
   with  open('filename.txt') as file_object: # 文件对象，file_object 只能在with关键字内部使用
       content = file_object.read(); # read方法将读取文件中所有的内容，当到达文件末尾是会返回一个空字符，可以使用rstrip方法去掉该空字符
       print(content.rstrip())
       
   # 逐行读取
   with open('filename.txt') as fileObject:
       for line in fileObect: # 读取文件的时候每一行末尾都有一个换行符，可以使用rstrip方法去掉该换行符
           print(line.rstrip())  #读取文件中的每一行
   
    # 返回一个列表
   with open('filename.txt') as file_object:
   # 由于file_object 文件对象只能在with 代码块内部使用，所以可以在文件代码块内部将文件的内容存入一个列表中，然后在 with 代码块外部使用 该列表
       lines = file_object.readlines() 
   for line in lines:
       print(line)
       
   # 切片 也可以用于字符串 
   message = "123456789"
   print(message[:7])
   for i in message:
       print(i)
   ~~~

2. 写入文件

   ~~~python
   # open方法打开一个文件时如果不指定权限参数那么将以只读的方式打开文件。
   # r 只读，w 只写，a 附加模式 会向文件中添加数据，而不会在返回文件对象前，清空数据。 r+ 读写
   # w  只写，如果文件不存在则创建该文件，如果文件已存在则清空文件中的内容
   with open('my_write.txt' ,'w') as file_object: # 向文件中输入一行数据
       file_object.write("向文件按中写入数据")
       file_object.write("只能向文件中写入字符串")
       file_object.write("如果是数值数据，则需要使用str函数将数值数据转换为字符串")
       
   # 向文件中输入多行数据
   with open('my_write.txt' ,'w') as file_object:
       file_object.write("向文件按中写入数据\n")
       file_object.write("只能向文件中写入字符串\n")
       file_object.write("如果是数值数据，则需要使用str函数将数值数据转换为字符串")
       
   # 采用 附加模式向文件中添加数据，如果文件不存在则会创建该文件
   with open('my_write.txt','a') as file_object:
       file_object.write("\n添加数据")
   
   ~~~

3. 异常

   ~~~python
   # python 使用 try-except 代码块处理异常
   
   # ZeroDivisionError  除零异常  5/0
   try: 
       print("try--try")
       me = 4/0
   except ZeroDivisionError:
       print("除零异常")
       
   # 结合 else
   try: 
       print("try--try")
       me = 4/0
   except ZeroDivisionError:
       print("除零异常")
   else:
       print("只有try中没有错误时，才会执行该句代码")
       print("如果不加 else 那么 无论 try 中是否发生错误都会执行该句代码 ")
       
   
    # FileNotFoundError
   file_name = 'my_writess.txt'
   try:
       with open(file_name) as file_object:
           message = file_object.read()
   except FileNotFoundError:
       print("文件没找到")
   else: print(message)
       
    # 出错时一声不吭
    # pass 语句，告诉python在出错时不要做任何处理
      
   try:
       mes = 4/0
   except ZeroDivisionError:
       pass #当发生除零错误时，python什么也不会做
   else:
       print("正常")
   ~~~

4. 存储数据

   ~~~python
   # 使用python中的json模块来存储数据
   # json.dump方法来存储数据
   import json
   my_list = ['43','e','rrr']
   file_name = 'store.txt'
   with open(file_name,'w') as file_object:
       json.dump(my_list,file_object)  # dump方法需要两个参数
    
   #json.load方法读取数据，                               
   import json  # 不要忘记导入 json 模块
   with open(file_name) as file_object:
       message = json.load(file_object)
       print(message)
   ~~~

   



