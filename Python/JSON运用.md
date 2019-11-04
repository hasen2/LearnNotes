### 一、Python的字典的格式和JSON格式对比：

- 字典中的引号支持单引号和双引号，JSON格式只支持双引号
- 字典中的True/False首字母大写，JSON格式为true/false
- 字典中的空值为None, JSON格式为null




### 二、JSON格式操作方法
- 序列化（字典 -> 文本/文件句柄）： json.dumps()/json.dump()
- 反序列化（文本/文件句柄 -> 字典) : json.loads()/json.load()

|函数|用途|
|--|--|
|json.dumps()|函数是将一个Python数据类型列表进行json格式的编码（将字典转化为字符串）|
|json.loads()|函数是将json格式数据转换为字典（将字符串转化为字典）|
|json.dump()|将json信息写入文件|
|json.load()|从文件读取json信息|


#### 2.1 json.dumps()举例：将字典转化为字符串
- 默认格式
```
import json
dict1 = {"age": "12"}
json_info = json.dumps(dict1)
print(f"dict1的类型：{type(dict1)}")
print(f"json.dumps()函数处理后的类型：{type(json_info)}")

# 执行结果
dict1的类型：<class 'dict'>
json.dumps()函数处理后的类型：<class 'str'>
```

- json.dumps()支持将json文本格式化输出
	- indent: 缩进空格数，indent=0输出为一行
	- sork_keys=True: 将json结果的key按ascii码排序
	- ensure_ascii=Fasle: 不确保ascii码，如果返回格式为utf-8包含中文，不转化为\u...

```
import json # 需要导入JSON包
data = {'name': '张三', 'password': '123456', "male": True, "money": None} # 字典格式
print(json.dumps(data, indent=2, sort_keys=True, ensure_ascii=False)) # 转为文本

#执行结果
{
  "male": true,
  "money": null,
  "name": "张三",
  "password": "123456"
}
```



#### 2.2 json.loads()举例：将字符串转化为字典
```
import json
json_info = '{"age": "12"}'
dict1 = json.loads(json_info)
print(f"json_info的类型：{type(json_info)}")
print(f"json.loads()函数处理后的类型：{type(dict1)}")
# 执行结果
json_info的类型：<class 'str'>
json.loads()函数处理后的类型：<class 'dict'>
```


#### 2.3 json.dump()举例：将json信息写入文件
```
import json
json_info = "{'age': '12'}"
file = open('1.json','w',encoding='utf-8')
json.dump(json_info,file)

# 生成的1.json文件内容
"{'age': '12'}"
```


#### 2.4 json.load()举例：从文件读取json信息
```
import json
file = open('1.json','r',encoding='utf-8')
info = json.load(file)
print(type(info))
print(info)

# 执行结果
<class 'str'>
{'age': '12'}

```



### 三、参考资料
- [python中json文件处理涉及的四个函数json.dumps()和json.loads()、json.dump()和json.load()的区分](https://www.cnblogs.com/xiaomingzaixian/p/7286793.html)
- [Python接口测试实战2 - 使用Python发送请求](file:///C:/Users/admin/Desktop/Python%E6%8E%A5%E5%8F%A3%E6%B5%8B%E8%AF%95%E5%AE%9E%E6%88%982%20-%20%E4%BD%BF%E7%94%A8Python%E5%8F%91%E9%80%81%E8%AF%B7%E6%B1%82%20-%20%E7%AE%80%E4%B9%A6.html)































































