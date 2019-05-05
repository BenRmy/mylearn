# 该文件是python的一些常用库

## 基本工具

pipenv：Python(虚拟)环境和依赖项管理  
pip、setuptools、wheel：Python的包管理器  
Jupyter notebook：在浏览器中提供Python基本解释器的所有功能  
fabric：控制多个服务器、方便安装、更改设置、开关某service等等  
nose、unittest、mock、coverage：测试相关库，优先使用nose  
cProfile：性能测试模块  
threading：标准库，多线程库，少用  
gevent、eventlet：异步库  
multiprocessing：标准库，多进程库，也包含了多线程，可以使用多个处理器  
concurrent.futures：标准库，提供一些未列入标准的使用功能，包括进程池/线程池相关  
pypy/psyco/cython/ctypes/cffi：与C语言相关库  
celery、luigi：分布式任务管理库  
logging：日志库  
docopt、argparse：参数解析库  
itertools：迭代器相关  
functools：主要用于高阶函数（返回其他函数的函数），任何可调用对象都可以被视为可用于此模块  
subprocess：调用shell命令  
Queue：队列  

## 数据处理

NumPy：提供一些数学功能  
pandas：基于numpy的数据处理和分析库  
Dask：实现了NumPy阵列的直接替代，可处理大于内存的数据并可以利用多核  
scipy：Python的算法和数学工具库  
SymPy：代数评测、差异化、扩展、复数等等  
sklearn：机器学习  
nltk、pattern：语言处理工具  
pyopencl、pyopengl、pycuda：利用GPU让numpy做复杂任务更加强更快  
Pillow：图像处理库  
PyVips：图像处理库。libvips的Python绑定，比pillow更快且占用的内存更少  
Faust：数据的流处理器  
pickle：数据序列化  
Pyflux：用于预测和分析时间序列  

## 数据可视化

matplotlib：全面的数据可视化库  
pyecharts：百度的数据可视化图表库  
Seaborn：基于matplotlib的数据可视化库  
Plotly：制作交互式、出版品质的图表  
Plotly Express：是Plotly.py的高级封装，为复杂的图表提供了一个简单的语法  
Bokeh：交互式数据可视化  
Dash：创建数据可视化的web应用程序  

## 网络相关

urllib：标准库，包含HTTP请求、响应、URL、错误等的基本操作函数  
urllib3：标准库，是urllib的补充，功能更全且更安全  
Requests：简单方便的HTTP请求库  
aiohttp：异步的HTTP库  
Twisted：基于事件驱动的网络框架，使网络应用程序的实现变得容易  
flask：web开发微框架  
Sanic：类似flask的异步web框架  
django：web开发重框架  
Falcon：一个构建云API的高性能Python框架,它鼓励使用REST架构风格  
Hug：提供在Python中创建HTTP REST API的最简洁方法  
Responder：一个HTTP服务框架（可异步），Flask，Falcon和Requests之间的混合  
Uvicorn：用于生产的Web服务器  
Pattern：网络信息挖掘模块  

## 爬虫相关

scrapy：用于创建爬虫程序  
PySpider：网络爬虫系统，可在浏览器中写爬虫脚本  
Selenium：web自动化测试工具，也可用于爬虫  
pyppeteer：类似Selenium但更简单，异步方式使用chromium  
Requestium：Requests和Selenium库的集合体，主要用于抓取含js的web内容  
appium：App自动化测试工具  
re：Python自带的正则表达式库  
FlashText：正则regexp的搜索及替换优化  
json：标准库，处理小型的json数据  
Simplejson：json编码器和解码器，比json有更高的性能  
lxml：xml和html的解析库，使用xpath语法  
pyquery：类似jquery方式来解析html  
BeautifulSoup：xml和html的解析库，使用css语法  

## 数据库相关

pymysql：myqsl关系型数据库连接器  
pymongo：mongo非关系型数据库连接器  
redis：redis非关系型数据库连接器  
psycopg2：postgretsql关系型数据库连接器  
asyncpg：PostgreSQL异步连接库，比psycopg2更快  
SQLAlchemy：ORM，使用面向对象方法操作数据库  
Peewee：轻量级的ORM，主要是操作关系型数据库  
Blaze：从多种数据库技术中抽象出来，提供了统一界面  

## 深度学习

jieba：中文分词工具  
Imbalanced-learn：对机器学习中的不平衡数据进行处理  
theano：深度学习库，用于优化、定义和评估数值方程和多为数组。基本上是数学表达式的编译器  
skorch：一个包装器，为PyTorch提供类似sklearn的界面  
pytorch：numpy的替代品，更高级的封装来构建神经网络  
Keras：对机器学习算法的更高级抽象，内部使用Theano或TensorFlow  
tensorflow：机器学习库，也可以是theano的替代品  
Eli5：使机器学习的结果更加准确  

## GUI相关库

wxpython和pyQT和thinter：用于python的GUI工具包  
simpleGUI：简单快速的gui工具包，是thinter的高级封装  
Remi：gui库，将Python代码转换为HTML界面，只依赖浏览器  

## 游戏相关

Pygame：2D游戏开发  
Pyglet：3D动画和游戏创作  

## 办公相关

PyYAML：读取脚本配置yaml文件  
xmltodict：xml转dict  
python-magic： 文件类型检测，libmagic的Python封装  
xlrd/xlwt：读写Excel文件的数据和格式信息  
openpyxl：读写Excel 2010 xlsx/xlsm/xltx/xltm 文件的库  
PDFMiner：从PDF文档中抽取信息的工具  

## 其他实用库

chardet：字符编码检测器  
difflib：对比文本之间的差异  
fuzzywuzzy：模糊字符串匹配  
Arrow、Pendulum：简单方便的时间处理库  
Trio：编写异步I/O程序  
fire：自动构建CLI  
pywin32：提供与windows交互的方法和类  
Retry：实现了通用装饰器，提供重试的行为  
phonenumbers：Google的一个接口，用于验证电话号码  
NetworkX：创建和操作网络图形  
Zappa：Python的无服务器框架  
black：Python文件格式化，可看作PEP8规则的严格子集  
nanotime：纳秒级的时间  
psutil：系统性能参数信息  
Scapy：数据包嗅探器和分析器  
uniout：打印可读的字符，而不是转义的字符串  
xpinyin：把汉字转换为拼音  
pprint：漂亮的输出  
timeit：计算代码运行的时间  
atexit：可用于在脚本退出运行前执行一些代码  
PyInstaller：将Python程序转换成独立的执行文件（跨平台）  
pathlib：跨平台的、面向对象的路径操作库
