# 语法点记录

@(技术)


- **时间戳**
unix的时间戳和java中的是不同的。unix为10位，java的13位。需要进行转换。

```java
long timestamps = 1509783992L;
long javaTimstamps = timestamps * 1000;
```
- **navicat导出数据字典**

```sql
SELECT TABLE_SCHEMA,TABLE_NAME,COLUMN_NAME,COLUMN_TYPE,COLUMN_COMMENT FROM information_schema.columns WHERE TABLE_SCHEMA='table name'
```
- **Java处理NaN的数据**

```java
private static boolean isNaNOrInfinite(double val) {
	return Double.isNaN(val) || Double.isInfinite(val);
}
```

- **解决python2.7 list输出中文为unicode**

```python
case_list = str(list).replace('u\'','\'')
print case_list.decode("unicode-escape")
```
- **py3列出路径下的所有文件**

```python
def get_all_files(path):
    files = []
    for dir_path, dir_names, file_names in os.walk(path):
        for name in file_names:
            if KEY in os.path.join(dir_path, name):
                files.append(os.path.join(dir_path, name))
    return files
```

- **py3列表去重**

```python
L = []
list = list(set(L))
```

- **py3文件读取**
`codecs.open`会自动对编码进行转换，比py自带的`open()`更友好。
```python
import codecs
with codecs.open("","r") as f:
	f.read()
```

- **py3异常处理**
`codecs.open`会自动对编码进行转换，比py自带的`open()`更友好。
```python
try:
<语句>        #运行别的代码
except <名字>：
<语句>        #如果在try部份引发了'name'异常
except <名字>，<数据>:
<语句>        #如果引发了'name'异常，获得附加的数据
else:
<语句>        #如果没有异常发生
```

- **py3 http请求包——requests**

```python
import requests

url = "http://www.qydeng.com/qydeng/icCardController.do"
querystring = {"app/uploadIcCardInfo":"","type":"1"}
headers = {
    'cache-control': "no-cache",
    'postman-token': "1bce74fd-4034-8cc8-1625-368a76dc4b12"
    }
response = requests.request("GET", url, headers=headers, params=querystring)
print(response.text)
```
