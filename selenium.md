##python + selenium UI自动化测试

###目录：
* **Python3.x环境安装(mac)**

* **PyCharm编译器破解版安装**
 
* **Selenium的环境搭建(mac)**
 
* **安装浏览器驱动chromedriver(mac)**
 
* **python、selenium/webdriver常见基本语法**

* **使用python3.7编写测试脚本**



###一、python3.x环境安装
####在Mac上安装Python
如果你正在使用Mac，系统是OS X >= 10.9，那么系统自带的Python版本是2.7。要安装最新的Python 3.7，有两个方法：

方法一：从Python官网下载Python 3.7的安装程序[Python 3.7][]，双击运行并安装（傻瓜式操作一直下一步即可）；

[Python 3.7]:https://www.python.org/ftp/python/3.7.0/python-3.7.0-macosx10.9.pkg

方法二：如果安装了Homebrew，直接通过命令brew install python3安装即可。

####Python解释器
当我们编写Python代码时，我们得到的是一个包含Python代码的以.py为扩展名的文本文件。要运行代码，就需要Python解释器去执行.py文件。

Mac电脑推荐:**PyCharm**

###二、安装PyCharm破解版

第一步:官方下载[PyCharm][]专业版（如果你已经下载有，建议你卸载删除后（一定要把数据删除干净）重新下载，避免出现版本问题）

[PyCharm]:https://www.jetbrains.com/pycharm/download/#section=mac

第二步:将DMG中的 PyCharm.app 拖动至 “应用程序”文件夹

![拖动至 “应用程序”文件夹](https://img-blog.csdn.net/20171016212040712)

第三步:下载[JetbrainsCrack][]破解补丁包

[JetbrainsCrack]:https://pan.baidu.com/s/1zz_lljNo79AW7OgTF6dg2w

第四步:将下载好的破解补丁包复制到 /Applications/PyCharm.app/Contents/bin/ 目录中（找到应用程序/Pycharm 右键显示包内容，就可以看到Contents文件夹）如图:

![拖动JetbrainsCrack](http://ws2.sinaimg.cn/large/a40724bfly1g59par3mhpg20la0c2k1w.gif)

第五步:用编辑器打开 `/Applications/PyCharm.app/Contents/bin/pycharm.vmoptions` 文件，添加 ` -javaagent:/Applications/PyCharm.app/Contents/bin/JetbrainsCrack-release-enc.jar`在最后一行。如图:

![添加javaagent](http://ws4.sinaimg.cn/large/a40724bfly1g59pe46dqkj20jo0c575o.jpg)


**注意:**路径修改成你的pycharm安装路径，然后保存。

第六步:启动PyCharm,选择**激活码激活**,并在**激活码**栏目输入任意内容，然后点击ok即可。

**大功告成:**显示到期日期为2100年

![PyCharm破解成功](http://wx3.sinaimg.cn/large/a40724bfly1g59pm381rnj20x40jatq2.jpg)

网上有不少用pip方式安装selenium的，其实selenium本质就是第三方库，我们可以采用pycharm自带方式来安装


###三、使用PyCharm安装selenium库文件
第一步:在PyCharm启动页面进入设置**Preferences**

![进入设置页面](http://ws2.sinaimg.cn/large/a40724bfly1g59q2gzrajj21760zs1eh.jpg)

第二步:进入**Project Interpreter**选项，点击“+”号

![添加](http://wx3.sinaimg.cn/large/a40724bfly1g59q4c4p3mj21k812owjk.jpg)

第三步:修改pip源，切换到国内`https://pypi.tuna.tsinghua.edu.cn/simple/`

![切换pip源到国内](http://wx1.sinaimg.cn/large/a40724bfly1g59qb4yr7gj21fc15gwnk.jpg)

![编辑pip的url](http://ws2.sinaimg.cn/large/a40724bfly1g59qbp57c8j21f8154h3a.jpg)

第四步:安装selenium
![安装selenium](http://wx3.sinaimg.cn/large/a40724bfly1g59qdtjuisj21fc15g138.jpg)

###四、安装浏览器驱动chromedriver(mac)

每个浏览器都有自己的驱动，比如谷歌的chromedriver、火狐的geckodriver、IE的IEDriverServer,
未安装chrome驱动时，使用webdriver调chrome，并使用get方法传url参数时会报错；

```
	TypeError: get() missing 1 required positional argument: 'url'

```
因此需要安装相应的浏览器驱动。

以下我们以谷歌的chromedriver为例:

1、查看chrome版本:输入`chrome://settings/help`

* 注意:<mark> chromedriver的版本一定要与chrome 浏览器的版本一致,否则在运行的时候会报错</mark> 
![查看chrome版本](http://wx2.sinaimg.cn/large/a40724bfly1g59qydplrfj21u612owmb.jpg)

2、下载[chromedriver][]

*	注意:<mark>需要翻墙才能下载</mark>

![下载chromedriver](http://ws1.sinaimg.cn/large/a40724bfly1g59rda46nzj21u80k8104.jpg)

3、拷贝到：usr/local/bin 。并不是usr/bin,因为没有系统管理员权限，拷贝到usr/bin下，很难成功，我尝试直接粘贴，用命令拷贝等，都不行。最后发现拷贝到：usr/local/bin，就可以用了。简单可行。
![拷贝chromedriver到bin文件夹](http://wx3.sinaimg.cn/large/a40724bfly1g59rbs8fdcj21g60u617m.jpg)


[chromedriver]:https://chromedriver.storage.googleapis.com/index.html?path=75.0.3770.140/

**注意:**<mark>常见报错原因：</mark>

* 浏览器和chromedriver版本不一致
* 防火墙导致无法访问铬浏览器，关闭防火墙

###五、python、selenimu、webdriver基本语法

####1、python基本语法:
	
推荐学习廖雪峰的[python教程][]
	

[python教程]:https://www.liaoxuefeng.com/wiki/1016959663602400


####2、selenium/webdriver常用知识点:

* 浏览器操作

```
		
1、浏览器最大化

	driver.maximize_window()

2、设置浏览器宽和高

	driver.set_window_size(400,800)

3、控制浏览器前进、后退

	driver.forward()

	driver.back()

4、刷新页面

	driver.refresh()
	
5、输入网址

	driver.get("http://wenku.baidu.com")
	
6、获得当前页面title，判断页面跳转是否符合预期
	
	driver.title
	
7、获得当前URL，一般用来测试重定向

	driver.current_url
			
```

* Selenium 八种元素定位方法

```
		
1、id定位

	driver.find_element_by_id()

2、name定位

	driver.find_element_by_name()


3、class定位

	driver.find_element_by_class_name()
	
4、tag定位

	driver.find_element_by_tag_name()
	
5、link定位

	driver.find_element_by_link_text()

6、partial_link定位

	driver.find_element_by_partial_link_text()
	
7、xpath定位

	driver.find_element_by_xpath()
	
8、CSS定位

	driver.find_element_by_css_selector()

			
```

* 操作测试对象

```
		
1、清除内容，如默认用户名和密码

	driver.find_element_by_css_selector('xxxxx').clear()

2、模拟鼠标点击操作

	driver.find_element_by_css_selector('xxxxx').click()

3、向输入框输入
	
	driver.find_element_by_css_selector('xxxxx').send_keys()

4、提交表单

	driver.find_element_by_css_selector('xxxxx').submit()
			
```

* WebElement接口常用方法

```
		
1、返回元素尺寸
	
	driver.find_element_by_css_selector('xxxxx').size

2、获取元素文本信息

	driver.find_element_by_css_selector('xxxxx').text

3、获取元素某个属性值

	driver.find_element_by_css_selector('xxxxx').get_attribute('type')

4、该元素用户是否可见

	driver.find_element_by_css_selector('xxxxx').is_displayde()
			
```

* 鼠标事件

```
		
ActionChains类操作鼠标事件ActionChains的使用:

首先引入:
from selenium.webdriver.common.actionchains import ActionChains

ActionChains的执行原理调用ActionChains方法的时候,用户行为不会立刻执行,
而是将所有操作放在一个队列中,当执行perform()方法时,按照放入队列的顺序先进先出执行ActionChains方法的书写格式

perform():执行

1、鼠标右击
	
	driver.find_element_by_css_selector('xxxxx').context_click()

2、鼠标双击

	driver.find_element_by_css_selector('xxxxx').double_click()	
	
3、鼠标点击
	
	driver.find_element_by_css_selector('xxxxx').click()
	
4、按住鼠标左键(不抬起)
	
	driver.find_element_by_css_selector('xxxxx').click_and_hold()
	
5、鼠标移动到某个元素

	ActionChains(driver).move_to_element(目标元素).perform()
	
6、鼠标移动到某个坐标

	ActionChains(driver).move_by_offset(xoffset,yoffset).perform()
	
7、将元素从起点source移动到终点target

	ActionChains(driver). drag_and_drop(source, target).perform()
	
8、按照坐标移动

	ActionChains(driver). drag_and_drop_by_offset(source, xoffset, yoffset).perform()
		
```

* 键盘事件

```
Keys类操作键盘事件

Keys类的使用

首先引入:
from selenium.webdriver.common.keys import Keys

1、输入框输入内容

 	driver.find_element_by_class_name('j-phone').send_keys('18519533777')
		
2、全选

	driver.find_element_by_css_selector('xxxxx').send_keys(Keys.CONTROL,'a')

3、复制

	driver.find_element_by_css_selector('xxxxx').send_keys(Keys.CONTROL,'c')

4、粘贴

	driver.find_element_by_css_selector('xxxxx').send_keys(Keys.CONTROL,'v')

5、剪切

	driver.find_element_by_css_selector('xxxxx').send_keys(Keys.CONTROL,'x')

6、回车键

	driver.find_element_by_css_selector('xxxxx').send_keys(Keys.ENTER)

7、删除键

	driver.find_element_by_css_selector('xxxxx').send_keys(Keys.BACK_SPACE)

8、空格键

	driver.find_element_by_css_selector('xxxxx').send_keys(Keys.SPACE)

9、制表键

	driver.find_element_by_css_selector('xxxxx').send_keys(Keys.TAB)

10、回退键

	driver.find_element_by_css_selector('xxxxx').send_keys(Keys.ESCAPE)
			
```

* selenium中的三种等待方式

```
		
1、显示等待(导入 WebDriverWait 包)

	显示等待，同样也是 webdirver 提供的方法。在设置时间内，默认每隔一段时间检测一次当前页面元素是否存在，如果超过设置时间检测不到则抛出异常。默认检测频率为0.5s，默认抛出异常为：NoSuchElementException
	
	WebDriverWait(driver,10).until(EC.presence_of_element_located(locator))
    driver.find_element_by_id("kw").send_keys('abc')

2、隐式等待

	隐式等待，也叫智能等待，是 webdirver 提供的一个超时等待。隐的等待一个元素被发现，或一个命令完成。如果超出了设置时间的则抛出异常。
	
	driver.implicitly(秒数)

3、强制等待(导入 time 包)

	强制等待，设置固定休眠时间。 python 的 time 包提供了休眠方法 sleep() ， 导入 time 包后就可以使用 sleep()，进行脚本的执行过程进行休眠。
	
	time.sleep(秒数)
			
```

* 定位frame中的对象

```
		
1、切换到iframe中

	driver.switch_to.frame(id/name/xpath)

2、从未嵌套的iframe中返回(切到frame中之后，我们便不能继续操作主文档的元素，这时如果想操作主文档内容，则需切回主文档。)

	driver.switch_to.default_content()

3、从嵌套的iframe中返回(parent_frame()这个相当于后退的方法，我们可以随意切换不同的frame)

	driver.switch_to.parent_frame()
			
```

* 多窗口处理
	* 要想在多个窗口之间切换，首先要获得每一个窗口的唯一标识符号（句柄）。通过获得的句柄来区别分不同的窗口，从而对不同窗口上的元素进行操作

```
		
1、获得当前窗口的句柄

	driver.current_window_handle

2、获得所有窗口的句柄

	driver.window_handles

3、切换回指定句柄的窗口

	driver.switch_to_handle("句柄")

4、关闭当前窗口

	driver.close()

5、关闭所有窗口

	driver.quit()
			
```

* 下拉菜单处理

```

导入Select类：from selenium.webdriver.support.select import Select

使用方法：Select(driver.find_element_by_name("xxx")).select_by_index()
		
1、根据index属性定位选项，index从0开始

	Select(driver.find_element_by_css_selector('xxxxx').select_by_index(index))

2、根据value属性定位

	Select(driver.find_element_by_css_selector('xxxxx').select_by_value(value)

3、根据选项文本值来定位

	Select(driver.find_element_by_css_selector('xxxxx').select_by_visible_text(text))

4、选择第一个选项

	Select(driver.find_element_by_css_selector('xxxxx').first_selected_option())
	
```

* 调用js代码

```

1、调用js代码

	driver.execute_script()
	
举个例子:

	js = 'var a = 100; var b = 200; var c = a + b; alert(c)'

	driver.execute_script(js)#会有弹框显示300
			
```
* 处理cookie

```
		
1、获得所有cookie

	.driver.get_cookies()

2、获得name属性的cookie

	.driver.get_cookie(name)

3、添加cookie（cookie格式为字典，）

	.driver.add_cookie(cookie_dic)

4、删除特定cookie

	.driver.delete_cookie(name)

5、删除所有cookie

	.driver.delete_all_cookies()
			
```
###六、使用python3.7编写测试脚本
```
import time
from selenium import webdriver
from selenium.webdriver import ActionChains
from selenium.webdriver.common.keys import Keys

driver = webdriver.Chrome()
# 设置为最大窗口
# driver.maximize_window()
driver.set_window_size(1400, 880)
# 设置隐式等待
driver.implicitly_wait(10)
# 访问网易云音乐
driver.get('https://music.163.com')
driver.find_element_by_class_name('m-tophead').click()
driver.find_element_by_class_name('u-btn2-2').click()

# 输入登录手机号码
driver.find_element_by_class_name('j-phone').send_keys('18519533777')

# 输入登录密码
driver.find_element_by_class_name('j-pwd').send_keys('oooooooo')
driver.find_element_by_class_name('j-primary').click()

# 搜索"讲真的"歌曲
driver.find_element_by_id('srch').send_keys('讲真的')
driver.find_element_by_id('srch').send_keys(Keys.ENTER)
driver.switch_to.frame('contentFrame')

# 点击播放
driver.find_element_by_css_selector('.srchsongst>div:nth-child(1) .ply').click()
time.sleep(5)
driver.switch_to.parent_frame()
# 暂停音乐播放
ActionChains(driver).move_to_element(driver.find_element_by_css_selector('.m-playbar')).perform()
driver.find_element_by_css_selector('.ply').click()

# 发现音乐
driver.find_element_by_css_selector('.m-nav .fst').click()

# 点击排行榜
driver.find_element_by_css_selector('.wrap .nav li:nth-child(2)').click()

driver.switch_to.frame('contentFrame')

div=driver.find_element_by_id('song-list-pre-cache')
tbody=div.find_element_by_tag_name('tbody')
trlist=tbody.find_elements_by_tag_name('tr')
driver.implicitly_wait(0)

for tr in trlist:
sftags = tr.find_elements_by_class_name('s-fc9')
if sftags:
# 歌曲名和演唱者名
songName=tr.find_element_by_css_selector('td .txt b').get_attribute('title')
authorName = tr.find_element_by_css_selector('td .text').get_attribute('title')

print('{:10s}:{}'.format(songName, authorName))

driver.implicitly_wait(10)

input('....')
driver.quit()

```









