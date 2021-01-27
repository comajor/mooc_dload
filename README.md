# 用Python批量下载MOOC资源

## 简介

这是我编写的一个Python脚本，用来批量下载一门MOOC的资源，包括视频、PDF和课程目录。

你是否也曾上MOOC学习过？有没有和我一样遇到这些情况：

1. 在线看MOOC视频消耗流量好多，或者浏览器仅支持的2倍速也无法满足你飞速的头脑，所以想要去免费网络处集中全部下载到电脑里
2. 老师的课件好精美，想要保存到本地，可以随时快速查阅
3. 纯粹是有收集癖，想把学习过的东西都保存到本地

那么，这个python脚本可能会帮到你，下面我来详细介绍它的使用方法



## 使用步骤

### 第一步 运行脚本

你的电脑上需要有一个[Python](https://www.python.org/)的IDE，或者其他可以运行Python脚本的软件，将mooc_dload.py放在一个单独的文件夹下运行；如果你是Windows系统，那么我已经为你将py文件变成了一个exe文件，就是mooc_dload.exe，你可以省去安装Python的解释器，直接以管理员身份运行它即可。



​										<img src="C:\Users\86132\Desktop\Export-7a691e02-0ffc-4211-96d0-c07ed33f6d6f\用Python批量下载MOOC资源 db5e218a86af4510b3f1958e740dcc1f\Untitled 2.png" alt="Untitled 2" style="zoom: 33%;" />    	         <img src="C:\Users\86132\Desktop\Export-7a691e02-0ffc-4211-96d0-c07ed33f6d6f\用Python批量下载MOOC资源 db5e218a86af4510b3f1958e740dcc1f\Untitled 1.png" alt="Untitled 1" style="zoom: 80%;" />

### 第二步 输入MOOC课程编号

运行后会弹出一个黑色的窗口，提示我们输入课程编号，课程就是你想要下载的MOOC课程，在网页中打开该课程后，浏览器的URL此时为：[https://www.icourse163.org/course/BIT-1001870001](https://www.icourse163.org/course/BIT-1001870001) （以《Python网络爬虫与信息提取》这门课为例）它的课程编号就是BIT-1001870001，我们直接在黑色的窗口中输入这个编号后回车。

<img src="%E7%94%A8Python%E6%89%B9%E9%87%8F%E4%B8%8B%E8%BD%BDMOOC%E8%B5%84%E6%BA%90%20db5e218a86af4510b3f1958e740dcc1f/Untitled%203.png" alt="%E7%94%A8Python%E6%89%B9%E9%87%8F%E4%B8%8B%E8%BD%BDMOOC%E8%B5%84%E6%BA%90%20db5e218a86af4510b3f1958e740dcc1f/Untitled%203.png" style="zoom:80%;" />

窗口会不断更新给出已经下载的课程目录，耐心等待全部下载完成。

### 第三步 查看下载结果

回到我们最初放置mooc_dload文件的目录，此时我们可以看到，文件夹中出现了几个新的文件，分别是PDFs、Links.txt、TOC.txt和Rename.bat，下面是它们各自的说明：

<img src="%E7%94%A8Python%E6%89%B9%E9%87%8F%E4%B8%8B%E8%BD%BDMOOC%E8%B5%84%E6%BA%90%20db5e218a86af4510b3f1958e740dcc1f/Untitled%204.png" alt="%E7%94%A8Python%E6%89%B9%E9%87%8F%E4%B8%8B%E8%BD%BDMOOC%E8%B5%84%E6%BA%90%20db5e218a86af4510b3f1958e740dcc1f/Untitled%204.png" style="zoom: 80%;" />


| 文件名 | 用处  |
| -------------- | ---------------------- |
| PDFs（文件夹） | 存放课程所有的PDF课件  |
| Links.txt      | 包含所有视频资源的链接 |
| TOC.txt        | 课程的文字目录         |
| Rename.bat     | 用于批量修改视频名     |

<img src="%E7%94%A8Python%E6%89%B9%E9%87%8F%E4%B8%8B%E8%BD%BDMOOC%E8%B5%84%E6%BA%90%20db5e218a86af4510b3f1958e740dcc1f/Untitled%205.png" alt="%E7%94%A8Python%E6%89%B9%E9%87%8F%E4%B8%8B%E8%BD%BDMOOC%E8%B5%84%E6%BA%90%20db5e218a86af4510b3f1958e740dcc1f/Untitled%205.png" style="zoom:67%;" />

### 第四步 下载视频

你可能发现了，脚本并没有直接下载视频，而是下载了视频的下载链接。因为我考虑到直接下载视频的话会使脚本运行时间过长，一旦中间不小心关闭窗口或者因为网络不稳定等原因使脚本终止，就只能删掉下载好的部分视频重新来过；对于有的MOOC包含的视频实在太长太多，我们可能会想要分批下载保存；另外，脚本默认的下载方式往往不是最快的，我们可以用链接+下载器的方式更好实现我们的下载。

这里我以迅雷为例

打开Links.txt，复制全部内容；打开迅雷软件-新增下载任务，迅雷会自动填入剪贴板中的链接，选择好下载目录开始下载。（最好新建一个专门的文件夹集中存放视频）

最终下载好的视频文件是原始名字，一般都是一串看不懂的字符，为了方便找到我们要看的视频，我们将Rename.bat拷贝到视频文件的目录下，双击运行，所有视频的名字就被改正过来了。

![%E7%94%A8Python%E6%89%B9%E9%87%8F%E4%B8%8B%E8%BD%BDMOOC%E8%B5%84%E6%BA%90%20db5e218a86af4510b3f1958e740dcc1f/Untitled%206.png](%E7%94%A8Python%E6%89%B9%E9%87%8F%E4%B8%8B%E8%BD%BDMOOC%E8%B5%84%E6%BA%90%20db5e218a86af4510b3f1958e740dcc1f/Untitled%206.png)

## 写在最后

1. 到此，MOOC资料就成功保存在本地了，可以随时随地用任意倍速观看了，这里推荐一个很好用的播放器：PotPlayer。
2. 我测试的时候是下载《Python网络爬虫与信息提取》、后来又测试《C语言程序设计》、《Python机器学习应用》也是OK的，但是后来我发现，现在MOOC上的一部分课程后台做了修改，这些课程故意隐藏了链接，导致我们通过爬虫无法获取到视频的链接了，所以对于这部分课程目前这个脚本只能获取除了视频以外的资源，我相信应该是可以通过改进代码获取到的，但是我目前的水平有限，期待你来补充改进，把他做完美。
3. 编写源码的过程中借鉴了网上的一些代码，由于太杂，过程中没有留心记录，所以这里也没有办法表明参考目录，如果有原作看到自己的部分希望联系我：comajor@buaa.edu.cn，我会在文档中标注出处。
4. 源码已经开源在我的Github
5. 仅作为学习交流，请不要用于商业用途。
6. 希望这篇文档能对你有帮助，比心 ❤️
