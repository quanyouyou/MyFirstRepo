## 输入input
```
 a = input("请输入一个数字:") // 这时候接受的数字是以字符的形式存在的
 b = int(input("请输入一个数字:")) // 使用强制转换能让它变成整型
```
## 循环while for
```
for i in range(1,5) //1 2 3 4 左闭右开
range(1 , 6 ,step = 2） //1 3 5 step表示步幅
```

## 判断if elif else
类比C语言就完事儿了

## 定义函数def
### 不含参数
```
#定义函数
def function():
  print("this is a function!")

#调用函数
function() //输出: this is a function
```
### 包含参数
```
#definition
def function(a,b):
  print("use the function : %d + %d = %d" % (a, b, a + b))
#call
a = 3
b = 4
function(a,b)
```
<font color=red> **print("use the function : %d + %d = %d" % (a, b, a + b))** 这一块很重要！！！！</font>

### 函数的默认参数值
```
def car(brand,type,price,is_qualified = True): #默认一台车是合格的
    print("the brand of the car is : ",brand,
          "\nthe type of the car is : ",type,
          "\nthe price of the car is : ",price,
          "\nis the car qualified : ",is_qualified)

car("BMW","XHW2300",45000)
car("BMW","XHW2300",45000,False) 

# the brand of the car is :  BMW
# the type of the car is :  XHW2300
# the price of the car is :  45000
# is the car qualified :  True
# the brand of the car is :  BMW
# the type of the car is :  XHW2300
# the price of the car is :  45000
# is the car qualified :  False

```
## 类class
```
class Calculator: #一般习惯来讲 类的首字母要大小
    type = "casio"
    price = 128
    def print_info(self):
        print("the type of the calculator is ",self.type)
        print("the price of the calculator is ",self.price)
    def add(self,a,b): #要在类里面的参数中第一个加入self
        result =  a + b
        print(result)
    def minus(self,a,b):
        result = a - b
        print(result)
    def times(self,a,b):
        result =  a * b
        print(result)
    def divide(self,a,b):
        result = a / b
        print(result)

cal = Calculator()
cal.print_info()
# the type of the calculator is  casio
# the price of the calculator is  128
cal.add(4,5)

cal2 = Calculator()
cal2.type = 'romoss'
cal2.price = 256
cal2.print_info()
# the type of the calculator is  romoss
# the price of the calculator is  256
```

- 类中定义的函数括号内第一个永远是**self**
- 类中的函数在使用类中的变量时要加前缀self
- 注意声明类的方式 **cal = Calculator()**

## 类init 初始
使用initial就可以在声明一个类变量的时候在括号内输入默认值
```
class Calculator: #一般习惯来讲 类的首字母要大小

    def __init__(self,name,price,height,width,weight):#代表着类它自己的功能
        self.name = name
        self.price  = price
        self.h = height
        self.w = width
        self.we = weight

cal = Calculator("casio",128,12,12,12) #<--------
```




