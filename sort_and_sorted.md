# sort( ) and sorted( )
 **sorted()和sort()函数一般有三个参数（cmp, key, reverse):** <br>
 * **cmp为用户定义的任何比较函数，函数的参数为两个可以比较的元素（来自iterable或者list),<br>
 函数根据第一个参数与第二个参数的关系依次返回-1、0、+1（第一个参数小于第二个返回-1）.**

**sorted( )可以作用于任何可迭代对象，而sort( )一般作用于列表.**
* **sorted( )的使用范围更广，可以对字典进行排序，对多维list进行排序等.**

### Example 1:
```
a = (1,2,3,4,5,2)
a.sort()
This will come with:
AttributeError: 'tuple' object has no attribute 'sort'
```
* **使用 sorted( ) 函数则没有这个问题.**
* **sort() 函数会直接修改原来的list，消耗内存少，效率更高，<br>
而sorted()会返回一个排序后的列表，原有的list保持不变.** <br>

* **传入参数key比参数cmp效率更高**

### Example 2:

```
persons = [{'name': 'John', 'age':32}, {'name': 'Alen', 'age':50}, {'name': 'Bob', 'age':23}, {'name': 'John', 'age':66}]
a = sorted(persons, key = lambda x: (x['name'], x['age']))
print(a)
```
### Example 3:

```
mydict = {
    'Li': ['M', 7],
    'Zhsng': ['E', 2],
    'Wang': ['P', 3],
    'Deng': ['O', 9]
}

t = sorted(mydict.items(), key = lambda x: x[1][1])
print(t)
#[('Zhsng', ['E', 2]), ('Wang', ['P', 3]), ('Li', ['M', 7]), ('Deng', ['O', 9])]


grades = [['Bob', 95, 'A'], ['Allen', 86, 'C'], ['Mandy', 83, 'A']]
a = sorted(grades, key = lambda x: (x[2], x[1]))
print(a)
#[['Mandy', 83, 'A'], ['Bob', 95, 'A'], ['Allen', 86, 'C']]
```
