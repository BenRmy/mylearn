# 以下是Python的一些常用库的使用介绍和示例

## Jupyter notebook

一个交互式的笔记本，支持运行超过40种编程语言。  
详情见：<https://jupyter.org/>

## nose

nose的优势：  
-编写测试更容易。nose可以自动识别继承于unittest.TestCase的测试单元，并执行测试，而且，nose也可以测试非继承于unittest.TestCase的测试单元。nose提供了丰富的API便于编写测试代码。  
-执行测试更容易。只要遵循一些简单的规则去组织你的类库和测试代码，nose是可以自动识别单元测试的。执行测试是非常耗资源的，但是，一般第一个测试模块被加载后，nose就开始执行测试。  
-建立测试环境更容易。  
-做你想做的事情更容易。nose拥有很多内置的插件帮助进行暑输出抓取、错误查找、代码覆盖、文档测试（doctest）等等。同样，可以自定义开发插件来完成你想要做的事情。  
使用格式: nosetests [options]

Options:  
  -h, --help            显示此帮助消息并退出  
  -V, --version         输出nose版本并退出  
  -p, --plugins         可用插件的输出列表并退出。可结合-v以获得更多细节  
  -v, --verbose         详情[NOSE_VERBOSE]  
  --verbosity=VERBOSITY 设置verbose：--verbosity=2与-v相同  
  -q, --quiet           不要详情  
  -c FILES, --config=FILES  从配置文件加载配置。可多次指定  
  -w WHERE, --where=WHERE  在此目录中查找测试[NOSE_WHERE]  
  --py3where=PY3WHERE   在Python 3.x下查找此目录中的测试[NOSE_PY3WHERE]  
  -m REGEX, --match=REGEX, --testmatch=REGEX  与此正则表达式匹配的文件，目录，函数名称和类名称被视为测试。默认: `(?:^|[\b_\./-])[Tt]est` [NOSE_TESTMATCH]  
  --tests=NAMES         运行这些测试（以逗号分隔的列表）。这个参数主要来自配置文件;在命令行上，只需传递测试以作为没有开关的附加参数运行。  
  -l DEBUG, --debug=DEBUG  激活一个或多个系统的调试日志记录  
  --debug-log=FILE      将调试消息记录到此文件 (默认: sys.stderr)  
  --logging-config=FILE, --log-config=FILE  从此文件加载日志记录配置--绕过所有其他日志记录配置设置。  
  -I REGEX, --ignore-files=REGEX  完全忽略与此正则表达式匹配的任何文件。优先于任何其他设置或插件。指定此选项将替换默认设置。多次指定此选项可添加更多正则表达式[NOSE_IGNORE_FILES]  
  -e REGEX, --exclude=REGEX  不要运行与正则表达式匹配的测试[NOSE_EXCLUDE]  
  -i REGEX, --include=REGEX  此正则表达式将应用于文件，目录，函数名称和类名，以便包含与TESTMATCH不匹配的其他测试。多次指定此选项可添加更多正则表达式[NOSE_INCLUDE]  
  -x, --stop            在第一次错误或失败后停止运行测试  
  -P, --no-path-adjustment  加载测试时，不要对sys.path进行任何更改[NOSE_NOPATH]  
  --exe                 在可执行的python模块中查找测试。正常行为是排除可执行模块，因为它们可能不是导入安全的[NOSE_INCLUDE_EXE]  
  --noexe               不要在可执行的python模块中查找测试（Windows平台上的默认设置是这样做）  
  --traverse-namespace  遍历命名空间包的所有路径条目  
  --first-package-wins, --first-pkg-wins, --1st-pkg-wins  如果在不同的位置看到一个包含相同名称的包，则nose的导入器通常会从sys.modules中删除一个包。设置此选项可禁用该行为。  
  --no-byte-compile     当nose扫描并运行测试时，防止nose将源代码编译成.pyc文件  
  -a ATTR, --attr=ATTR  仅运行具有ATTR指定的属性的测试[NOSE_ATTR]  
  -A EXPR, --eval-attr=EXPR  仅运行Python表达式EXPR评估为True的属性的测试[NOSE_EVAL_ATTR]  
  -s, --nocapture       不捕获标准输出（任何标准输出将立即打印）[NOSE_NOCAPTURE]  
  --nologcapture        禁用日志记录捕获插件。记录配置将保持不变。[NOSE_NOLOGCAPTURE]  
  --logging-format=FORMAT  指定自定义格式以打印语句。默认使用与标准日志记录处理程序使用的格式相同的格式。[NOSE_LOGFORMAT]  
  --logging-datefmt=FORMAT  指定自定义日期/时间格式以打印语句。默认使用与标准日志记录处理程序使用的格式相同的格式。[NOSE_LOGDATEFMT]  
  --logging-filter=FILTER  指定要过滤/过滤的语句。默认情况下，捕获所有内容。如果输出过于冗长，请使用此选项过滤掉不必要的输出。  
  示例：filter=foo将捕获仅发送给foo或foo.what.ever.sub的语句，但不捕获foobar或其他记录器。使用逗号指定多个记录器：filter=foo，bar，baz。如果任何记录器名称前缀为减号，例如filter=-foo，则将其排除而不是包括在内。
  默认值：从nose本身排除日志消息[NOSE_LOGFILTER]  
  --logging-clear-handlers  清除所有其他日志处理程序  
  --logging-level=LOGCAPTURE_LEVEL  设置要捕获的日志级别  
  --with-coverage       启用插件覆盖：使用Ned Batchelder的覆盖模块激活覆盖率报告。[NOSE_WITH_COVERAGE]  
  --cover-package=PACKAGE  将覆盖范围输出限制为选定的包[NOSE_COVER_PACKAGE]  
  --cover-erase         在运行之前删除先前收集的覆盖率统计  
  --cover-tests         在覆盖率报告中包含测试模块[NOSE_COVER_TESTS]  
  --cover-min-percentage=COVER_MIN_PERCENTAGE  通过测试的最小覆盖率[NOSE_COVER_MIN_PERCENTAGE]  
  --cover-inclusive     在coverage报告中包含工作目录下的所有python文件。如果测试套件未导入所有文件，则可用于发现测试覆盖中的漏洞。[NOSE_COVER_INCLUSIVE]  
  --cover-html          生成HTML覆盖信息  
  --cover-html-dir=DIR  在dir中生成HTML覆盖信息  
  --cover-branches      在覆盖率报告中包括分支覆盖范围[NOSE_COVER_BRANCHES]  
  --cover-xml           生成XML覆盖信息  
  --cover-xml-file=FILE 生成XML覆盖信息到FILE文件  
  --pdb                 在出现故障或错误时进入调试器  
  --pdb-failures        在失败时进入调试器  
  --pdb-errors          在出错时进入调试器  
  --no-deprecated       禁用对DeprecatedTest异常的特殊处理  
  --with-doctest        启用插件Doctest：激活doctest插件以在非测试模块中查找和运行doctests[NOSE_WITH_DOCTEST]  
  --doctest-tests       在测试模块中查找doctests。请注意，类、方法和函数应该具有doctests或非doctest测试，而不是两者。[NOSE_DOCTEST_TESTS]  
  --doctest-extension=EXT  同时在具有此扩展名的文件中查找doctests  [NOSE_DOCTEST_EXTENSION]  
  --doctest-result-variable=VAR  将变量名称设置为默认值“`_`”的最后一个解释器命令的结果。可用于避免与用于文本转换的_（）函数冲突[NOSE_DOCTEST_RESULT_VAR]  
  --doctest-fixtures=SUFFIX  在模块中查找doctest文件的fixture，并将此名称附加到doctest文件的基本名称  
  --doctest-options=OPTIONS  指定要传递给doctest的选项。  
  --with-isolation      启用插件IsolationPlugin：激活隔离插件以将外部模块的更改隔离到单个测试模块或包。隔离插件在每个测试模块或包运行到测试之前的状态后重置sys.modules的内容。请注意，此插件不应与coverage插件一起使用，或者在模块重新加载可能产生不良副作用的任何其他情况下使用。[NOSE_WITH_ISOLATION]  
  -d, --detailed-errors, --failure-detail  尝试评估失败的断言，向错误输出添加详细信息[NOSE_DETAILED_ERRORS]  
  --no-skip             禁用SkipTest异常的特殊处理  
  --with-id             启用插件TestId：激活以向每个测试名称输出添加测试ID（如＃1）。使用--failed激活仅重新运行失败的测试。[NOSE_WITH_ID]  
  --id-file=FILE        存储在此文件中的测试运行中找到的测试ID。默认值是工作目录中的.noseids文件。  
  --failed              运行上次测试运行失败的测试。  
  --processes=NUM       在这许多过程中进行传播测试。设置一个等于机器中处理器或内核数量的数字，以获得最佳效果。传递一个负数，使进程数自动设置为核心数。传递0意味着禁用并行测试。除非设置了NOSE_PROCESSES，否则默认值为0。[NOSE_PROCESSES]  
  --process-timeout=SECONDS  设置超时以返回每个测试运行程序进程的结果。默认值为10。[NOSE_PROCESS_TIMEOUT]  
  --process-restartworker  如果设置，将在测试完成后重新启动每个工作进程，这有助于控制内存泄漏以杀死系统。[NOSE_PROCESS_RESTARTWORKER]  
  --with-xunit          启用插件Xunit：此插件以标准XUnit XML格式提供测试结果。[NOSE_WITH_XUNIT]  
  --xunit-file=FILE     用于存储xunit报告的xml文件的路径。默认为工作目录中的nosetests.xml[NOSE_XUNIT_FILE]  
  --xunit-testsuite-name=PACKAGE  xunit xml中由插件生成的testsuite的名称。默认测试套件名称是nosetests。  
  --all-modules         启用插件AllModules：从所有python模块收集测试。[NOSE_ALL_MODULES]  
  --collect-only        启用仅收集：仅收集和输出测试名称，不运行任何测试。[COLLECT_ONLY]  

## threading

threading模块是Python里面常用的线程模块，多线程处理任务对于提升效率非常重要。  
线程是计算机中执行任务的最小单元。一般IO密集型应用使用多线程（不使用CPU）。  
线程优点：共享内存，IO操作时相当于并发操作  
线程缺点：抢占资源时需要锁  
线程不是越多越好，需要具体分析，因为线程切换也需要时间  

### threading模块可以创建多个线程，不过由于GIL锁的存在，Python在多线程里面其实是快速切换。所以一般用于IO密集型应用。

示例：

```python3
import time
import threading


def ff(a1, a2):
    time.sleep(5)  # 代表IO耗时操作
    # 其他操作或函数动作


# 下面代码是直接运行下去的，不会等待函数里面设定的sleep
t = threading.Thread(target=ff, args=(111, 112))  # 创建线程
# 设置为后台线程，默认是False，设置为True之后则主线程不用等待子线程。注意与join()的区别
t.setDaemon(True)
t.start()  # 开启线程

t = threading.Thread(target=ff, args=(111, 112))
t.start()

t = threading.Thread(target=ff, args=(111, 112))
t.start()
```

在线程里面setDaemon（）和join（）方法都是常用的，他们的区别如下：

+ join ()方法：主线程A中，创建了子线程B，并且在主线程A中调用了B.join()，那么，主线程A会在调用的地方等待，直到子线程B完成操作后，才可以接着往下执行，那么在调用这个线程时可以使用被调用线程的join方法。join([timeout]) 里面的参数时可选的，代表线程运行的最大时间，即如果超过这个时间，不管这个此线程有没有执行完毕都会被回收，然后主线程或函数都会接着执行的，如果线程执行时间小于参数表示的时间，则接着执行，不用一定要等待到参数表示的时间。

+ setDaemon()方法。主线程A中，创建了子线程B，并且在主线程A中调用了B.setDaemon(),这个的意思是，把主线程A设置为守护线程，这时候，要是主线程A执行结束了，就不管子线程B是否完成,一并和主线程A退出.这就是setDaemon方法的含义，这基本和join是相反的。此外，还有个要特别注意的：必须在start() 方法调用之前设置，如果不设置为守护线程，程序会被无限挂起，只有等待了所有线程结束它才结束。

### 线程锁

在多线程处理任务的时候，在同时操作一个数据的时候可能会造成脏数据，这时候就出现了锁的概念，也就是有一个线程在操作该数据的时候，就把该数据锁上，防止别的线程操作，操作完了再释放锁。  
一个锁是对于一个资源而言的，每个资源可对应一个锁，即可以存在多个资源锁。  
示例：

```python3
import threading
import time

n = 0

class MyThread(threading.Thread):
    def __init__(self):
        threading.Thread.__init__(self)

    def run(self):
        global n, lock
        time.sleep(1)
        if lock.acquire():
            print(n, self.name)
            n += 1
            lock.release()

if "__main__" == __name__:
    n = 1
    ThreadList = []
    lock = threading.Lock()
    for i in range(1, 200):
        t = MyThread()
        ThreadList.append(t)
    for t in ThreadList:
        t.start()
    for t in ThreadList:
        t.join()
```

这种类型的加锁可能会导致死锁发生，Threading模块中，也有一个类，RLock，称之为可重入锁。该锁对象内部维护着一个Lock和一个counter对象。counter对象记录了acquire的次数，使得资源可以被多次require。最后，当所有RLock被release后，其他线程才能获取资源。在同一个线程中，RLock.acquire可以被多次调用，利用该特性，可以解决部分死锁问题。

### event方法

该方法的具体用法是给线程设置红绿灯，红灯表示停，绿灯表示运行。比如等待输入。
示例：

```python3
import threading
import time


def do(event):
    print('start')
    event.wait()  # 红灯，所有线程执行都这里都在等待
    print('end')

event_obj = threading.Event()  # 创建一个事件

for i in range(10):  # 创建10个线程
    t = threading.Thread(target=do, args=(event_obj,))
    t.start()

time.sleep(5)

event_obj.clear()  # 让灯变红，默认也是红的，阻塞所有线程运行
data = input('请输入要：')
if data == 'True':
    event_obj.set()  # 变绿灯，可以运行
```

## multiprocessing

由于GIL的存在，如果想要充分地使用多核CPU的资源，在python中大部分情况需要使用多进程（并发执行）。multiprocessing支持子进程、通信和共享数据、执行不同形式的同步，提供了Process、Queue、Pipe、Lock等组件。  
一般计算密集型应用使用多进程（使用多个CPU）。与threading.Thread类似，它可以利用multiprocessing.Process对象来创建一个进程。该进程可以运行在Python程序内部编写的函数。该Process对象与Thread对象的用法相同，也有start(), run(), join()的方法。此外multiprocessing包中也有Lock/Event/Semaphore/Condition类 (这些对象可以像多线程那样，通过参数传递给各个进程)，用以同步进程，其用法与threading包中的同名类一致。所以，multiprocessing的很大一部份与threading使用同一套API，只不过换到了多进程的情境。  
进程优点：同时利用多个CPU，能够同时进行多个操作  
进程缺点：耗费资源（每个进程有单独的内存空间）  
进程不是越多越好，一般：进程数=CPU数  
在使用这些共享API的时候，要注意以下几点：

+ 在UNIX平台上，当某个进程终结之后，该进程需要被其父进程调用wait，否则进程成为僵尸进程(Zombie)。所以，有必要对每个Process对象调用join()方法 (实际上等同于wait)。对于多线程来说，由于只有一个进程，所以不存在此必要性。
+ multiprocessing提供了threading包中没有的IPC(比如Pipe和Queue)，效率上更高。应优先考虑Pipe和Queue，避免使用Lock/Event/Semaphore/Condition等同步方式 (因为它们占据的不是用户进程的资源)。
+ 多进程应该避免共享资源。在多线程中，可以比较容易地共享资源，比如使用全局变量或者传递参数。在多进程情况下，由于每个进程有自己独立的内存空间，以上方法并不合适。此时可以通过共享内存和Manager的方法来共享资源。但这样做提高了程序的复杂度，并因为同步的需要而降低了程序的效率。
+ window系统下，需要注意的是要想启动一个子进程，必须加上那句if __name__ == "main"，进程相关的要写在这句下面。
+ Process.PID中保存有PID，如果进程还没有start()，则PID为None。

简单多进程示例：  
方法一：直接传入要运行的方法/函数

```python3
from multiprocessing import Process
import time

def foo(i):
    print('say hi', i)

if __name__ == '__main__':
    for i in range(10):
        p = Process(target=foo, args=(i,))
        p.start()
```

方法二：从Process继承并覆盖run()

```python3
rom multiprocessing import Process
import time

class MyProcess(Process):
    def __init__(self, arg):
        super(MyProcess, self).__init__()
        self.arg = arg

    def run(self):
        print('say hi', self.arg)
        time.sleep(1)

if __name__ == '__main__':
    for i in range(10):
        p = MyProcess(i)
        p.start()
```

### Process类

构造方法：  
Process([group [, target [, name [, args [, kwargs]]]]])

+ group: 线程组，目前还没有实现，库引用中提示必须是None
+ target: 要执行的方法
+ name: 进程名
+ args/kwargs: 要传入方法的参数。

实例方法：

+ is_alive()：返回进程是否在运行
+ join([timeout])：阻塞当前上下文环境的进程，直到调用此方法的进程终止或到达指定的timeout（可选参数）
+ start()：进程准备就绪，等待CPU调度
+ run()：strat()调用run方法，如果实例进程时未制定传入target，这star执行t默认run()方法。
+ terminate()：不管任务是否完成，立即停止工作进程

属性：

+ authkey
+ daemon：和线程的setDeamon功能一样
+ exitcode(进程在运行时为None、如果为–N，表示被信号N结束）
+ name：进程名字。
+ pid：进程号。

### Pool类

进程池内部维护一个进程序列，当使用时，则去进程池中获取一个进程，如果进程池序列中没有可供使用的进进程，那么程序就会等待，直到进程池中有可用进程为止。进程池设置最好等于CPU核心数量。  
构造方法：  
Pool([processes[, initializer[, initargs[, maxtasksperchild[, context]]]]])

+ processes ：使用的工作进程的数量，如果processes是None那么使用 os.cpu_count()返回的数量。
+ initializer： 如果initializer是None，那么每一个工作进程在开始的时候会调用initializer(*initargs)。
+ maxtasksperchild：工作进程退出之前可以完成的任务数，完成后用一个新的工作进程来替代原进程，来让闲置的资源被释放。maxtasksperchild默认是None，意味着只要Pool存在工作进程就会一直存活。
+ context: 用在制定工作进程启动时的上下文，一般使用 multiprocessing.Pool() 或者一个context对象的Pool()方法来创建一个池，两种方法都适当的设置了context
  
实例方法：

+ apply(func[, args[, kwds]])：同步进程池
+ apply_async(func[, args[, kwds[, callback[, error_callback]]]]) ：异步进程池
+ close() ： 关闭进程池，阻止更多的任务提交到pool，待任务完成后，工作进程会退出。
+ terminate() ： 结束工作进程，不在处理未完成的任务
+ join() : wait工作线程的退出，在调用join()前，必须调用close() or terminate()。这样是因为被终止的进程需要被父进程调用wait（join等价与wait），否则进程会成为僵尸进程。pool.join()必须使用在

异步进程池示例：  

```python3
from multiprocessing import Pool
import time

def Foo(i):
    time.sleep(2)
    return i + 100

def Bar(arg):
    print(arg)

if __name__ == '__main__':
    t_start = time.time()
    pool = Pool(5)

    for i in range(10):
        # 维持执行的进程总数为processes，当一个进程执行完毕后会添加新的进程进去
        pool.apply_async(func=Foo, args=(i,), callback=Bar)

    pool.close()
    pool.join()  # 进程池中进程执行完毕后再关闭，如果注释，那么程序直接关闭。
    pool.terminate()
    t_end = time.time()
    t = t_end-t_start
    print('the program time is :%s' % t)
```

同步进程池示例：  

```python3
from multiprocessing import Process, Pool
import time


def Foo(i):
    time.sleep(1)
    print(i + 100)


if __name__ == '__main__':
    t_start = time.time()
    pool = Pool(5)

    for i in range(10):
        pool.apply(Foo, (i,))

    pool.close()
    pool.join()  # 进程池中进程执行完毕后再关闭，如果注释，那么程序直接关闭。
    t_end = time.time()
    t = t_end-t_start
    print('the program time is :%s' % t)
```

异步进程池使用get()方法获得进程执行结果值：  

```python3
from multiprocessing import Pool
import time


def Foo(i):
    time.sleep(2)
    return i + 100


def Bar(arg):
    return arg


if __name__ == '__main__':
    res_list = []
    t_start = time.time()
    pool = Pool(5)

    for i in range(10):
        res = pool.apply_async(func=Foo, args=(i,), callback=Bar)
        res_list.append(res)

    pool.close()
    pool.join()
    for res in res_list:
        print(res.get())
    t_end = time.time()
    t = t_end-t_start
    print('the program time is :%s' % t)
```

### 进程数据共享

进程各自持有一份数据，默认无法共享数据。可以使用Manager或第三方应用作为桥梁来共享数据。

## concurrent.futures

Python标准库提供了threading和multiprocessing模块编写相应的多线程/多进程代码，但是当项目达到一定的规模，频繁创建/销毁进程或者线程是非常消耗资源的，这个时候就要编写线程池/进程池，以空间换时间。但从Python3.2开始，标准库提供了concurrent.futures模块，它提供了ThreadPoolExecutor和ProcessPoolExecutor两个类，实现了对threading和multiprocessing的进一步抽象，对编写线程池/进程池提供了直接的支持。

### Executor和Future

+ concurrent.futures模块的基础是Exectuor，Executor是一个抽象类，它不能被直接使用。但是它提供的两个子类ThreadPoolExecutor和ProcessPoolExecutor却是非常有用，两者分别被用来创建线程池和进程池的代码。可以将相应的tasks直接放入线程池/进程池，不需要维护Queue来操心死锁的问题，线程池/进程池会自动帮我们调度。
+ Future这个概念可以把它理解为一个在未来完成的操作，这是异步编程的基础，传统编程模式下比如操作queue.get的时候，在等待返回结果之前会产生阻塞，cpu不能让出来做其他事情，而Future的引入帮助我们在等待的这段时间可以完成其他的操作。

### 使用submit来操作线程池/进程池

线程池示例：  

```python3
# 线程池：
from concurrent.futures import ThreadPoolExecutor
import urllib.request
URLS = ['http://www.163.com', 'https://www.baidu.com/', 'https://github.com/']


def load_url(url):
    with urllib.request.urlopen(url, timeout=60) as conn:
        print('%r page is %d bytes' % (url, len(conn.read())))


executor = ThreadPoolExecutor(max_workers=3)

for url in URLS:
    future = executor.submit(load_url, url)
    print(future.done())

print('主线程')
```

使用submit方法来往线程池中加入一个task，submit返回一个Future对象。由于线程池异步提交了任务，主线程并不会等待线程池里创建的线程执行完毕，所以执行了print('主线程')，相应的线程池中创建的线程并没有执行完毕，故future.done()返回结果为False。  
进程池示例：  

```python3
# 进程池
from concurrent.futures import ProcessPoolExecutor
import urllib.request
URLS = ['http://www.163.com', 'https://www.baidu.com/', 'https://github.com/']

def load_url(url):
    with urllib.request.urlopen(url, timeout=60) as conn:
        print('%r page is %d bytes' % (url, len(conn.read())))

executor = ProcessPoolExecutor(max_workers=3)
if __name__ == '__main__':  # 要加main

    for url in URLS:
        future = executor.submit(load_url, url)
        print(future.done())
    print('主线程')
```

### 使用map来操作线程池/进程池

除了submit，Exectuor还提供了map方法。  
示例：

```python3
from concurrent.futures import ThreadPoolExecutor
import urllib.request
URLS = ['http://www.163.com', 'https://www.baidu.com/', 'https://github.com/']

def load_url(url):
    with urllib.request.urlopen(url, timeout=60) as conn:
        print('%r page is %d bytes' % (url, len(conn.read())))

executor = ThreadPoolExecutor(max_workers=3)

executor.map(load_url, URLS)

print('主线程')
```

map是按照URLS列表元素的顺序返回的，并且写出的代码更加简洁直观。

### wait方法

wait方法接会返回一个tuple(元组)，tuple中包含两个set(集合)，一个是completed(已完成的)另外一个是uncompleted(未完成的)。使用wait方法的一个优势就是获得更大的自由度，它接收三个参数FIRST_COMPLETED, FIRST_EXCEPTION 和ALL_COMPLETE，默认设置为ALL_COMPLETED。  
如果采用默认的ALL_COMPLETED，程序会阻塞直到线程池里面的所有任务都完成，再执行主线程。  
示例：  

```python3
from concurrent.futures import ThreadPoolExecutor, wait, as_completed
import urllib.request
URLS = ['http://www.163.com', 'https://www.baidu.com/', 'https://github.com/']

def load_url(url):
    with urllib.request.urlopen(url, timeout=60) as conn:
        print('%r page is %d bytes' % (url, len(conn.read())))

executor = ThreadPoolExecutor(max_workers=3)

f_list = []
for url in URLS:
    future = executor.submit(load_url, url)
    f_list.append(future)
print(wait(f_list))

print('主线程')
```

如果采用FIRST_COMPLETED参数，程序并不会等到线程池里面所有的任务都完成。  
示例：

```python3
from concurrent.futures import ThreadPoolExecutor, wait, as_completed
import urllib.request
URLS = ['http://www.163.com', 'https://www.baidu.com/', 'https://github.com/']

def load_url(url):
    with urllib.request.urlopen(url, timeout=60) as conn:
        print('%r page is %d bytes' % (url, len(conn.read())))

executor = ThreadPoolExecutor(max_workers=3)

f_list = []
for url in URLS:
    future = executor.submit(load_url, url)
    f_list.append(future)
print(wait(f_list, return_when='FIRST_COMPLETED'))

print('主线程')
```

线程池/进程池应用：  

```python3
from concurrent.futures import ThreadPoolExecutor, ProcessPoolExecutor
import requests
import time
import os

def get_page(url):
    print('<%s> is getting [%s]' % (os.getpid(), url))
    response = requests.get(url)
    if response.status_code == 200:  # 200代表状态：下载成功了
        return {'url': url, 'text': response.text}

def parse_page(res):
    res = res.result()
    print('<%s> is getting [%s]' % (os.getpid(), res['url']))
    with open('db.txt', 'a') as f:
        parse_res = 'url:%s size:%s\n' % (res['url'], len(res['text']))
        f.write(parse_res)

if __name__ == '__main__':
    # p = ThreadPoolExecutor()
    p = ProcessPoolExecutor()
    l = [
        'http://www.baidu.com',
        'http://www.baidu.com',
        'http://www.baidu.com',
        'http://www.baidu.com',
    ]
    for url in l:
        # 这里的回调函数拿到的是一个对象。得先把返回的res得到一个结果。即在前面加上一个res.result()，谁好了谁就去掉回调函数也是一种编程思想。不仅开线程池用，进线程池也用
        res = p.submit(get_page, url).add_done_callback(parse_page)
    p.shutdown()  # 相当于进程池里的close和join
    print('主', os.getpid())
```

## logging日志库

logging模块是Python内置的标准模块，主要用于输出运行日志，可以设置输出日志的等级、日志保存路径、日志文件回滚等。  

### 基本使用（控制台输出）

示例：  

```python3
import logging

logging.basicConfig(level=logging.INFO,
                    format='%(asctime)s - %(name)s - %(levelname)s - %(message)s')
logger = logging.getLogger(__name__)

logger.info('start this!')
logger.debug('this is debug!')
logger.warning('no.it is a waring!')
logger.error('bad,it is error!')
logger.info('ok,it is end!')
```

logging中可以选择很多消息级别，如debug、info、warning、error以及critical。通过赋予logger或者handler不同的级别，开发者就可以只输出错误信息到特定的记录文件，或者在调试时只记录调试信息。  
注：当消息级别设置为INFO时，debug消息是不输出的。

logging.basicConfig函数各参数含义：

+ filename：指定日志文件名
+ filemode：和file函数意义相同，指定日志文件的打开模式，'w'或者'a'
+ format：指定输出的格式和内容
+ datefmt：指定时间格式，同time.strftime()
+ level：设置日志级别，默认为logging.WARNNING
+ stream：指定将日志的输出流，可以指定输出到sys.stderr，sys.stdout或者文件，默认输出到sys.stderr，当stream和filename同时指定时，stream被忽略

format参数的值：  

+ %(levelno)s：打印日志级别的数值
+ %(levelname)s：打印日志级别的名称
+ %(pathname)s：打印当前执行程序的路径，其实就是sys.argv[0]
+ %(filename)s：打印当前执行程序名
+ %(funcName)s：打印日志的当前函数
+ %(lineno)d：打印日志的当前行号
+ %(asctime)s：打印日志的时间
+ %(thread)d：打印线程ID
+ %(threadName)s：打印线程名称
+ %(process)d：打印进程ID
+ %(message)s：打印日志信息

### 将日志写入到文件

设置logging，创建一个FileHandler，并对输出消息的格式进行设置，将其添加到logger，然后将日志写入到指定的文件中。  
示例：

```python3
import logging

logger = logging.getLogger(__name__)
logger.setLevel(level=logging.INFO)

handler = logging.FileHandler(filename='1.txt')
handler.setLevel(logging.INFO)
formatter = logging.Formatter(
    '%(asctime)s - %(name)s - %(levelname)s - %(message)s')
handler.setFormatter(formatter)

logger.addHandler(handler)

logger.info('start this!')
logger.debug('this is debug!')
logger.warning('no.it is a waring!')
logger.error('bad,it is error!')
logger.info('ok,it is end!')
```

### 将日志写入到文件并在控制台打印

示例：

```python3
import logging

logger = logging.getLogger(__name__)
logger.setLevel(level=logging.INFO)

handler = logging.FileHandler(filename='1.txt')
handler.setLevel(logging.INFO)
formatter = logging.Formatter(
    '%(asctime)s - %(name)s - %(levelname)s - %(message)s')
handler.setFormatter(formatter)

console = logging.StreamHandler()
console.setLevel(logging.INFO)
console.setFormatter(formatter)

logger.addHandler(handler)
logger.addHandler(console)

logger.info('start this!')
logger.debug('this is debug!')
logger.warning('no.it is a waring!')
logger.error('bad,it is error!')
logger.info('ok,it is end!')
```

logging有一个日志处理的主对象，其他处理方式都是通过addHandler添加进去，logging中包含的handler主要有如下几种：  

+ StreamHandler：logging.StreamHandler。日志输出到流，可以是sys.stderr，sys.stdout或者文件
+ FileHandler：logging.FileHandler。日志输出到文件
+ BaseRotatingHandler：logging.handlers.BaseRotatingHandler。基本的日志回滚方式
+ RotatingHandler：logging.handlers.RotatingHandler。日志回滚方式，支持日志文件最大数量和日志文件回滚
+ TimeRotatingHandler：logging.handlers.TimeRotatingHandler。日志回滚方式，在一定时间区域内回滚日志文件
+ SocketHandler：logging.handlers.SocketHandler。远程输出日志到TCP/IP sockets
+ DatagramHandler：logging.handlers.DatagramHandler。远程输出日志到UDP sockets
+ SMTPHandler：logging.handlers.SMTPHandler。远程输出日志到邮件地址
+ SysLogHandler：logging.handlers.SysLogHandler。日志输出到syslog
+ NTEventLogHandler：logging.handlers.NTEventLogHandler。远程输出日志到Windows NT/2000/XP的事件日志
+ MemoryHandler：logging.handlers.MemoryHandler。日志输出到内存中的指定buffer
+ HTTPHandler：logging.handlers.HTTPHandler。通过"GET"或者"POST"远程输出到HTTP服务器

### 日志回滚

使用RotatingFileHandler
示例：  

```python3
from logging.handlers import RotatingFileHandler

logger = logging.getLogger(__name__)
logger.setLevel(level = logging.INFO)
#定义一个RotatingFileHandler，最多备份3个日志文件，每个日志文件最大1K
rHandler = RotatingFileHandler("log.txt",maxBytes = 1*1024,backupCount = 3)
rHandler.setLevel(logging.INFO)
formatter = logging.Formatter('%(asctime)s - %(name)s - %(levelname)s - %(message)s')
rHandler.setFormatter(formatter)

logger.addHandler(rHandler)
```

### 消息等级

+ FATAL：致命错误
+ CRITICAL：特别糟糕的事情，如内存耗尽、磁盘空间为空，一般很少使用
+ ERROR：发生错误时，如IO操作失败或者连接问题
+ WARNING：发生很重要的事件，但是并不是错误时，如用户登录密码错误
+ INFO：处理请求或者状态变化等日常事务
+ DEBUG：调试过程中使用DEBUG等级，如算法中每个循环的中间状态

### 捕获traceback

ython中的traceback模块被用于跟踪异常返回信息，可以在logging中记录下traceback。  
示例：  

```python3
try:
    open("sklearn.txt","rb")
except (SystemExit,KeyboardInterrupt):
    raise
except Exception:
    logger.error("Faild to open sklearn.txt from logger.error",exc_info = True)
```

也可以使用logger.exception(msg,_args)，它等价于logger.error(msg,exc_info = True,_args)：  
可以将  
logger.error("Faild to open sklearn.txt from logger.error",exc_info = True)
替换为  
logger.exception("Failed to open sklearn.txt from logger.exception")

### 多模块使用logging

首先是在主文件中配置logger：  
logger = logging.getLogger("mainModule")  
然后在子模块中直接引用名称，不需重新配置：  
sub_logger = logging.getLogger("mainModule.sub")  
还有下级日志记录器可以继续添加：  
next_logger = logging.getLogger("mainModule.sub.app")

实际开发一个application时，首先可以通过logging配置文件编写好这个application所对应的配置，可以生成一个根logger，如'PythonAPP'，然后在主函数中通过fileConfig加载logging配置，接着在application的其他地方、不同的模块中，可以使用根logger的子logger，如'PythonAPP.Core'，'PythonAPP.Web'来进行log，而不需要反复的定义和配置各个模块的logger。  

### 通过JSON或者YAML文件配置logging模块

尽管可以在Python代码中配置logging，但是这样并不够灵活，最好的方法是使用一个配置文件来配置。在Python 2.7及以后的版本中，可以从字典中加载logging配置，也就意味着可以通过JSON或者YAML文件加载日志的配置。

## itertools

itertools用于高效循环的迭代函数集合。包含一些使用功能。

### 无限迭代器：

迭代器|结果|示例
--|:--:|--:
count(start, [step])|start, start+step, start+2*step, ...|count(10) --> 10 11 12 13 14 ...
cycle(p)|p0, p1, ... plast, p0, p1, ...|cycle('ABCD') --> A B C D A B C D ...
repeat(elem [,n])|elem, elem, elem, ...无休止地或多达n次|repeat(10, 3) --> 10 10 10

### 处理输入序列迭代器：

迭代器|结果|示例
--|:--:|--:
chain(p, q, ...)|p0, p1, ... plast, q0, q1, ...|chain('ABC', 'DEF') --> A B C D E F
compress(data, selectors)|(d[0] if s[0]), (d[1] if s[1]), ...|compress('ABCDEF', [1,0,1,0,1,1]) --> A C E F
dropwhile(pred, seq)|seq[n], seq[n+1],当pred失败时开始迭代|dropwhile(lambda x: x<5, [1,4,6,4,1]) --> 6 4 1
groupby(iterable[, keyfunc])|sub-iterators grouped by value of keyfunc(v)
ifilter(pred, seq)|elements of seq where pred(elem) is True|ifilter(lambda x: x%2, range(10)) --> 1 3 5 7 9
ifilterfalse(pred, seq)|elements of seq where pred(elem) is False|ifilterfalse(lambda x: x%2, range(10)) --> 0 2 4 6 8
islice(seq, [start,] stop [, step])|elements from seq[start:stop:step]|islice('ABCDEFG', 2, None) --> C D E F G
imap(func, p, q, ...)|func(p0, q0), func(p1, q1), ...|imap(pow, (2,3,10), (5,2,3)) --> 32 9 1000
starmap(func, seq )|func(*seq[0]), func(*seq[1]), ...|starmap(pow, [(2,5), (3,2), (10,3)]) --> 32 9 1000
tee(it, n)|it1, it2 , ... itn splits one iterator into n
takewhile(pred, seq)|seq[0], seq[1], until pred fails|takewhile(lambda x: x<5, [1,4,6,4,1]) --> 1 4
izip(p, q, ...)|(p[0], q[0]), (p[1], q[1]), ...|izip('ABCD', 'xy') --> Ax By
izip_longest(p, q, ...)|(p[0], q[0]), (p[1], q[1]), ...|izip_longest('ABCD', 'xy', fillvalue='-') --> Ax By C- D-

### 组合生成器：

迭代器|结果
--:|--:
product(p, q, ... [repeat=1])|cartesian product, equivalent to a nested for-loop
permutations(p[, r])|r-length tuples, all possible orderings, no repeated elements
combinations(p, r)|r-length tuples, in sorted order, no repeated elements
combinations_with_replacement(p, r)|r-length tuples, in sorted order, with repeated elements
product('ABCD', repeat=2)|AA AB AC AD BA BB BC BD CA CB CC CD DA DB DC DD
permutations('ABCD', 2)|AB AC AD BA BC BD CA CB CD DA DB DC
combinations('ABCD', 2)|AB AC AD BC BD CD
combinations_with_replacement('ABCD', 2)|AA AB AC AD BB BC BD CC CD DD

## functools

functools，用于高阶函数：指那些作用于函数或者返回其它函数的函数，通常只要是可以被当做函数调用的对象就是这个模块的目标。  
主要包括：

+ functools.partial
+ functool.update_wrapper
+ functool.wraps
+ functools.reduce
+ functools.cmp_to_key
+ functools.total_ordering

### functools.partial

functools.partial 通过包装手法，允许"重新定义"函数签名。  
用一些默认参数包装一个可调用对象,返回结果是可调用对象，并且可以像原始对象一样对待冻结部分函数位置函数或关键字参数，以简化函数，使其可以用更少更灵活的函数参数调用。  
内部原理：  

```python3
def partial(func, *args, **keywords):
    def newfunc(*fargs, **fkeywords):
        newkeywords = keywords.copy()
        newkeywords.update(fkeywords)
        # 合并，调用原始函数，此时用了partial的参数
        return func(*(args + fargs), **newkeywords)
    newfunc.func = func
    newfunc.args = args
    newfunc.keywords = keywords
    return newfunc
```

示例：  
urlunquote_1 = functools.partial(urlunquote, encoding='latin1')  
当调用 urlunquote_1(args, *kargs)相当于调用urlunquote(args, *kargs, encoding='latin1')

### functool.update_wrapper

默认partial对象没有__name__和__doc__, 这种情况下，对于装饰器函数非常难以debug。所以使用update_wrapper()，将他们从原始对象拷贝或加入到现有partial对象。  
它可以把原始函数的__name__、module、__doc__和 __dict__都复制到封装函数中去(模块级别常量WRAPPER_ASSIGNMENTS, WRAPPER_UPDATES)。  
这个函数主要用在装饰器函数中，装饰器返回函数反射得到的是包装函数的函数定义而不是原始函数定义：  

```python3
from functools import update_wrapper

def wrap(func):
    def call_it(*args, **kwargs):
        """wrap func: call_it"""
        print('before call')
        return func(*args, **kwargs)
    return call_it

@wrap
def hello():
    """say hello"""
    print('hello world')

def wrap2(func):
    def call_it(*args, **kwargs):
        """wrap func: call_it2"""
        print('before call')
        return func(*args, **kwargs)
    return update_wrapper(call_it, func)

@wrap2
def hello2():
    """test hello"""
    print('hello world2')

if __name__ == '__main__':
    hello()
    print(hello.__name__)
    print(hello.__doc__)

    print()
    hello2()
    print(hello2.__name__)
    print(hello2.__doc__)
```

### functool.wraps

调用函数装饰器partial(update_wrapper, wrapped=wrapped, assigned=assigned, updated=updated)的简写。  
示例：

```python3
from functools import wraps

def wrap3(func):
    @wraps(func)
    def call_it(*args, **kwargs):
        """wrap func: call_it2"""
        print('before call')
        return func(*args, **kwargs)
    return call_it

@wrap3
def hello3():
    """test hello 3"""
    print('hello world3')
```

### functools.reduce

functools.reduce(function, iterable[, initializer])等同于内置函数reduce()，用这个的原因是使代码更兼容python3。

### functools.cmp_to_key

将老式比较函数转换成key函数，用在接受key函数的方法中如：sorted(), min(), max(), heapq.nlargest(), heapq.nsmallest(), itertools.groupby()。  
一个比较函数，接收两个参数，小于返回负数，等于返回0，大于返回整数。key函数，接收一个参数，返回一个表明该参数在期望序列中的位置：  
sorted(iterable, key=cmp_to_key(locale.strcoll))  # locale-aware sort order

### functools.total_ordering

functools.total_ordering(cls)这个装饰器是在python2.7的时候加上的，它是针对某个类如果定义了__lt__、le、gt、__ge__这些方法中的至少一个，使用该装饰器，则会自动的把其他几个比较函数也实现在该类中。

```python3
import functools

@functools.total_ordering
class Student:
    def __eq__(self, other):
        return ((self.lastname.lower(), self.firstname.lower()) ==
                (other.lastname.lower(), other.firstname.lower()))

    def __lt__(self, other):
        return ((self.lastname.lower(), self.firstname.lower()) <
                (other.lastname.lower(), other.firstname.lower()))

print(dir(Student))
```

结果：

```python3
['__doc__', '__eq__', '__ge__', '__gt__', '__le__', '__lt__', '__module__']
```

## queue

queue模块实现了多生产者，多消费者的队列。当要求信息必须在多线程间安全交换，这个模块在线程编程时非常有用。Queue模块实现了所有要求的锁机制。当然进程有单独的queue模块。  
这个模块实现了三种类型的queue，区别仅仅在于进去和取出的位置：

+ 在一个FIFO（First In，First Out）队列中，先进先出
+ 在一个LIFO（Last In First Out）的队列中，后进先出（操作起来跟stack一样）
+ priority队列，有序保存，优先级最低的先出来。

### 内容：

+ class queue.Queue(maxsize=0)：构造一个FIFO队列，maxsize可以限制队列的大小。如果队列的大小达到了队列的上限，就会加锁，加入就会阻塞，直到队列的内容被消费掉。maxsize的值小于等于0，那么队列的尺寸就是无限制的
+ class queue.LifoQueue(maxsize = 0)：构造一个Lifo队列
+ class PriorityQueue(maxsize = 0)：优先级最低的先出去，优先级最低的一般使用sorted(list(entries))[0])。典型加入的元素是一个元祖(优先级, 数据)
+ queue.empty异常：只有非阻塞的时候，队列为空，取数据才会报异常
+ queue.Full异常：只有非阻塞的时候，队列满了，继续放数据才会出现异常

### 队列对象的方法：

+ Queue.qsize()：返回queue的近似值。注意：qsize>0 不保证(get)取元素不阻塞。qsize< maxsize不保证(put)存元素不会阻塞
+ Queue.empty():判断队列是否为空。和上面一样注意
+ Queue.full():判断是否满了。和上面一样注意
+ Queue.put(item, block=True, timeout=None): 往队列里放数据。如果满了的话，blocking = False 直接报Full异常。如果blocking = True，就是等一会，timeout必须为0或正数。None为一直等下去，0为不等，正数n为等待n秒还不能存入，报Full异常
+ Queue.put_nowait(item)：往队列里存放元素，不等待
+ Queue.get(item, block=True, timeout=None): 从队列里取数据。如果为空的话，blocking = False 直接报empty异常。如果blocking = True，就是等一会，timeout必须为0或正数。None为一直等下去，0为不等，正数n为等待n秒还不能读取，报empty异常
+ Queue.get_nowait(item)：从队列里取元素，不等待
+ Queue.queue.clear()：清空队列

下面两个方法跟踪入队的任务是否被消费者daemon进程完全消费：

+ Queue.task_done()：表示队列中某个元素被消费进程使用，消费结束发送的信息。每个get()方法会拿到一个任务，其随后调用task_done()表示这个队列，这个队列的线程的任务完成。就是发送消息，告知完成了！如果当前的join()处于阻塞状态，当前的所有元素执行后都会重启（意味着收到加入queue的每一个对象的task_done()调用的信息）。如果调用的次数操作比放入队列的items的个数多的话，会触发ValueError异常。
+ Queue.join()：一直阻塞直到队列中的所有元素都被取出和执行。未完成的个数，只要有元素添加到queue中就会增加。未完成的个数，只要消费者线程调用task_done()表明其被取走，其调用结束。当未完成任务的计数等于0，join()就会不阻塞。

## NumPy

NumPy(Numerical Python) 是 Python 语言的一个扩展程序库，支持大量的维度数组与矩阵运算，此外也针对数组运算提供大量的数学函数库。  
NumPy 是一个运行速度非常快的数学库，主要用于数组计算，包含：

+ 一个强大的N维数组对象 ndarray
+ 广播功能函数
+ 整合 C/C++/Fortran 代码的工具
+ 线性代数、傅里叶变换、随机数生成等功能

NumPy通常与SciPy（Scientific Python）和Matplotlib（绘图库）一起使用，这种组合广泛用于替代 MatLab，是一个强大的科学计算环境，有助于通过Python学习数据科学或者机器学习。  
SciPy是一个开源的Python算法库和数学工具包。SciPy 包含的模块有最优化、线性代数、积分、插值、特殊函数、快速傅里叶变换、信号处理和图像处理、常微分方程求解和其他科学与工程中常用的计算。  
Matplotlib是Python编程语言及其数值数学扩展包NumPy的可视化操作界面。

### Ndarray对象

是其N维数组对象，它是一系列同类型数据的集合，以0为下标开始进行集合中元素的索引。ndarray 对象是用于存放同类型元素的多维数组、ndarray 中的每个元素在内存中都有相同存储大小的区域。
创建一个ndarray只需调用NumPy的 array 函数即可：  
numpy.array(object, dtype=None, copy=True, order=None, subok=False, ndmin=0)  
参数说明：  
名称|描述
--:|--:
object|数组或嵌套的数列
dtype|数组元素的数据类型，可选
copy|对象是否需要复制，可选
order|创建数组的样式，C为行方向，F为列方向，A为任意方向（默认）
subok|默认返回一个与基类类型一致的数组
ndmin|指定生成数组的最小维度

示例（底层ndarray构造器来创建）：  

```python3
import numpy as np
a = np.array([[1,  2],  [3,  4]])
print(a)
```

除了底层方法构建还有以下几种方式：  

#### numpy.empty

numpy.empty 方法用来创建一个指定形状（shape）、数据类型（dtype）且未初始化的数组：  
numpy.empty(shape, dtype = float, order = 'C')  
参数说明：  
名称|描述
--:|--:
shape|数组形状
dtype|数据类型，可选
order|有"C"和"F"两个选项,分别代表，行优先和列优先，在计算机内存中的存储元素的顺序

#### numpy.zeros

创建指定大小的数组，数组元素以 0 来填充：  
numpy.zeros(shape, dtype = float, order = 'C')  
参数说明同上。

#### numpy.ones

创建指定形状的数组，数组元素以 1 来填充：  
numpy.ones(shape, dtype = None, order = 'C')  

从已有的数组创建数组：  

#### numpy.asarray

numpy.asarray类似numpy.array，但numpy.asarray参数只有三个，比 numpy.array 少两个：  
numpy.asarray(a, dtype = None, order = None)  

#### numpy.frombuffer

numpy.frombuffer 用于实现动态数组。接受buffer输入参数，以流的形式读入转化成ndarray 对象：  
numpy.frombuffer(buffer, dtype = float, count = -1, offset = 0)  
注意：buffer 是字符串的时候，Python3 默认 str 是 Unicode 类型，所以要转成 bytestring 在原 str 前加上 b。
参数说明：  
名称|描述
--:|--:
buffer|可以是任意对象，会以流的形式读入
dtype|返回数组的数据类型，可选
count|读取的数据数量，默认为-1，读取所有数据
offset|取的起始位置，默认为0

#### numpy.fromiter

从可迭代对象中建立 ndarray 对象，返回一维数组：  
numpy.fromiter(iterable, dtype, count=-1)  

以下是以数值范围来创建数组。  

#### numpy.arange

numpy包中的使用arange函数创建数值范围并返回 ndarray 对象，函数格式如下：  
umpy.arange(start, stop, step, dtype)  
根据 start 与 stop 指定的范围以及 step 设定的步长，生成一个 ndarray。  

#### numpy.linspace

用于创建一个一维数组，数组是一个等差数列构成的，格式如下：  
np.linspace(start, stop, num=50, endpoint=True, retstep=False, dtype=None)  
参数说明：  
名称|描述
--:|--:
start|序列的起始值
stop|序列的终止值，如果endpoint为true，该值包含于数列中
num|要生成的等步长的样本数量，默认为50
endpoint|该值为 ture 时，数列中中包含stop值，反之不包含，默认是True。
retstep|如果为 True 时，生成的数组中会显示间距，反之不显示。
dtype|ndarray 的数据类型

#### numpy.logspace

用于创建一个于等比数列。格式如下：  
np.logspace(start, stop, num=50, endpoint=True, base=10.0, dtype=None)  
base 参数意思是取对数的时候 log 的下标。

### 数据类型

numpy支持的数据类型比Python内置的类型要多很多，基本上可以和C语言的数据类型对应上，其中部分类型对应为 Python 内置的类型。  
数据类型对象(dtype)是用来描述与数组对应的内存区域如何使用，这依赖如下几个方面：

+ 数据的类型（整数，浮点数或者 Python 对象）
+ 数据的大小（例如， 整数使用多少个字节存储）
+ 数据的字节顺序（小端法或大端法）
+ 在结构化类型的情况下，字段的名称、每个字段的数据类型和每个字段所取的内存块的部分
+ 如果数据类型是子数组，它的形状和数据类型

字节顺序是通过对数据类型预先设定"<"或">"来决定的。"<"意味着小端法(最小值存储在最小的地址，即低位组放在最前面)。">"意味着大端法(最重要的字节存储在最小的地址，即高位组放在最前面)。  
dtype 对象是使用以下语法构造的：  
numpy.dtype(object, align, copy)

+ object - 要转换为的数据类型对象
+ align - 如果为 true，填充字段使其类似 C 的结构体
+ copy - 复制 dtype 对象 ，如果为 false，则是对内置数据类型对象的引用

### 数组属性

NumPy 的数组中比较重要 ndarray 对象属性有：

名称|说明
--:|--:
ndarray.ndim|秩，即轴（axis）的数量或维度的数量
ndarray.shape|数组的维度，对于矩阵，n 行 m 列
ndarray.size|数组元素的总个数，相当于 .shape 中 n*m 的值
ndarray.dtype|ndarray 对象的元素类型
ndarray.itemsize|ndarray 对象中每个元素的大小，以字节为单位
ndarray.flags|ndarray 对象的内存信息
ndarray.real|ndarray元素的实部
ndarray.imag|ndarray 元素的虚部
ndarray.data|包含实际数组元素的缓冲区，由于一般通过数组的索引获取元素，所以通常不需要使用这个属性

### 切片和索引

ndarray对象的内容可以通过索引或切片来访问和修改，与Python中list的切片操作一样。除了用整数和切片的索引外，数组可以由整数数组索引、布尔索引及花式索引。

#### 整数数组索引

以下实例获取数组中(0,0)，(1,1)和(2,0)位置处的元素：

```python3
import numpy as np

x = np.array([[1,  2],  [3,  4],  [5,  6]])
y = x[[0, 1, 2],  [0, 1, 0]]
print(y)
```

#### 布尔索引

布尔索引通过布尔运算（如：比较运算符）来获取符合指定条件的元素的数组:

```python3
import numpy as np

x = np.array([[0, 1, 2], [3, 4, 5], [6, 7, 8], [9, 10, 11]])
print(x[x > 5])
```

#### 花式索引

指的是利用整数数组进行索引。花式索引根据索引数组的值作为目标数组的某个轴的下标来取值。对于使用一维整型数组作为索引，如果目标是一维数组，那么索引的结果就是对应位置的元素；如果目标是二维数组，那么就是对应下标的行。花式索引跟切片不一样，它总是将数据复制到新数组中。  
传入顺序索引数组:

```python3
import numpy as np

x = np.arange(32).reshape((8, 4))
print(x[[4, 2, 1, 7]])
```

传入倒序索引数组:

```python3
import numpy as np

x = np.arange(32).reshape((8, 4))
print(x[[-4, -2, -1, -7]])
```

传入多个索引数组（要使用np.ix_）:

```python3
import numpy as np

x = np.arange(32).reshape((8, 4))
print(x[np.ix_([1, 5, 7, 2], [0, 3, 1, 2])])
```

### 广播(Broadcast)

是 numpy 对不同形状(shape)的数组进行数值计算的方式， 对数组的算术运算通常在相应的元素上进行。  
如果两个数组 a 和 b 形状相同，即满足 a.shape == b.shape，那么 a*b 的结果就是 a 与 b 数组对应位相乘。这要求维数相同，且各维度的长度相同。当运算中的 2 个数组的形状不同时，numpy 将自动触发广播机制。  
广播的规则:

+ 让所有输入数组都向其中形状最长的数组看齐，形状中不足的部分都通过在前面加1补齐。
+ 输出数组的形状是输入数组形状的各个维度上的最大值。
+ 如果输入数组的某个维度和输出数组的对应维度的长度相同或者其长度为1时，这个数组能够用来计算，否则出错。
+ 当输入数组的某个维度的长度为1时，沿着此维度运算时都用此维度上的第一组值。

对两个数组，分别比较他们的每一个维度（若其中一个数组没有当前维度则忽略），满足：

+ 数组拥有相同形状。
+ 当前维度的值相等。
+ 当前维度的值有一个是 1。

若条件不满足，抛出 "ValueError: frames are not aligned" 异常。

### 迭代数组

迭代器对象numpy.nditer提供了一种灵活访问一个或者多个数组元素的方式。迭代器最基本的任务的可以完成对数组元素的访问。  
控制遍历顺序:  

+ for x in np.nditer(a, order='F'):Fortran order，即是列序优先；
+ for x in np.nditer(a.T, order='C'):C order，即是行序优先；

修改数组中元素的值：nditer对象有另一个可选参数op_flags。默认情况下，nditer将视待迭代遍历的数组为只读对象（read-only），为了在遍历数组的同时，实现对数组元素值得修改，必须指定read-write或者write-only的模式。示例：

```python3
import numpy as np

a = np.arange(0, 60, 5)
a = a.reshape(3, 4)
for x in np.nditer(a, op_flags=['readwrite']):
    x[...] = 2*x
print(a)
```

使用外部循环：nditer类的构造器拥有flags参数，它可以接受下列值：

参数|描述
--:|--:
c_index|可以跟踪 C 顺序的索引
f_index|可以跟踪 Fortran 顺序的索引
multi-index|每次迭代可以跟踪一种索引类型
external_loop|给出的值是具有多个值的一维数组，而不是零维数组

广播迭代：如果两个数组是可广播的，nditer组合对象能够同时迭代它们。假设数组a的维度为3X4，数组b的维度为1X4，则使用以下迭代器（数组b被广播到a的大小）。示例：

```python3
import numpy as np

a = np.arange(0, 60, 5)
a = a.reshape(3, 4)
b = np.array([1,  2,  3,  4], dtype=int)
for x, y in np.nditer([a, b]):
    print("%d:%d" % (x, y), end=", ")
```

### 数组操作

#### 修改数组形状

函数|描述
--:|--:
reshape|不改变数据的条件下修改形状
flat|数组元素迭代器
flatten|返回一份数组拷贝，对拷贝所做的修改不会影响原始数组
ravel|返回展开数组

#### 翻转数组

函数|描述
--:|--:
transpose|对换数组的维度
ndarray.T|和 self.transpose() 相同
rollaxis|向后滚动指定的轴
swapaxes|对换数组的两个轴

#### 修改数组维度

函数|描述
--:|--:
broadcast|产生模仿广播的对象
broadcast_to|将数组广播到新形状
expand_dims|扩展数组的形状
squeeze|从数组的形状中删除一维条目

#### 连接数组

函数|描述
--:|--:
concatenate|连接沿现有轴的数组序列
stack|沿着新的轴加入一系列数组。
hstack|水平堆叠序列中的数组（列方向）
vstack|竖直堆叠序列中的数组（行方向）

#### 分割数组

函数|描述
--:|--:
split|将一个数组分割为多个子数组
hsplit|将一个数组水平分割为多个子数组（按列）
vsplit|将一个数组垂直分割为多个子数组（按行）

#### 数组元素的添加与删除

函数|描述
--:|--:
resize|返回指定形状的新数组
append|将值添加到数组末尾
insert|沿指定轴将值插入到指定下标之前
delete|删掉某个轴的子数组，并返回删除后的新数组
unique|查找数组内的唯一元素

### 位运算

"bitwise_" 开头的函数是位运算函数。NumPy 位运算包括以下几个函数：

函数|描述
--:|--:
bitwise_and|对数组元素执行位与操作
bitwise_or|对数组元素执行位或操作
invert|按位取反
left_shift|向左移动二进制表示的位
right_shift|向右移动二进制表示的位

### 字符串函数

函数|描述
--:|--:
add()|对两个数组的逐个字符串元素进行连接
multiply()|返回按元素多重连接后的字符串
center()|居中字符串
capitalize()|将字符串第一个字母转换为大写
title()|将字符串的每个单词的第一个字母转换为大写
lower()|数组元素转换为小写
upper()|数组元素转换为大写
split()|指定分隔符对字符串进行分割，并返回数组列表
splitlines()|返回元素中的行列表，以换行符分割
strip()|移除元素开头或者结尾处的特定字符
join()|通过指定分隔符来连接数组中的元素
replace()|使用新字符串替换字符串中的所有子字符串
decode()|数组元素依次调用str.decode
encode()|数组元素依次调用str.encode

### 数学函数

NumPy 包含大量的各种数学运算的函数，包括三角函数，算术运算的函数，复数处理函数等。  
其还包含算术函数（包含简单的加减乘除）、统计函数（用于从数组中查找最小元素，最大元素，百分位标准差和方差等）、排序函数、筛选函数等。

### 矩阵库(Matrix)

NumPy中包含了一个矩阵库numpy.matlib，该模块中的函数返回的是一个矩阵，而不是ndarray对象。一个 的矩阵是一个由行（row）列（column）元素排列成的矩形阵列。矩阵里的元素可以是数字、符号或数学式。

+ numpy.matlib.empty()：返回一个新的空矩阵
+ numpy.matlib.zeros()：创建一个以 0 填充的矩阵
+ numpy.matlib.ones()：创建一个以 1 填充的矩阵
+ numpy.matlib.eye()：返回一个单位矩阵，对角线元素为 1，其他位置为零
+ numpy.matlib.identity()：返回给定大小的单位矩阵
+ numpy.matlib.rand()：创建一个给定大小的矩阵，数据是随机填充的

### 线性代数

NumPy 提供了线性代数函数库 linalg，该库包含了线性代数所需的所有功能：

函数|描述
--:|--:
dot|两个数组的点积，即元素对应相乘。
vdot|两个向量的点积
inner|两个数组的内积
matmul|两个数组的矩阵积
determinant|数组的行列式
solve|求解线性矩阵方程
inv|计算矩阵的乘法逆矩阵

### IO

Numpy可以读写磁盘上的文本数据或二进制数据。NumPy为ndarray对象引入了一个简单的文件格式：npy。npy文件用于存储重建ndarray所需的数据、图形、dtype 和其他信息。  
常用的 IO 函数有：

+ load()和save()函数是读写文件数组数据的两个主要函数，默认情况下，数组是以未压缩的原始二进制格式保存在扩展名为.npy的文件中。
+ savze()函数用于将多个数组写入文件，默认情况下，数组是以未压缩的原始二进制格式保存在扩展名为.npz的文件中。
+ loadtxt()和savetxt( 函数处理正常的文本文件(.txt 等)

## pandas

Pandas概述：

+ Pandas是Python的一个数据分析包，该工具为解决数据分析任务而创建。
+ Pandas纳入大量库和标准数据模型，提供高效的操作数据集所需的工具。
+ Pandas提供大量能快速便捷地处理数据的函数和方法。
+ Pandas是字典形式，基于NumPy创建，让NumPy为中心的应用变得更加简单。

### 数据结构

+ Series：相当于一维数组
+ DataFrame：表格型数据结构，包含一组有序的列，每列可以是不同的值类型。DataFrame有行索引和列索引，可以看成由Series组成的字典。

### 生成数据表

首先导入pandas库，一般都会用到numpy库，所以先导入备用：

```python3
import numpy as np  
import pandas as pd  
```

导入CSV或者xlsx文件：

```python3
df = pd.DataFrame(pd.read_csv('name.csv',header=1))
df = pd.DataFrame(pd.read_excel('name.xlsx'))
```

用pandas创建数据表：

```python3
df = pd.DataFrame(
    {"id": [1001, 1002, 1003, 1004, 1005, 1006],
     "date": pd.date_range('20130102', periods=6),
     "city": ['Beijing ', 'SH', ' guangzhou ', 'Shenzhen', 'shanghai', 'BEIJING '],
     "age": [23, 44, 54, 32, 34, 32],
     "category": ['100-A', '100-B', '110-A', '110-C', '210-A', '130-F'],
     "price": [1200, np.nan, 2133, 5433, np.nan, 4432]},
    columns=['id', 'date', 'city', 'category', 'age', 'price'])
```

### 数据表信息查看

df.shape：维度查看  
df.info()：数据表基本信息（维度、列名称、数据格式、所占空间等）  
df.dtypes：每一列数据的格式  
df['B'].dtype：某一列格式  
df.isnull()：查看某一列空值  
df['B'].unique()：查看某一列的唯一值  
df.values ：查看数据表的值  
df.columns：查看列名称  
df.head()：默认前10行数据（也可输入行数）  
df.tail()：默认后10 行数据（也可输入行数）  

### 数据表清洗

用数字0填充空值：df.fillna(value=0)  
使用列prince的均值对NA进行填充：df['prince'].fillna(df['prince'].mean())  
清除city字段的字符空格：df['city']=df['city'].map(str.strip)  
大小写转换：df['city']=df['city'].str.lower()  
更改数据格式：df['price'].astype('int')  
更改列名称：df.rename(columns={'category': 'category-size'})  
删除后出现的重复值：df['city'].drop_duplicates()  
删除先出现的重复值：df['city'].drop_duplicates(keep='last')  
数据替换：df['city'].replace('sh', 'shanghai')  

### 数据预处理

示例数据：

```python3
df1 = pd.DataFrame(
    {"id": [1001, 1002, 1003, 1004, 1005, 1006, 1007, 1008],
     "gender": ['male', 'female', 'male', 'female', 'male', 'female', 'male', 'female'],
     "pay": ['Y', 'N', 'Y', 'Y', 'N', 'Y', 'N', 'Y', ],
     "m-point": [10, 12, 20, 40, 40, 40, 30, 20]})
```

数据表合并:  
df_inner=pd.merge(df,df1,how='inner')  # 匹配合并，交集  
df_left=pd.merge(df,df1,how='left')  # 左连接  
df_right=pd.merge(df,df1,how='right')  # 右连接  
df_outer=pd.merge(df,df1,how='outer')  #并集  
设置索引列：df_inner.set_index('id')  
按照索引列排序：df_inner.sort_index()  
按照特定列的值排序：df_inner.sort_values(by=['age'])  
如果prince列的值>3000，group列显示high，否则显示low：  
df_inner['group'] = np.where(df_inner['price'] > 3000,'high','low')  
对复合多个条件的数据进行分组标记：  
df_inner.loc[(df_inner['city'] == 'beijing') & (df_inner['price'] >= 4000), 'sign']=1  
对category字段的值依次进行分列，并创建数据表，索引值为df_inner的索引列，列名称为category和size：  
pd.DataFrame((x.split('-') for x in df_inner['category']),index=df_inner.index,columns=['category','size']))  
将完成分裂后的数据表和原df_inner数据表进行匹配：  
df_inner=pd.merge(df_inner,split,right_index=True, left_index=True)  

### 数据提取

主要用到的三个函数：loc,iloc和ix。

+ loc函数按标签值进行提取
+ iloc按位置进行提取
+ ix可以同时按标签和位置进行提取

按索引提取单行的数值：df_inner.loc[3]  
按索引提取区域行数值：df_inner.iloc[0:5]  
重设索引：df_inner.reset_index()  
设置日期为索引：df_inner=df_inner.set_index('date')  
提取4日之前的所有数据：df_inner[:'2013-01-04']
使用iloc按位置区域提取数据：df_inner.iloc[:3,:2] #冒号前后的数字不再是索引的标签名称，而是数据所在的位置，从0开始，前三行，前两列。  
适应iloc按位置单独提起数据：df_inner.iloc[[0,2,5],[4,5]] #提取第0、2、5行，4、5列  
使用ix按索引标签和位置混合提取数据：df_inner.ix[:'2013-01-03',:4] #2013-01-03号之前，前四列数据  
判断city列的值是否为北京：df_inner['city'].isin(['beijing'])  
判断city列里是否包含beijing和shanghai，然后将符合条件的数据提取出来：df_inner.loc[df_inner['city'].isin(['beijing','shanghai'])]  
提取前三个字符，并生成数据表：pd.DataFrame(category.str[:3])  

### 数据筛选

使用与、或、非三个条件配合大于、小于、等于对数据进行筛选，并进行计数和求和。  
使用“与”进行筛选：df_inner.loc[(df_inner['age'] > 25) & (df_inner['city'] == 'beijing'), ['id','city','age','category','gender']]  
使用“或”进行筛选：df_inner.loc[(df_inner['age'] > 25) | (df_inner['city'] == 'beijing'), ['id','city','age','category','gender']].sort(['age'])  
使用“非”条件进行筛选：df_inner.loc[(df_inner['city'] != 'beijing'), ['id','city','age','category','gender']].sort(['id'])  
对筛选后的数据按city列进行计数：df_inner.loc[(df_inner['city'] != 'beijing'), ['id','city','age','category','gender']].sort(['id']).city.count()  
使用query函数进行筛选：df_inner.query('city == ["beijing", "shanghai"]')  
对筛选后的结果按prince进行求和：df_inner.query('city == ["beijing", "shanghai"]').price.sum()

### 数据汇总

主要函数是groupby和pivote_table。  
对所有的列进行计数汇总：df_inner.groupby('city').count()  
按城市对id字段进行计数：
```df_inner.groupby('city')['id'].count()```
对两个字段进行汇总计数：
```df_inner.groupby(['city','size'])['id'].count()```
对city字段进行汇总，并分别计算prince的合计和均值：
```df_inner.groupby('city')['price'].agg([len,np.sum, np.mean])```

### 数据统计

主要是数据采样，计算标准差，协方差和相关系数。  
简单的数据采样：df_inner.sample(n=3)  
手动设置采样权重：  
weights = [0, 0, 0, 0, 0.5, 0.5]  
df_inner.sample(n=2, weights=weights)  
采样后不放回：df_inner.sample(n=6, replace=False)  
采样后放回：df_inner.sample(n=6, replace=True)  
数据表描述性统计：df_inner.describe().round(2).T #round函数设置显示小数位，T表示转置  
计算列的标准差：df_inner['price'].std()  
计算两个字段间的协方差：df_inner['price'].cov(df_inner['m-point'])  
数据表中所有字段间的协方差：df_inner.cov()  
两个字段的相关性分析：df_inner['price'].corr(df_inner['m-point']) #相关系数在-1到1之间，接近1为正相关，接近-1为负相关，0为不相关  
数据表的相关性分析：df_inner.corr()

### 数据输出

分析后的数据可以输出为xlsx格式和csv格式。  
写入Excel：  
df_inner.to_excel('excel_to_python.xlsx', sheet_name='bluewhale_cc')  
写入到CSV：  
df_inner.to_csv('excel_to_python.csv')  
