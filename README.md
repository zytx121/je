# Justice_Eternal 曲谱库2.0
> 一个非营利的、兴趣驱动的曲谱编辑、发布与整理解决方案。

![license](https://img.shields.io/github/license/mashape/apistatus.svg)  [![](https://img.shields.io/badge/%E8%B4%B4%E5%90%A7%20-%20justice__eternal%20-orange.svg)](https://tieba.baidu.com/f?kw=justice_eternal&ie=utf-8)  ![](https://img.shields.io/badge/Made-%E2%9D%A4-ff69b4.svg)

## Resource

[贴吧地址](https://tieba.baidu.com/f?kw=justice_eternal) | [网站](http://bipubipu.com) | [移动端老站](http://jefun.top) | [PC端老站](http://lightmoon.pw) | [曲库地址](https://github.com/zytx121/justice_eternal/issues) | [安卓客户端下载地址](https://pan.baidu.com/s/1pLMIsn5) ，密码: qrt9

交流QQ群：690514210  （群内有图文教程，手把手教你传谱或调用该曲库API）

## Contributors

<a href="https://github.com/livesun"><img src="https://avatars0.githubusercontent.com/u/27534854?s=460&v=4" height="66px" width="66px"></a>
<a href="https://github.com/GlacierStudioQ"><img src="https://avatars2.githubusercontent.com/u/13463146?v=4&s=460" height="66px" width="66px"></a>
<a href="https://github.com/liurunzechn"><img src="https://avatars2.githubusercontent.com/u/30720999?v=4&s=460" height="66px" width="66px"></a>
<a href="https://github.com/NorthPoleStar"><img src="https://avatars1.githubusercontent.com/u/30740698?v=4&s=460" height="66px" width="66px"></a>
<a href="https://github.com/Mars-Cat"><img src="https://avatars3.githubusercontent.com/u/34885717?s=460&v=4?v=4&s=460" height="66px" width="66px"></a>



## Usage

#### getIssues
```
https://api.github.com/search/issues?q=${data.keyword}+state:open+repo:zytx121/justice_eternal${label}&sort=created&order=desc
```

#### getIssue
```
https://api.github.com/repos/zytx121/justice_eternal/issues/${number}
```

##### getLabels
```
https://api.github.com/repos/zytx121/justice_eternal/labels
```

> Reference： [Github REST API v3](https://developer.github.com/v3/issues/)


## 	Explanation


#### je谱

- 1＝C的情况下1234567同简谱的中音，#升半音，例如1# 123中#1为升半音，即推半音键。
- 1＝#C的情况下，1234567全部是升半音，b为降半音，如12b13中的b1即松半音阶推键。
- ｛｝中为超低音区音,（）中为低音区音,[]或【】中为高音区音，{{}}为倍低音区音。
- 至于时值节奏，单曲循环自行把握。
- 注意：je谱为约定俗成，并无严格规定格式。

#### 扒谱人
一种以码数字为乐趣的生物，个体可赋有被动技能“绝对音准”。
#### 搬运工
一群以搬运谱子为乐趣的勤劳生物。
#### 用户
一种以演奏为乐趣的生物。

#### Q&A

Q：曲谱库和网站和客户端是什么关系
A：曲谱库是利用github的相关功能来存放谱子，起到一个数据库的作用。网站和客户端则是通过调用曲谱库中的数据，更好的方便大家使用，但其实利用github曲库本身也能实现谱子的查找。总的来说，github曲库就像是砖，用它可以搭建不同风格的建筑（网站或客户端）。我近期会将曲库的api端口详细的写出来，如果有小伙伴想用咱们曲库开发自己的网站或者客户端，咱们绝对是热烈欢迎！并且提供一对一的技术支持！（ios开发的小伙伴你在哪里？快到碗里来！）

Q：网站老是上不去，怕自己上传的谱子消失，没有安全感- -！
A：额。。。黑人问号.jpg  这里我必须解释一下，之前网站是我自己学习编程所写，中途由于换了几次域名，导致原来的域名无法正常访问。但是，目前可以负责人的告诉大家，github曲库至始至终都是可以正常访问的并上传谱子的。相信只要大家理解曲谱库和网站或客户端的关系，就不会有后顾之忧了。github男友力max！安全感爆表啊！

Q：github曲库和主站自由神社什么关系？
A：我个人给github曲库的定位是一个存放谱子的数据库，因为楼主也参（划）与（水）了自由神社新版本的开发，所以已经确定的是，等新站上线，本曲库的所有谱子都会连同老站的谱子一起移植到新站。所以也请小伙伴本不要没有安全感- -！安安心心上传吧！我们也知道谱子是小伙伴们辛辛苦苦扒出来的，那份想与大家分享的心情我们是坚决不会辜负的！！！

Q：如果谱子是在别人基础上根据自己喜好修改而来怎么办？
A：可以在扒谱人后加一行修改人

Q：同一首曲子能否有多版本？
A：可以的。考虑到大家扒的谱根据自己的偏好可能存在差异，所以即使是同一首曲子也不要求只留一个版本，可以同时存在不同版本。这样也方便大家挑选自己喜欢的版本。对于一首曲子本身就有不同版本，只需在曲名上进行区分即可。

Q：2.0版本和之前的版本有什么区别？
A：为了使搜索谱子更加方便，大幅调整了曲谱储存方式。2.0版本将**每一首谱子单独设为一个issue，通过project对不同谱子按照来来源进行分类**。


## License

MIT 


