### һ��Python���ֵ�ĸ�ʽ��JSON��ʽ�Աȣ�

- �ֵ��е�����֧�ֵ����ź�˫���ţ�JSON��ʽֻ֧��˫����
- �ֵ��е�True/False����ĸ��д��JSON��ʽΪtrue/false
- �ֵ��еĿ�ֵΪNone, JSON��ʽΪnull




### ����JSON��ʽ��������
- ���л����ֵ� -> �ı�/�ļ�������� json.dumps()/json.dump()
- �����л����ı�/�ļ���� -> �ֵ�) : json.loads()/json.load()

|����|��;|
|--|--|
|json.dumps()|�����ǽ�һ��Python���������б����json��ʽ�ı��루���ֵ�ת��Ϊ�ַ�����|
|json.loads()|�����ǽ�json��ʽ����ת��Ϊ�ֵ䣨���ַ���ת��Ϊ�ֵ䣩|
|json.dump()|��json��Ϣд���ļ�|
|json.load()|���ļ���ȡjson��Ϣ|


#### 2.1 json.dumps()���������ֵ�ת��Ϊ�ַ���
- Ĭ�ϸ�ʽ
```
import json
dict1 = {"age": "12"}
json_info = json.dumps(dict1)
print(f"dict1�����ͣ�{type(dict1)}")
print(f"json.dumps()�������������ͣ�{type(json_info)}")

# ִ�н��
dict1�����ͣ�<class 'dict'>
json.dumps()�������������ͣ�<class 'str'>
```

- json.dumps()֧�ֽ�json�ı���ʽ�����
	- indent: �����ո�����indent=0���Ϊһ��
	- sork_keys=True: ��json�����key��ascii������
	- ensure_ascii=Fasle: ��ȷ��ascii�룬������ظ�ʽΪutf-8�������ģ���ת��Ϊ\u...

```
import json # ��Ҫ����JSON��
data = {'name': '����', 'password': '123456', "male": True, "money": None} # �ֵ��ʽ
print(json.dumps(data, indent=2, sort_keys=True, ensure_ascii=False)) # תΪ�ı�

#ִ�н��
{
  "male": true,
  "money": null,
  "name": "����",
  "password": "123456"
}
```



#### 2.2 json.loads()���������ַ���ת��Ϊ�ֵ�
```
import json
json_info = '{"age": "12"}'
dict1 = json.loads(json_info)
print(f"json_info�����ͣ�{type(json_info)}")
print(f"json.loads()�������������ͣ�{type(dict1)}")
# ִ�н��
json_info�����ͣ�<class 'str'>
json.loads()�������������ͣ�<class 'dict'>
```


#### 2.3 json.dump()��������json��Ϣд���ļ�
```
import json
json_info = "{'age': '12'}"
file = open('1.json','w',encoding='utf-8')
json.dump(json_info,file)

# ���ɵ�1.json�ļ�����
"{'age': '12'}"
```


#### 2.4 json.load()���������ļ���ȡjson��Ϣ
```
import json
file = open('1.json','r',encoding='utf-8')
info = json.load(file)
print(type(info))
print(info)

# ִ�н��
<class 'str'>
{'age': '12'}

```



### �����ο�����
- [python��json�ļ������漰���ĸ�����json.dumps()��json.loads()��json.dump()��json.load()������](https://www.cnblogs.com/xiaomingzaixian/p/7286793.html)
- [Python�ӿڲ���ʵս2 - ʹ��Python��������](file:///C:/Users/admin/Desktop/Python%E6%8E%A5%E5%8F%A3%E6%B5%8B%E8%AF%95%E5%AE%9E%E6%88%982%20-%20%E4%BD%BF%E7%94%A8Python%E5%8F%91%E9%80%81%E8%AF%B7%E6%B1%82%20-%20%E7%AE%80%E4%B9%A6.html)































































