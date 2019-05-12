# 以下是Python的一些常用库的使用介绍和示例

## pipenv

Pipfile是社区拟定的依赖管理文件，用于替代过于简陋的requirements.txt文件。pipenv是Pipfile主要倡导者，主要包含了Pipfile、pip、click、requests和virtualenv。  
使用格式: pipenv [OPTIONS] COMMAND [ARGS]...

Options:  
  --where             输出项目目录信息  
  --venv              输出虚拟环境信息  
  --py                输出Python解释器信息  
  --envs              输出环境变量选项  
  --rm                删除虚拟环境  
  --bare              最小化输出  
  --completion        输出完成（待评估）  
  --man               显示联机帮助页  
  --support           输出用于GitHub问题的诊断信息  
  --site-packages     为虚拟环境启用site-packages[环境变量:PIPENV_SITE_PACKAGES]  
  --python TEXT       指定哪个版本的Python虚拟环境应该使用  
  --three/--two       在创建virtualenv时使用Python 3/2  
  --clear             清除缓存（pipenv，pip和pip-tools）[环境变量:PIPENV_CLEAR]  
  -v, --verbose       详细模式  
  --pypi-mirror TEXT  指定PyPI镜像  
  --version           显示版本并退出  
  -h, --help          显示此帮助消息并退出  

使用示例:  
   使用Python 3.7创建一个新项目:  
   $ pipenv --python 3.7

   删除项目virtualenv（从当前目录推断）:  
   $ pipenv --rm

   安装项目的所有依赖项（包括dev）:  
   $ pipenv install --dev

   创建包含预发布的锁文件:  
   $ pipenv lock --pre

   显示已安装包的依赖项的图表:  
   $ pipenv graph

   检查已安装的依赖项是否存在安全漏洞:  
   $ pipenv check

   将本地setup.py安装到虚拟环境/Pipfile中:  
   $ pipenv install -e .

   使用较低级别的pip命令:  
   $ pipenv run pip freeze

Commands:  
  check      检查Pipfile中提供的安全漏洞和PEP 508标记  
  clean      卸载Pipfile.lock中未指定的所有软件包  
  graph      显示当前安装的依赖关系图信息  
  install    安装提供的包并将它们添加到Pipfile，或者（如果没有给出包）从Pipfile安装所有包  
  lock       生成Pipfile.lock  
  open       在编辑器中查看给定模块  
  run        运行一个安装在virtualenv中的命令  
  shell      在virtualenv中生成一个shell  
  sync       安装Pipfile.lock中指定的所有包  
  uninstall  卸载提供的软件包并将其从Pipfile中删除  
  update     运行锁定，然后同步

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

```#!/usr/bin/python3
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

```#!/usr/bin/python3
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

```#!/usr/bin/python3
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

```#!/usr/bin/python3
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

```#!/usr/bin/python3
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

```#!/usr/bin/python3
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

```#!/usr/bin/python3
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

```#!/usr/bin/python3
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

```#!/usr/bin/python3
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

```#!/usr/bin/python3
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

```#!/usr/bin/python3
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

```#!/usr/bin/python3
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

```#!/usr/bin/python3
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

```#!/usr/bin/python3
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

## Arrow

提供了一种合理的，人性化的方法来创建，操作，格式化和转换日期，时间和时间戳。使用更少的导入和更少的代码来处理日期和时间。  
获取当前本地时间：arrow.now()  
获取当前UTC时间：arrow.utcnow()  
将时间戳转化为arrow对象，其中时间戳可以是int，float或者可以转化为float的字符串：arrow.get(timestamp)  
将字符串转换为arrow对象：arrow.get(string[,format_string])  
示例：arrow.get('2018-02-24 12:30:45', 'YYYY-MM-DD HH:mm:ss')  
遵循ISO-8601的字符串不需要格式字符串参数即可转换：arrow.get('2018-02-24T13:00:00.000-07:00')  
从字符串中通过格式参数搜索时间：arrow.get('June was born in May 1980', 'MMMM YYYY')  
直接创建arrow对象：arrow.get(2018, 2, 24)  
arrow对象属性：datetime,timestamp,native,tzinfo  
获取datetime对象的值：a.hour  
时间推移，shift方法获取某个时间之前或之后的时间,关键字参数为years,months,weeks,days,hours，seconds，microseconds：a.shift(**kwargs)  
时间替换，返回一个被替换后的arrow对象，原对象不变：a.replace(**kwargs)  
格式化输出：a.format([format_string])  
人性化输出(xx之前、xx之后)：a.humanize(locale),locale参数可以指定地区语言  
时间范围和区间：a.span(string), a.floor(), a.ceil()

## logging日志库

logging模块是Python内置的标准模块，主要用于输出运行日志，可以设置输出日志的等级、日志保存路径、日志文件回滚等。  

### 基本使用（控制台输出）

示例：  
```#!/usr/bin/python3
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

```#!/usr/bin/python3
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
```#!/usr/bin/python3
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
```#!/usr/bin/python3
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
```#!/usr/bin/python3
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
