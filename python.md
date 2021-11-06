## 连接mysql

```
#安装包
#mysql 5.0
pip install mysql-connector
#mysql 8.0
pip install MySQL-connector-python
```

```
#导入包
import mysql.connector
#建立连接
mydb = mysql.connector.connect(
    host="google.com",  # 数据库主机地址
    user="user",  # 数据库用户名
    passwd="123456@WS"  # 数据库密码
)
```



## 办公自动化

```python
# .xlsx
import openpyxl
# .xls
import xlrd xlwt xlutils
# 获取工作簿
workbook = openpyxl.load_workbook('resources/py.xlsx')
# 获取表格
sheet = workbook['Sheet1']  # type:Worksheet
# h
cell = sheet['B2']  # type:Cell
```

## OpenCV

```bash
pip install numpy
pip install matplotlib

#3.4.3版本y
pip install opencv-python==3.4.2.17
```



```python
import cv2 as cv
#查看版本
print(cv.__version__)
```
