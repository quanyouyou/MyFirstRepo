## 输入input

```py
 a = input("请输入一个数字:") // 这时候接受的数字是以字符的形式存在的
 b = int(input("请输入一个数字:")) // 使用强制转换能让它变成整型
 c = 5
 print(c**2) #prints 25 **就是^
```

## 循环while for

```python
for i in range(1,5) //1 2 3 4 左闭右开
range(1 , 6 ,step = 2） //1 3 5 step表示步幅
```

## 判断if elif else

类比C语言就完事儿了

## 定义函数def

### 不含参数

```python
#定义函数
def function():
  print("this is a function!")

#调用函数
function() //输出: this is a function
```

### 包含参数

```python
#definition
def function(a,b):
  print("use the function : %d + %d = %d" % (a, b, a + b))
#call
a = 3
b = 4
function(a,b)
```

<font color=red> print("use the function : %d + %d = %d" **% (a, b, a + b)**) 这一块很重要！！！！</font>

### 函数的默认参数值

```python
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

```python
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
- <font color = "red">注意声明类的方式 **cal = Calculator()** </font>

## 类init 初始

使用initial就可以在声明一个类变量的时候在括号内输入默认值

```python
class Calculator: #一般习惯来讲 类的首字母要大小

    def __init__(self,name,price,height,width,weight):#代表着类它自己的功能
        self.name = name
        self.price  = price
        self.h = height
        self.w = width
        self.we = weight

cal = Calculator("casio",128,12,12,12) #<--------
```

## container in Python 容器

### List列表

- **list可以使用反方向的索引**

```python
list = [1,3,5,7,9]
print(list,list[1]) # prints: [1,3,5,7,9] 3
print(list[-1]) #打印倒数第一个
```

- **list 可以同时包含不同类型的元素**

```python
list.append("hello") #append 直接在表尾添加一个新的元素
print(list) #prints:  [1,3,5,7,9,'hello']
```

- **list可以进行出栈操作pop**

```python
element = list.pop() #删除列表的最后一个元素并返回它
print(element) #prints: 'hello'
```

- **list独特的切片操作**

```python
nums = list(range(5))     # 使用range来创建一个整型的列表
print(nums)               # Prints "[0, 1, 2, 3, 4]"
print(nums[2:4])          # 将索引是2到4（左闭右开）的元素切片输出 0 1|2 3|4
print(nums[2:])           # 将索引是2到最后的元素切片输出 0 1|2 3 4|
print(nums[:2])           # 将索引是2前面（开区间）的元素切片输出 |0 1|2 3 4
print(nums[:])            # 将整个列表切片输出 |0 1 2 3 4|
print(nums[:-1])          # 将倒是第一个元素以前（不包含本身）的元素切片输出 |0 1 2 3|4
nums[2:4] = [8, 9]        # 可以对列表的元素切片赋新值
print(nums)               # Prints "[0, 1, 8, 9, 4]"
```

### Dictionaries 字典 

存在**一一对应**的映射关系的一种容器结构（键，值）<font color=red>**使用的是大括号{ }和冒号:的组合表示**</font>

```python
d = {'cat': 'cute', 'dog': 'furry', 'pig': 'lazzy'} 
print(d['cat']) #'cat'对应'cute'，所以prints：'cute'

#可以检查对应关系是否存在
print('cat' in d) # prints: True

#可以直接添加键与值的对应关系
d['fish']= 'wet'
print(d) # prints:{'cat': 'cute', 'dog': 'furry', 'pig': 'lazzy', 'fish': 'wet'}

#get方法可以获取键对应的值
print(d.get('monkey','N/A')) #如果字典中不存在键 `'monkey'`，则返回默认值 `'N/A'`。
#这是一种安全访问字典元素的方式，可以避免因为键不存在而导致的 `KeyError` 异常。

#使用del删除字典中的键和其对应的值
del d['fish']
print(d) # prints:{'cat': 'cute', 'dog': 'furry', 'pig': 'lazzy'}

#字典中允许出现不同类型的键与值
d[23] = 'spider'
d['frog'] = 2
print(d) # prints:{'cat': 'cute', 'dog': 'furry', 'pig': 'lazzy', 23: 'spider', 'frog': 2}
```

### set 集合

集合是由不同元素组成的**无序**集合。<font color=red>**使用的是大括号{ }表示**</font>

```python
animals = {'cat', 'dog', 'pig'}
print('cat' in animals)   # 检查元素是否在集合中; prints "True"
print('fish' in animals)  # prints "False"

#使用add方法在集合中添加元素
animals.add("fish")
print('fish' in animals)  # prints "True"

#用len返回集合长度
print(len(animals)) #prints 4

#用remove删除集合中的元素
animals.remove('pig')
print(len(animals)) #prints 3
```

### tuple元组

元组是一个**（不可变的）**有序值列表。元组在很多方面与列表相似，其中最重要的区别是元组可以用作字典中的键和集合中的元素，而列表则不能，<font color=red>**用小括号表示（）**</font>

```python
d = {(x, x + 1): x for x in range(6)}  # Create a dictionary with tuple keys
print(d)	# prints {(0, 1): 0, (1, 2): 1, (2, 3): 2, (3, 4): 3, (4, 5): 4, (5, 6): 5}
t = (5, 6)        # Create a tuple
print(type(t))    # Prints "<class 'tuple'>"
print(d[t])       # Prints "5"
print(d[(1, 2)])  # Prints "1"
```

## Numpy
