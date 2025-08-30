# 自由神社曲谱库 2.0
> 一个非营利的、兴趣驱动的曲谱编辑、发布与整理解决方案。

![license](https://img.shields.io/github/license/mashape/apistatus.svg)  [![](https://img.shields.io/badge/%E8%B4%B4%E5%90%A7%20-%20justice__eternal%20-orange.svg)](https://tieba.baidu.com/f?kw=justice_eternal&ie=utf-8)  ![](https://img.shields.io/badge/Made-%E2%9D%A4-ff69b4.svg)

## Resource

[曲库地址](https://github.com/zytx121/je/issues) | [自由神社](http://moeje.org) | [曲库移动端老站](http://jefun.top) | [曲库PC端老站](http://lightmoon.pw) | [百度贴吧](https://tieba.baidu.com/f?kw=justice_eternal)

[安卓客户端(新)](https://github.com/madderscientist/JEapp/releases) | [安卓客户端(老)](https://github.com/livesun/JE-/raw/master/app-release.apk) | [微信小程序](https://github.com/madderscientist/JElib) | [资源汇总](./download.md)

交流QQ群：690514210  （群内有图文教程，手把手教你传谱或调用该曲库API,另外如果有dalao愿意尝试ios端或者微信小程序开发请加群详聊！）

## Contributors

<a href="https://github.com/madderscientist"><img src="https://avatars.githubusercontent.com/u/51468627?s=400&v=4" height="66px" width="66px"></a>
<a href="https://github.com/TOKdawn"><img src="https://avatars2.githubusercontent.com/u/15122564?s=460&v=4" height="66px" width="66px"></a>
<a href="https://github.com/livesun"><img src="https://avatars0.githubusercontent.com/u/27534854?s=460&v=4" height="66px" width="66px"></a>
<a href="https://github.com/GlacierStudioQ"><img src="https://avatars2.githubusercontent.com/u/13463146?v=4&s=460" height="66px" width="66px"></a>
<a href="https://github.com/liurunzechn"><img src="https://avatars2.githubusercontent.com/u/30720999?v=4&s=460" height="66px" width="66px"></a>
<a href="https://github.com/Dyakira"><img src="https://avatars0.githubusercontent.com/u/11003029?s=460&v=4" height="66px" width="66px"></a>
<a href="https://github.com/NorthPoleStar"><img src="https://avatars1.githubusercontent.com/u/30740698?v=4&s=460" height="66px" width="66px"></a>
<a href="https://github.com/Mars-Cat"><img src="https://avatars3.githubusercontent.com/u/34885717?s=460&v=4?v=4&s=460" height="66px" width="66px"></a>
<a href="https://github.com/IGRX"><img src="https://avatars2.githubusercontent.com/u/35169480?s=460&v=4" height="66px" width="66px"></a>
<a href="https://github.com/aS737345039"><img src="https://avatars2.githubusercontent.com/u/35213527?s=460&v=4" height="66px" width="66px"></a>
<a href="https://github.com/xqyww123"><img src="https://avatars3.githubusercontent.com/u/3982387?s=460&v=4" height="66px" width="66px"></a>
<a href="https://github.com/njupt4145438"><img src="https://avatars3.githubusercontent.com/u/35494698?s=460&v=4" height="66px" width="66px"></a>
<a href="https://github.com/rockyhann"><img src="https://avatars2.githubusercontent.com/u/30772677?s=460&v=4" height="66px" width="66px"></a>

## Usage

### 搜索曲谱
```
https://api.github.com/search/issues?q=${keyword}+state:open+repo:zytx121/je${label}&sort=created&order=desc
```
- `keyword`: 搜索关键词
- `label`: 曲谱标签。若无标签， `${label}&sort=created&order=desc` 可省

### 请求某一个曲谱
```
https://api.github.com/repos/zytx121/je/issues/${number}
```
- `number`: 曲谱的ID，即网页浏览issue时，地址最后的数字

### 获取所有曲谱标签
```
https://api.github.com/repos/zytx121/je/labels
```

### 按时间倒序请求最新曲谱
```
https://api.github.com/repos/zytx121/je/issues?per_page=${perPage}&page=${pageID}
```
- `perPage`: 每一页多少曲谱
- `pageID`: 按照 `perpage` 分页时，第几页曲谱。从1开始

当 `pageID` 较大时，应通过上一页的**响应头**中的 `Link` 字段获取下一页链接：
```
'Link': '<https://api.github.com/repositories/117391789/issues?per_page=30&page=2&after=Y3Vyc29yOnYyOpLPAAABkDqjQUDOjQwhaQ%3D%3D>; rel="next"'
```
响应头内容参考：[About the response code and headers](https://docs.github.com/en/rest/using-the-rest-api/getting-started-with-the-rest-api?apiVersion=2022-11-28#about-the-response-code-and-headers)

> Reference: [Github REST API v3](https://developer.github.com/v3/issues/)


## 	Explanation


### je谱

- `1＝C` 的**默认**情况下，`1234567` 同简谱的中音，`#`为升半音，即推半音键；`b`为降半音。变音记号仅作用于其后紧跟的音符数字，两者之间不应有空格。例如 `#1`、`b2` 都为推键的 `do`。
- `1＝#C` 的情况下，`1234567`全部是升半音（保持推键按下），`b`为降半音，例如 `12b131` 中仅第三个音 `b1` 需要松半音推键。
- `()`（或`（）`）中为低八度；`[]`（或`【】`）中为高八度；括号可以嵌套，例如 `((12))` 表示倍低音的 `do re`，而 `[[b4#3]]` 表示倍高音的 `mi fa`。
- 至于时值节奏，单曲循环自行把握。谱中可通过空格、换行、波浪线、甚至文字等方式表示简单的节奏。
- 注意：je谱约定俗成，并无严格规定格式。

### 扒谱人
一种以码数字为乐趣的生物，个体可赋有被动技能“绝对音准”。
### 搬运工
一群以搬运谱子为乐趣的勤劳生物。
### 用户
一种以演奏为乐趣的生物。

### Q&A

Q：曲谱库和网站和客户端是什么关系？
<br>
A：曲谱库是利用github的相关功能来存放谱子，起到一个数据库的作用。网站和客户端则是通过调用曲谱库中的数据，更好的方便大家使用，但其实利用github曲库本身也能实现谱子的查找。总的来说，github曲库就像是砖，用它可以搭建不同风格的建筑（网站或客户端）。如果有小伙伴想用咱们曲库开发自己的网站或者客户端，咱们绝对是热烈欢迎！并且提供一对一的技术支持！（ios和微信小程序开发的小伙伴你在哪里？快到碗里来！）

Q：网站老是上不去，怕自己上传的谱子消失，没有安全感- -！
<br>
A：额。。。黑人问号.jpg  这里我必须解释一下，之前网站是我自己学习编程所写，中途由于换了几次域名，导致原来的域名无法正常访问。但是，目前可以负责人的告诉大家，github曲库至始至终都是可以正常访问的并上传谱子的。相信只要大家理解曲谱库和网站或客户端的关系，就不会有后顾之忧了。github男友力max！安全感爆表啊！

Q：github曲库和主站自由神社什么关系？
<br>
A：为了更好推动JE吧的发展，我们也已经正式更名为自由神社曲谱库，作为自由神社资源的一部分存在！同时我们的安卓客户端也将开始使用自由神社这个名字。今后，我们自由神社曲谱库将会持续为JE吧做贡献！所以也请小伙伴本不要没有安全感- -！安安心心上传吧！我们也知道谱子是贴吧里的小伙伴们辛辛苦苦扒出来的，那份想与大家分享的心情我们是坚决不会辜负的！！！

Q：如果谱子是在别人基础上根据自己喜好修改而来怎么办？
<br>
A：可以在扒谱人后加一行整理人

Q：同一首曲子能否有多版本？
<br>
A：可以的。考虑到大家扒的谱根据自己的偏好可能存在差异，所以即使是同一首曲子也不要求只留一个版本，可以同时存在不同版本。这样也方便大家挑选自己喜欢的版本。


###  2.0版本和之前的版本有什么区别？

- 1.0版本中为了美观使用了badge，后来成为了上传模板的主要门槛。另外，badge中的文字信息无法搜索到，影响了基本的搜索功能，导致许多用户搜不到想要的谱子，爬虫无法正确抓取歌曲信息。2.0版本中，我们决定将数据和样式分离，仅仅将github曲库定位为一个数据库，去除badge。这样不仅改善了搜索，同时使得利用爬虫备份谱子数据成为可能。

- 1.0版本将一个作品定为一个issue，用issue里的comment来储存该作品的谱子，随着谱子数量增加，逐渐暴露出来一些问题。1. 如果同一作品下的谱子太多，那么用户搜索到该作品后还需要往下滚动很久才能找到需要的谱子，大大降低了用户体验。2. 以作品为基本单位的设计，先入为主地将谱子之间的其他方面联系削弱了。在2.0版本中，我们将每一首谱子单独作为一个issue，通过在comment中加入各种关键字（复数个关键字之间用分号隔开）来实现对谱子的分类搜索。在2.0版本中，用户能够按照作品名，扒谱人，xx年xx月新番，甚至是编曲人等等关键字进行搜索。极大的提高了搜索的自由度。（值得一提的是由于github后端使用的是elasticsearch，所以我们的曲库是支持分段搜索的，如输入：`2017 4`也可搜索到带有`2017年04月`关键字的谱子）
