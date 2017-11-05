# 每天踩过的坑

- **时间戳**
unix的时间戳和java中的是不同的。unix为10位，java的13位。需要进行转换。

 ```java
 long timestamps = 1509783992L
long javaTimstamps = timestamps * 100
 ```
- **navicat导出数据字典**

 ```sql
 SELECT TABLE_SCHEMA,TABLE_NAME,COLUMN_NAME,COLUMN_TYPE,COLUMN_COMMENT  FROM information_schema.columns WHERE TABLE_SCHEMA='table name'
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
