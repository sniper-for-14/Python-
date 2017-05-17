# Python-
##迭代器 iterator 和生成器 constructor
一、迭代器iteraor
  在Python中，for循环可以用于Python中的任何类型，包括列表、元祖等等，实际上，for循环可用于任何“可迭代对象”，这其实就是迭代器
  for line in open("test.txt").readlines():
    print line
  文件一次性加载到内存中，然后逐行打印
  for line in open("test.txt"):   #use file iterators
    print line
二、生成器 constructor
    生成器函数在Python中与迭代器协议的概念联系在一起。简而言之，包含yield语句的函数会被特地编译成生成器。当函数被调用时，他们返回一个生成器对象，
    这个对象支持迭代器接口。函数也许会有个return语句，但它的作用是用yield产生值的。
    不像一般的函数会生成值后退出，生成器函数在生成值后会自动挂起并暂停他们的执行和状态，他的本地变量将保存状态信息，这些信息在函数恢复时将再度有效
    
    def g(n):
    for i in range(n):
        yield i**2
        

    for i in g(5):
        print(i,end=':')
      
      t.__next__()
      Out[16]: 0

      t.__next__()
      Out[17]: 1

      t.__next__()
      Out[18]: 4

      t.__next__()
      Out[19]: 9

      t.__next__()
      Out[20]: 16

      t.__next__()
      ---------------------------------------------------------------------------
      StopIteration                             Traceback (most recent call last)
      <ipython-input-21-59371ca21898> in <module>()
      ----> 1 t.__next__()

      StopIteration: 

      简单地讲，yield 的作用就是把一个函数变成一个 generator，带有 yield 的函数不再是一个普通函数，Python 解释器会将其视为一个 generator，
      调用 fab(5) 不会执行 fab 函数，而是返回一个 iterable 对象！在 for 循环执行时，每次循环都会执行 fab 函数内部的代码，执行到 yield b 时，
      fab 函数就返回一个迭代值，下次迭代时，代码从 yield b 的下一条语句继续执行，而函数的本地变量看起来和上次中断执行前是完全一样的，于是函数
      继续执行，直到再次遇到 yield
