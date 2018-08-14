## 多行字符串
```python
str = '''
{0} : {1} : {2} abcde
'''
str.format(1, 2, "CF")
```

## json.dumps格式化对象
```python
class Obj:
	# ...
	def __repr__():
		return json.dumps(self, default=lambda obj: obj.__dict__)
```
		
## 读写文件
```python
def rwFile(filePath):
	# 读文件
	with open(filePath, mode='r', encoding='UTF-8') as f:
		lines = f.readlines()
		return lines
	# 写文件
	with open('output.html', "w") as f:
		f.write(html + outContent + "</body>")		
```
		
## 字符串操作
```python
str = "  abc: key "
str = str.strip(); # "abc: key"
str.find('a') # 0
strArr = str.split(":") # ["abc", " key"]
```

## list
```python
list = [1, 2, 3]
list.append(4)
```

## Input&Output
```python
if __name__ == '__main__':
	doCompare(sys.argv)
	# sys.argv 为一个数组，可以获取用户传入的参数
```

## 多线程

```python
# -*- coding: UTF-8 -*-

import threading
import time

# 申请锁对象
threadLock = threading.Lock()
# 使用 Thread 对象的 Lock 和 Rlock 可以实现简单的线程同步，这两个对象都有 acquire 方法和 release 方法，
# 对于那些需要每次只允许一个线程操作的数据，可以将其操作放到 acquire 和 release 方法之间。
class FuckThread(threading.Thread):
	def __init__(self, threadId, name):
		threading.Thread.__init__(self)
		self.threadId = threadId
		self.name = name

	def run(self):
		print("开始线程：%s" % self.name)
		# 获取锁
		threadLock.acquire()
		# 执行方法
		doLuck(self.name)
		# 释放锁
		threadLock.release()
		print("结束线程：%s" % self.name)

def doLuck(threadName):
	i = 3
	while i:
		print("%s do Luck" % threadName)
		i -= 1

thread1 = FuckThread(12, "A1")
thread2 = FuckThread(13, "A2")

thread1.start()
thread2.start()

thread1.join()
thread2.join()

print("主线程结束！！！")
```
- [Link1](http://www.runoob.com/python3/python3-multithreading.html)
- [Link2](https://www.cnblogs.com/284628487a/p/5590857.html)
