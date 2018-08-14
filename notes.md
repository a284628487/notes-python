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
