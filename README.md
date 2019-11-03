# pyqt5
pyhon+pyqt5+access实现数据管理

此程序构建了一个管理数据的桌面GUI，5000行代码量，共七个界面，包括数据的录入、导出（支持excel批量），还包括查询功能，其中供应商查询实现了交叉查询。

关于界面：采用QT designer进行界面搭建之后利用eric6（pycharm也行）转化为代码

关于功能：主要包含了界面和access数据库、excel表格间的数据交互，数据库交互利用了pyqt5本身连接数据库的接口函数和pyodbc；excel表格的数据交互用到了xlrd(
读)、openxl(写)

关于界面与功能交互：采用了pyqt5中signal-function的模式，即控件操作可发出信号，编写函数捕捉信号即可完成功能上的交互。所用到的控件信号主要包括：
按钮单击（导入、导出、查询等）、下拉框激活以及选择、复选框选择等。

关于注意事项：此程序利用pyinstall可打包成exe，大概30M左右，对打包环境有要求：
window环境：32bit或64bit；Micro office环境：32bit或64bit。运行环境要与打包环境一致。
上传代码的运行环境为：64bit windows+ 64bit office(**64bit ODBC数据源**)，首先检查ODBC中是否包含64bit accesss数据源，不包含需要创建，不然无法运行。
如果为32bit office可参考一下代码进行替换：

  64bit
  Microsoft Access Driver (*.mdb, *.accdb)

  32bit
  Microsoft Access Driver (*.mdb)


程序中引用的附件涉及公司文件不方便上传，主要是一些表格导入导出的模板。更详细的介绍可参考上传的PPT。
