# 以下是Python的一些常用库的使用介绍和示例

## pipenv
Pipfile是社区拟定的依赖管理文件，用于替代过于简陋的requirements.txt文件。pipenv是Pipfile主要倡导者，主要包含了Pipfile、pip、click、requests和virtualenv。
使用: pipenv [OPTIONS] COMMAND [ARGS]...

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
详情见：https://jupyter.org/

## nose
nose的优势：
-编写测试更容易。nose可以自动识别继承于unittest.TestCase的测试单元，并执行测试，而且，nose也可以测试非继承于unittest.TestCase的测试单元。nose提供了丰富的API便于编写测试代码。
-执行测试更容易。只要遵循一些简单的规则去组织你的类库和测试代码，nose是可以自动识别单元测试的。执行测试是非常耗资源的，但是，一般第一个测试模块被加载后，nose就开始执行测试。
-建立测试环境更容易。
-做你想做的事情更容易。nose拥有很多内置的插件帮助进行暑输出抓取、错误查找、代码覆盖、文档测试（doctest）等等。同样，可以自定义开发插件来完成你想要做的事情。
使用: nosetests [options]

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
  -m REGEX, --match=REGEX, --testmatch=REGEX  与此正则表达式匹配的文件，目录，函数名称和类名称被视为测试。默认: (?:^|[\b_\./-])[Tt]est[NOSE_TESTMATCH]
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
  --doctest-extension=EXT  同时在具有此扩展名的文件中查找doctests[NOSE_DOCTEST_EXTENSION]
  --doctest-result-variable=VAR  将变量名称设置为默认值“_”的最后一个解释器命令的结果。可用于避免与用于文本转换的_（）函数冲突[NOSE_DOCTEST_RESULT_VAR]
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

## concurrent.futures


## Scrapy、PySpider
都是爬虫框架

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



