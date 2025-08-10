# 信息检索教程

Copyright © 2025 wold9168. Licensed under the CC BY 4.0 International License.

---

信息检索是从信息资源集合获得与信息需求相关的信息资源的活动。本文所讨论的信息检索并非专业和学术领域的信息检索，而是个人可以应用于生活中的一种技能。

信息检索在信息时代是很重要的技能，在此不赘述其重要性。

笔者是计算机专业的人士，因而文章中的许多内容侧重于计算机专业方面。愿以同心之智，聚众手之能。如您有更好的建议，欢迎提出 [Issue](https://github.com/wold9168/information_retrieval_tutorial/issues) 或者 [PR 此仓库](https://github.com/wold9168/information_retrieval_tutorial/pulls)！

## 信息检索理论（可以跳过）

最简单的信息检索包含两个方面的活动，一个活动是从信源到受众的信息收集过程，一个活动是从受众到受众的认知的信息理解过程。这就和我们读书上学一样，学会一个东西需要上课听讲和自己理解。而知识是信息检索的目的，因而我们理解完毕以后得到的产物是知识。

进一步地，为了避免遗忘，我们会尝试在学习的过程中做笔记、做习题。对应到信息检索中，我们就是在本地构建了相应信息的索引，并且尝试加强对相关信息的学习。

总结起来有如下几步：

1. 信息收集
2. 信息理解
3. 建立索引
4. 加强学习

我们将围绕这四步展开阐述如何进行信息检索。

## 信息收集

### 善用搜索引擎

搜索引擎是很强大的工具。使用搜索引擎的上下限差异很大，不同的用户检索同一内容，检索出来的东西可能天差地别。

#### 选择正确的搜索引擎

中文互联网最大的搜索引擎是百度，其次是搜狗和 Bing（国内版本），其他基本没有记忆的需要。而其他搜索引擎里需要注意的包括：Google、Bing（国际版本）、Yandex、Yahoo、DuckDuckGo。

这些搜索引擎有这样的特点：

| 搜索引擎                                                       | 特点                                                                                                                                                         |
| -------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 百度                                                           | 擅长搜索中文互联网的古早内容（一些已经关闭的论坛的帖子），以及中国文化相关内容（农历等），广告很多。搜索国内政策、政府文件相关的时候很好用。                 |
| 百度（开发者搜索，[kaifa.baidu.com](https://kaifa.baidu.com)） | 网络受限情况下的选择。检索 CSDN、博客园等国内平台上的 Java8 等国内广泛应用的传统技术栈，以及 OpenGauss、OpenEuler 等信创技术栈时有无可比拟的优势，几乎无广告 |
| 搜狗                                                           | 百度的下位替代，没什么用的必要                                                                                                                               |
| Bing（国内版本）                                               | 国外社区相关的内容权重较低。在无法科学上网情况下，这是最佳的搜索引擎。                                                                                       |
| Yandex                                                         | 广告很少，俄语内容很多，但也能搜索出许多英文互联网相关内容。在无法科学上网情况下，这是次佳的搜索引擎。                                                       |
| Google                                                         | 地表第一搜索引擎。搜索界面几乎没有广告的同时，右侧的摘要栏目效率非常之高。                                                                                   |
| Bing（国际版本）                                               | 和国内版本的区别不大，但是搜索结果包含更多国际互联网的信息。（这一点对于计算机专业的同学比较有用）                                                           |
| Yahoo                                                          | 日本最大的搜索引擎，搜索日本相关的内容的时候非常合适。                                                                                                       |
| DuckDuckGo                                                     | 一款注重隐私的搜索引擎。搜索结果较佳。                                                                                                                       |

根据你的需要选择合适的搜索引擎。一般而言，无脑选择谷歌就行，其次就是用用百度。

#### 搜索运算符和高级搜索

部分搜索引擎支持搜索运算符和高级搜索的特性。这一特性允许用户检索特定类型、特定站点、特定日期，以及具有复杂关键词的搜索结果。

使用高级搜索，可以直接在搜索引擎中搜索“高级搜索”得到相应URL：[百度的高级搜索](https://www.baidu.com/gaoji/advanced.html)和[谷歌的高级搜索](https://www.google.com.hk/advanced_search)。

高级搜索一般通过搜索运算符限定搜索的内容，用户最常见的搜索运算符包括：

- `filetype`：限定搜索的文件类型（是的，你可以在搜索引擎中直接搜索到 pdf 文件）
- `site`：限定搜索的站点

比较常见的用法包括

- 搜索内容包含`foo`的 pdf 文件：`filetype:pdf foo`
- 搜索`cnblogs.com`站点上的内容包含`foo`的文章：`site:cnblogs.com foo`
- 搜索不在`csdn.net`站点上，但是内容包含`foo`的文章（站点黑名单）：`-site:csdn.net foo`

善用搜索运算符和高级搜索可以帮助我们快速圈定范围。

#### 拆词搜索

搜索引擎无法理解一整句话的含义。`我希望知晓哪一本书是JK罗琳写的`和`JK罗琳 作品`，这两种搜索方式，后者的搜索结果明显更优。

要尝试把自己的搜索需求表达成一个个关键词，并且去除里面和搜索结果无关的部分（例如主语`我`，表达强烈意愿的成分`希望`，口语化成分`知晓`、`写的`）。

一种例外的情况是，对于一个被广泛搜索的固定句式，该固定句式本身也是一个关键词。例如在 Google 中，有许多人搜索`how to`开头的句式，用以知晓如何做某件事情。以`how to`开头可以更方便地让搜索引擎知晓你想搜索的内容是做某件事的方法。

### 善用大模型

感谢大模型，现在我们可以用大模型检索网站了。

不过需要注意的是，大模型的幻觉往往非常严重，因而对于大模型为你提炼的信息，你应该要求大模型提供原始信源，并且认真审查原始信源中是否有相应的表述。

笔者个人经常使用的一个提示词是：

```
确保所有引用的文献必须真实存在，作者、标题、期刊/出版社名称和年份需准确无误。若不确定某文献是否存在，请明确标注'可能存在不确定性'或直接跳过。请仅引用近五年内发表于核心数据库（此处自行定义）的文献，优先选择被引量超过20次的论文。在每段对话末尾生成结构化文献展示。
```

搜索非学术内容的时候，把`文献`替换成其他的表述即可。关键在于`在每段对话末尾生成结构化文献展示`（但是这个特性并不为所有的大模型网站支持，有些网站可能无法渲染结构化文献展示）。

你也可以直接要求大模型给出相应搜索结果的链接。

### 社区问答

当你无法通过搜索引擎和大模型搜索到你想要的内容的时候，你应该尝试去特定领域的社区寻求帮助。

对于理工科性质较强的学科而言，[StackExchange](https://stackexchange.com)及其下辖站点是极佳的一个选择！对于英文水平有限的朋友，[思否](https://segmentfault.com/)是该站点的一个不错的替代。

[百度贴吧](https://tieba.baidu.com/)仍然是中文互联网几乎最大的文字社区。这里包罗万象、鱼龙混杂，同时在过去有过一段很昌盛的时间。与之对应的是[Reddit](https://reddit.com)（红迪网），别号国外版贴吧。对于这两个社区而言，一些专业性较弱的问题可以在其中获得很好的解答，专业性较强的问题，它们通常会给出一个“电工胶布”式的解决方案。

[知乎](https://zhihu.com/)是一个高质量的问答网站，以问答为中心构建了社区的生态。不过由于其社区运营和转型带来的问题，其内容质量江河日下。[Quora](https://www.quora.com/)号称国外版知乎，可以与知乎结合使用，质量则相对较高一点。

对于托管在互联网上的软件，一般可以通过其 Issues（工单/议题，或者随你怎么翻译）与其开发者进行沟通，IRC、电子邮件、邮件列表也可能是其开发者青睐的联系方式。例如本仓库的 [Issues](https://github.com/wold9168/information_retrieval_tutorial/issues)。

要善于使用 QQ 群、Discord 群进行问答。QQ 群是现代中文互联网网民获得高质量回答的最廉价方式之一。

在问答之前，建议阅读[提问的智慧](https://github.com/tvvocold/How-To-Ask-Questions-The-Smart-Way)。这篇广受好评的文章详细阐述了如何在互联网上就计算机问题进行提问，同样也适用于其他大部分领域的提问。非常建议阅读。（其实主要就是注意问答礼仪，不要懒得动手搜索而去麻烦别人。）

### 专业数据库

一些内容可能仅存在于部分专门的专业数据库之中，无法在搜索引擎里很好地搜索到。例如论文。这为我们的信息收集带来困难。

不过这些专业数据库本身就是可以被搜索到的，只是其中的内容无法被搜索。因此直接搜索这些专业数据库有哪些，分别涉及什么领域即可。

### 延展阅读：去哪里获取信息

以下内容一开始系我收藏夹导出，可能出现分类上的问题。一些链接可能因为年代久远已经失效。

- 电子书
  - 　 | CBETA 財團法人佛教電子佛典基金會 : https://www.cbeta.org/
  - [搬书匠] - 电子书(EBook) : http://www.banshujiang.cn/
  - 【故宮博物院】圖書文獻類型數典系統 : https://rbk-doc.npm.edu.tw/npmtpc/npmtpall?@@0.5416912920004143
  - 50,000+ Free eBooks in the Genres you Love | Manybooks : https://manybooks.net/
  - 100% Free eBooks for All Devices : https://www.planetebook.com/
  - Anna’s Archive : https://annas-archive.org/
  - BookRix - Self-Publishing made easy! : https://www.bookrix.de/en/home
  - books with free ebook downloads available : https://www.goodreads.com/ebooks
  - Cambridge Notes : http://dec41.user.srcf.net/notes/
  - Chinese Rare Book Digital Collection, Available Online | Library of Congress : https://www.loc.gov/collections/chinese-rare-books/
  - DigiLibraries.com - Free eBooks library : https://digilibraries.com/
  - Download Free Books to Read with the Free NOOK App | Barnes & Noble® : http://www.barnesandnoble.com/b/free-ebooks/ebooks-nook/_/N-ry0Z8qa;jsessionid=907DE83194F4719975D6401175521FC8.prodny_store02-atgap14
  - Download Free Computer Books : IT, Programming and Computer Science - OnlineProgrammingBooks.com : https://www.onlineprogrammingbooks.com/
  - eBooks for Free - Christianbook.com : https://www.christianbook.com/page/ebooks/free-ebooks?event=eBooks|1000234
  - English e-Reader : https://english-e-reader.net/
  - epub.us - Library : https://epub.us/library
  - epubBooks - Download Free EPUB and Kindle eBooks : https://www.epubbooks.com/
  - Free Computer, Programming, Mathematics, Technical Books, Lecture Notes and Tutorials : https://freecomputerbooks.com/
  - Free eBooks | Project Gutenberg : https://www.gutenberg.org/
  - Girlebooks : https://girlebooks.com/
  - Home - Research Guide for Chinese Studies - Research Guides at Harvard Library : https://guides.library.harvard.edu/chinese
  - Home - Z Library : https://zlibrary.jimdofree.com/
  - BAEN Free Library - Categories : https://www.baen.com/catalog/category/view/s/free-library/id/2012
  - iBookPile - Discover your next great book! : https://ibookpile.in/
  - itbook.download - Free Download IT Programming EBook : https://itbook.download/
  - Jiumo Search 鸠摩搜索 - 文档搜索引擎 : https://www.jiumodiary.com/
  - Kono 電子雜誌 : https://www.thekono.com/
  - Library Genesis : http://libgen.li/
  - Mox.moe [Kindle漫畫|Kobo漫畫|epub漫畫] [mox.moe] : https://mox.moe/
  - Mox.moe [Kindle漫畫|Kobo漫畫|epub漫畫] [vol.moe] : https://www.vol.moe/
  - Open Access Library (OALib) : https://www.oalib.com/
  - PDF Drive - Search and download PDF files for free. : https://www.pdfdrive.com/
  - PDF之家 – PDF杂志、PDF图书免费下载，PDF工具与资源分享 : https://www.pdfzj.com/
  - Preface | awesome-programming-books.github.io : https://awesome-programming-books.github.io/
  - sci-hub小天地\_小鲸鱼文献,一站搞定文献下载！ : http://www.9312.net/#/
  - SoBooks - 一起分享阅读的乐趣~ : https://sobooks.cc/
  - TaleBook : https://talebook.mineserver.info/
  - The Public Domain Review – Online journal dedicated to showcasing the most interesting and unusual out-of-copyright works available on the web : https://publicdomainreview.org/
  - VB爱好者乐园(VBGood)新手学堂多本VB6书籍教程高清PDF版 - Powered by Discuz! : http://www.vbgood.com/thread-116738-1-1.html
  - zlibrary最新可用的地址 持续更新 : http://chendandan.store/?p=3379
  - トップページ | 京都大学貴重資料デジタルアーカイブ : https://rmda.kulib.kyoto-u.ac.jp/
  - トップメニュー : http://kanji.zinbun.kyoto-u.ac.jp/db-machine/toho/html/top.html
  - 上海图书馆藏家谱全文选览 : http://wrd2016.library.sh.cn/channel/stjp/
  - 上海圖書館古籍聯合目錄及循證平臺 : https://gj.library.sh.cn/index
  - 中国古典文献资源导航系统 : https://www.kuizhangge.cn/
  - 中国最权威的出版物数据服务平台（PDC） : https://pdc.capub.cn/
  - 中图易阅通 : https://www.cnpereading.com/
  - 书享家\_电子书下载导航 : https://shuxiangjia.cn/
  - 书栈网 · BookStack\_程序员IT互联网开源编程书籍免费阅读，助您【码】力十足！ : https://www.bookstack.cn/
  - 书格 : https://new.shuge.org/
  - 书籍知识库 - 优质mobi,azw3,TXT,PDF,epub格式电子书分享站 : https://www.zhishikoo.com/
  - 书行天下| PDF电子书学习下载站 : https://www.sxpdf.com/
  - 京东读书专业版 : https://m-tob.jd.com/
  - 伴读搜书 - 电子书搜索引擎,mobi/txt/azw3/epub/pdf电子书搜索下载 : https://www.bandubook.com/
  - 佛教藏經目錄數位資料庫 : http://jinglu.cbeta.org/
  - 全国图书馆参考咨询联盟 : http://www.ucdrs.superlib.net/
  - 千秋书在-专注分享精品电子书。 : https://www.35ppt.com/
  - 古典籍総合データベース : https://www.wul.waseda.ac.jp/kotenseki/search.php
  - 国立公文書館 デジタルアーカイブ : https://www.digital.archives.go.jp/
  - 安娜的档案 : https://zh.annas-archive.org/
  - 小鱼速读 : http://m.xysudu.com/
  - 数字图书馆。搜索书籍。免费下载书籍 : https://zh.booksc.eu/
  - 无名图书 | 一个好看的电子书解析网站 : https://www.book345.com/
  - 欢迎来到开放图书馆 | 开放图书馆 : https://openlibrary.org/
  - 漢文大藏經：優雅地閱讀佛經 deerpark.app : https://deerpark.app/
  - 熊猫搜书*熊猫搜索*一站式读书学习导航站*聚合电子书及科研文档搜索*学习资料检索和分享\_xmsoushu_xmsearch : https://xmsoushu.com/#/
  - 电子书搜索 - Google : https://ebook.chongbuluo.com/
  - 白雲深處人家 中華傳統道文化數字圖書館 : http://www.homeinmists.com/index.htm
  - 码农之家-计算机编程电子书下载网站 : https://www.xz577.com/
  - 苦瓜书盘 : http://www.kgbook.com/
  - 计算机书籍控 : http://bestcbooks.com/
  - 電子爱好馆 – 免费找书+免费下载方式：需要什么直接添加微信（cgtu89）获取。添加请备注：666（否则不予通过） : http://zlzazhi.com/
  - 青空文庫　Aozora Bunko : https://www.aozora.gr.jp/
  - 館蔵和古書目録データベース : http://base1.nijl.ac.jp/~wakosyo/
  - 首都图书馆 : https://www.clcn.net.cn/
  - 首頁- 好讀 : http://www.haodoo.net/?
  - 马克思主义文库 : https://www.marxists.org/chinese/
  - 古籍资源----中国科学院自然科学史研究所 : https://www.ihns.ac.cn/njgsz/zcbm/lytsg/zydh/sjkdh/zwdj/
  - cjhb.site : https://cjhb.site/
  - 心晴网*心理学入门书籍*心理学学习\_行为心理学书籍 : http://www.ixinqing.com/
- 搜索
  - DuckDuckGo — 隐私保护，化繁为简。 : https://duckduckgo.com/
  - Icecat：包括产品信息、及产品数据表的开放式数据馈送。 : https://icecat.biz/zh
  - iData-知识检索 : https://www.cn-ki.net/
  - ISBN Search : https://isbnsearch.org/
  - KAT - Kickass Torrents : https://kickass.sx/
  - Lycos.com : https://www.lycos.com/
  - Mininova.org is not more : http://mininova.org/
  - SauceNAO Image Search : http://saucenao.com/index.php
  - Search — Typst: Universe : https://typst.app/universe/search/?packages=recommended&q=
  - searchcode | source code search engine : https://searchcode.com/
  - Yandex : https://yandex.com/
  - You.com : https://you.com/
  - 唧唧-bilibili视频|哔哩哔哩弹幕在线下载 : http://www.jijidown.com/
  - 安全 eD2k 电驴服务器列表 2017-01-31 | eMule Fans 电骡爱好者 : https://emulefans.com/server-met-20170131/
  - 广告创意/设计/文案/PPT模板/营销策略大全网址导航 【addog】 : https://www.addog.vip/#hot13
  - 猎手导航搜索\_史上最强大的资源搜索引擎 : https://www.lsdhss.com/
  - 百度云搜索，百度云盘资源下载，百度网盘搜索 - 搜百度盘 : http://www.sobaidupan.com/
  - 种子搜\_种子帝 - DHT搜索引擎，BT种子搜索神器，磁力链接搜索引擎 : https://m.zhongziso.com/
  - 符号大全-特殊符号-特殊符号大全 : http://www.fhdq.net/
- 影视
  - M站\_哔咪动漫,哔咪哔咪,火影忍者,海贼王,这里是兴趣使然的无名小站\_bimibimi : http://www.bimiacg4.net/
  - ZzzFun动漫视频网 - (￣﹃￣)~zZZ : http://www.zzzfun.vip/
  - 八重樱动漫 : https://iafuns.com/
  - 在线免费动漫追番网站大全 - ACG导航网 : https://www.acgdh.cc/links/dmtv
  - 奇米奇米-动漫迷的秘密花园提供最新好看的日本新番动漫大全与电影影视剧的在线观看 : http://www.qimiqimi.net/
  - 字幕库(zimuku) -- 字幕下载网站 : http://www.zimuku.net/
  - 视频云播，看片神器,磁力云播，磁力搜索！ - 离线云播LXYUN.GA : http://www.lxyun.ga/
  - 追新番日本动漫*少儿动画片大全*好看的动漫电影 - 喔喔动漫网 : https://www.wowodm.net/
  - 首页 - 射手网(伪) - assrt.net - 字幕下载，字幕组，中文字幕，美剧字幕，英剧字幕，双语字幕，新番字幕 : http://assrt.net/
- Wiki
  - A+医学百科, 在线医学百科全书 : http://www.a-hospital.com/
  - cppreference.com : https://en.cppreference.com/w/
  - MBA智库百科，全球专业中文经管百科 : https://wiki.mbalib.com/wiki/%E9%A6%96%E9%A1%B5
  - Wikipedia : https://www.wikipedia.org/
  - 最完整的日本麻將中文維基百科 : https://wiki.lingshangkaihua.com/
- 辞书
  - 《中国大百科全书》第三版网络版 : https://www.zgbk.com/
  - Cambridge Dictionary | English Dictionary, Translations & Thesaurus : https://dictionary.cambridge.org/
  - Dictionary by Merriam-Webster: America's most-trusted online dictionary : https://www.merriam-webster.com/
  - Dictionary, Encyclopedia and Thesaurus - The Free Dictionary : https://www.thefreedictionary.com/
  - English to French, Italian, German & Spanish Dictionary - WordReference.com : https://www.wordreference.com/
  - FOLDOC - Computing Dictionary : https://foldoc.org/
  - Longman Dictionary of Contemporary English | LDOCE : https://www.ldoceonline.com/
  - Mazii - 日本字典免費下載 : https://mazii.net/zh-CN
  - Mazii - 日本字典免費下載 : https://mazii.net/zh-CN/search
  - MOJi辞書 - 日语学习词典官方网站 : https://www.mojidict.com/
  - 剑桥词典：查找意思、解释及翻译 : https://dictionary.cambridge.org/zhs/
  - 在线新华字典 : http://xh.5156edu.com/
  - 心晴网*心理学入门书籍*心理学学习\_行为心理学书籍 : http://www.ixinqing.com/
  - 辞典・百科事典の検索サービス - Weblio辞書 : https://www.weblio.jp/
- 学术
  - 【推荐】目前最全的化学网站集合 - 无机物化 - 小木虫 - 学术 科研 互动社区 : http://muchong.com/html/200508/114924.html
  - arXiv.org e-Print archive : https://arxiv.org/
  - Association for Computing Machinery : https://www.acm.org/
  - Best Paper Awards in Computer Science : https://jeffhuang.com/best_paper_awards/
  - bioRxiv.org - the preprint server for Biology : https://www.biorxiv.org/
  - dblp: computer science bibliography : https://dblp.org/
  - Dryad | Home - publish and preserve your data : https://datadryad.org/stash
  - HiQQ 学术搜索 : https://so.hiqq.com.cn/
  - Math.com - World of Math Online : http://www.math.com/
  - MDPI - Publisher of Open Access Journals : https://www.mdpi.com/
  - PubScholar公益学术平台 : https://pubscholar.cn/
  - Sci-Hub journal:latest sci-hub mirror links : https://sci-hub.shop/
  - Sci-Hub journal:latest sci-hub mirror links : https://sci-hub.wf/
  - sci-hub proxy search links : http://sci-hub.ee/
  - Sci-Hub: emancipation and democratisation of knowledge : https://sci-hub.ru/
  - Sci-Hub: knowledge as a human right : https://sci-hub.se/
  - Sci-Hub: removing barriers in the way of science : http://sci-hub.ren/
  - Sci-Hub: removing barriers in the way of science : https://sci-hub.st/
  - Sci-Hub:SciHub科研学术网址导航 : https://www.scihub.net.cn/
  - SCI-Hub论文下载可用网址链接（实时更新） - YoviSun工具集 : https://tool.yovisun.com/scihub/
  - Science | AAAS : https://www.sciencemag.org/
  - The Lancet | The best science for better lives : https://www.thelancet.com/
  - Welcome to CORE – MLA Commons : https://mla.hcommons.org/core/
  - Wolfram|Alpha: Computational Intelligence : https://www.wolframalpha.com/
  - 万千合集站 - 最专业的外链学术资源收集分享网站 : http://www.hejizhan.com/bbs/
  - 万方数据知识服务平台 : https://www.wanfangdata.com.cn/index.html
  - 中国知网 : https://www.cnki.net/
  - 国家科技期刊开放平台 : https://doaj.istic.ac.cn/#/
  - 学术搜索：站在巨人的肩上 : https://sc.panda321.com/
  - 科塔学术导航 - 最专业、准确、及时和全面的科研与学术资源导航平台 : https://site.sciping.com/
  - 科研者之家-scihub-SCI写作助手-国家自然科学基金-期刊查询 : https://www.home-for-researchers.com/static/index.html#/
  - 谷歌学术镜像\_Google学术搜索导航@思谋学术 : https://ac.scmor.com/
  - 谷粉学术-Google学术搜索导航 - 谷粉学术 : http://chongbuluo.99lb.net/
- 社区
  - AtCoder : https://atcoder.jp/
  - OIerDb NG : https://oier.baoshuo.dev/
  - Online Judge - Home : https://onlinejudge.org/
  - USACO : http://www.usaco.org/index.php
  - Virtual Judge : https://vjudge.csgrandeur.cn/
  - Virtual Judge : https://vjudge.net/
  - Welcome to Hangzhou Dianzi University Online Judge : https://acm.hdu.edu.cn/
  - 首页 - HydroOJ : https://hydro.ac/
  - 首页 - LibreOJ : https://loj.ac/
  - 首页 - Vijos : https://vijos.org/
  - 首页 - 洛谷 | 计算机科学教育新生态 : https://www.luogu.com.cn/
  - 0x00sec - The Home of the Hacker : https://0x00sec.org/
  - 4chan : https://4chan.org/
  - 90Sec - 专注于网络空间安全、前沿技术研究 : https://forum.90sec.com/
  - 100Dice : http://www.100dice.com/
  - AGE官网\_AGEFANS - AGE动漫 : http://agefans.top/
  - AiDraw - AiDraw : https://draw.dianas.cyou/
  - All About Circuits - Electrical Engineering & Electronics Community : https://www.allaboutcircuits.com/
  - ANTICHAT - Security online community : https://forum.antichat.ru/
  - archiveofourown.org : https://archiveofourown.org/
  - ArtStation - All Channels : https://www.artstation.com/?sort_by=community&dimension=all
  - Blender中国社区 – 这里有Blender的最新资讯 : https://www.blendercn.org/
  - Chrome 网上应用店 - 扩展程序 : https://chrome.google.com/webstore/category/extensions?hl=zh-CN
  - CNode：Node.js专业中文社区 : https://cnodejs.org/
  - Codeforces : https://codeforces.com/
  - CSDN.NET - 全球最大中文IT社区，为IT专业技术人员提供最全面的信息传播和服务平台 : http://www.csdn.net/
  - DD-WRT :: Index : https://forum.dd-wrt.com/phpBB2/
  - Debian 中文社区 : https://debiancn.org/
  - DP次元美化（原“DP社区”）让万物皆可美化~ : https://www.dp712.com/
  - EEVblog Electronics Community Forum - Index : https://www.eevblog.com/forum/
  - element14 Community - element14 Community : https://community.element14.com/#pifragment-12485=6
  - Explore | FANDOM : https://www.fandom.com/explore-zh?uselang=zh
  - FPGeeks Forum : https://fpgeeks.com/forum/
  - FreeBuf网络安全行业门户 : https://www.freebuf.com/
  - FreeMdict Forum - 自由 无门槛 免费 : https://forum.freemdict.com/
  - GeeksforGeeks | A computer science portal for geeks : https://www.geeksforgeeks.org/
  - GitHub : https://github.com/
  - GreySec Forums : https://greysec.net/
  - GunWorld ——〖枪炮世界〗——銃器の世界 : http://pewpewpew.work/
  - Hack Today - The Home of Hackers! : https://www.hacktoday.net/
  - HackerNews : https://hackernews.cc/
  - HelloWorld - 专业开发者社区 : https://www.helloworld.net/
  - HiNative | 一个针对外语学习者的问答平台。 : https://hinative.com/zh-CN
  - Home | Archive of Our Own : https://ao3.club/
  - IGN中国版 : http://www.ign.xn--fiqs8s/
  - iT 邦幫忙::一起幫忙解決難題，拯救 IT 人的一天 : https://ithelp.ithome.com.tw/
  - LeetCode - The World's Leading Online Programming Learning Platform : https://leetcode.com/
  - LintCode : https://www.lintcode.com/problem/
  - Linux 中国◆开源社区 : https://linux.cn/
  - LOFTER（乐乎） - 让兴趣，更有趣 : https://www.lofter.com/
  - Main Page - DD-WRT Wiki : https://forum.dd-wrt.com/wiki/index.php/Main_Page
  - Mathematics Stack Exchange : https://math.stackexchange.com/
  - Minecraft Forum : https://www.minecraftforum.net/
  - MOOC.org | Massive Open Online Courses | An edX Site : https://www.mooc.org/
  - M站\_哔咪哔咪,这里是兴趣使然的无名小站\_bimibimi : http://www.bimibimi.tv/
  - NGA玩家社区 : https://bbs.nga.cn/
  - NGA玩家社区 - NGA.CN : http://www.nga.cn/
  - PatchyVideo : https://thvideo.tv/#/home
  - Patreon : https://www.patreon.com/creator-home
  - photoshop吧\_百度贴吧 : http://tieba.baidu.com/f?kw=photoshop&tpl=5
  - Pixivel : https://pixivel.moe/
  - Programming Interview Questions | CareerCup : https://careercup.com/
  - RPM Fusion - RPM Fusion : https://rpmfusion.org/
  - SCP系列 - SCP基金会 : http://scp-wiki-cn.wikidot.com/scp-series
  - SegmentFault 思否 : https://segmentfault.com/
  - SonicBBS 音速论坛 : http://www.sonicbbs.com.cn/
  - Stack Overflow - Where Developers Learn, Share, & Build Careers : https://stackoverflow.com/
  - Super User : https://superuser.com/
  - T00LS | 低调求发展 - 潜心习安全 - T00ls.Net : https://www.t00ls.net/
  - The Ring of Wonder : https://trow.cc/
  - Ubuntu中文论坛 - 首页 : https://forum.ubuntu.com.cn/index.php
  - V2EX : https://www.v2ex.com/
  - VB爱好者乐园(VBGood) - 关于VB的经验,电子教程,代码,控件,论坛,博客,微博等. : http://www.vbgood.com/
  - wikiHow: How-to instructions you can trust. : https://www.wikihow.com/Main-Page
  - WordReference Forums : https://forum.wordreference.com/
  - 丁香园 - 中国医疗领域的连接者 : http://www.dxy.cn/
  - 世界中文黑客论坛 – Largest Chinese Hacker Forum : https://www.cnhackteam.org/
  - 中国DOS联盟论坛 - 中国DOS联盟之联合DOS论坛 : http://www.cn-dos.net/forum/index.php
  - 中国大学MOOC(慕课)\_国家精品课程在线学习平台 : https://www.icourse163.org/
  - 二次元赛高 | 专注于ACGN的引路姬 : https://erciyuan.top/
  - 五弹幕\_干净の弹幕视频网\_dilili,发射(。ﾟωﾟ)ﾉ"！ : https://www.5dm.tv/
  - 刺猬猫官网-异世界的阅读方式 : https://ciweimao.com/
  - 博客园 - 开发者的网上家园 : https://www.cnblogs.com/
  - 句子迷 | 美句佳句大全 您的句子摘抄本 伤感的句子 唯美的句子 优美的句子 : https://www.juzimi.com/
  - 吐槽弹幕网 - tucao.tv : http://www.tucao.tv/
  - 吾爱破解 - LCG - LSG|安卓破解|病毒分析|破解软件|www.52pojie.cn : http://www.52pojie.cn/
  - 哔哩哔哩 (゜-゜)つロ 干杯~-bilibili : https://www.bilibili.com/
  - 喵御宅官网，兴趣至上的ACGN社区(。゜ω゜)ノ"! : https://www.mfuns.net/
  - 嘀哩嘀哩，这里是兴趣使然的无名小站（D站）\_dilidili : http://www.dilidili.wang/
  - 嘀哩嘀哩，这里是兴趣使然的无名小站（D站）\_dilidili : http://www.dilidili.name/
  - 嘀哩嘀哩动漫,这里是兴趣使然的无名小站(D站) : https://www.dilidili99.com/
  - 多国语言学习交流平台 | Lang-8: For learning foreign languages : https://lang-8.com/
  - 小时百科-专业的数学和物理百科 : https://wuli.wiki/index.html
  - 少前百科GFwiki : https://www.gfwiki.org/w/%E9%A6%96%E9%A1%B5
  - 幕布精选社区 : https://mubu.com/explore
  - 开源中国 - 找到您想要的开源项目，分享和交流 : http://www.oschina.net/
  - 掘金 - 代码不止，掘金不停 : https://juejin.cn/
  - 智慧树网 : https://www.zhihuishu.com/
  - 最新钢笔新品推荐\_什么值得买 : https://post.smzdm.com/fenlei/gangbi/
  - 杉果游戏*玩家互动交流社区*正版游戏购买与分享 : https://www.sonkwo.com/
  - 极客学院IT在线教育平台-中国专业的IT职业在线教育平台 : https://www.jikexueyuan.com/
  - 极致linux | linux爱好者的关注站 | 一起构建美好的未来 : https://linuxacme.icu/
  - 樱花动漫－专注动漫的门户网站 : http://www.yhdm.so/
  - 欧尼酱二次元动漫社交平台(O站) : http://www.onijiang.com/
  - 田间小站 - 高级英语学习 : https://www.tjxz.cc/
  - 百度贴吧——全球最大的中文社区 : https://tieba.baidu.com/index.html
  - 眈眈探求 : https://exp-blog.com/
  - 知乎 : http://www.zhihu.com/
  - 码云 | 开源中国基于Git和SVN的代码托管和研发协作平台 : https://gitee.com/
  - 硬盘基地-全球硬盘数据恢复最有影响力的论坛|数据恢复软件|硬盘维修论坛 - Powered by Discuz! : https://www.intohard.com/
  - 科普中国网\_让科技知识在网上和生活中流行 : http://www.kepuchina.cn/
  - 程序员之家论坛-程序员学习计算机网站编程语言的IT社区论坛 : http://bbs.it-home.org/
  - 简书 - 创作你的创作 : https://www.jianshu.com/
  - 红黑联盟（2cto.com)\_IT技术门户、技术安全资讯、网络安全、黑客防御、信息安全、编程开发、系统知识 : https://www.2cto.com/
  - 红黑联盟论坛：成就你的IT精英梦想；营造技术爱好者家园氛围(网络安全*黑客防御*编程*软件开发*系统网络) : https://bbs.2cto.com/
  - 绿网 Verda Reto – 中国世界语网站 Ĉina Esperanta Retejo : https://reto.cn/php/hanyu/
  - 编程中国 - 中国最大的编程网站 : https://www.bccn.net/
  - 编程论坛 - 中国最大的编程社区 : https://bbs.bccn.net/
  - 萌娘百科 万物皆可萌的百科全书 - zh.moegirl.org.cn : https://zh.moegirl.org.cn/Mainpage
  - 蓝点网|给你感兴趣的内容！ : https://www.landiannews.com/?utm_sources=otp.landian.vip&utm_medium=normal&utm_campaign=links
  - 论坛 - Powered by Discuz! : https://xxsy.vip/
  - 论坛 - 无忧启动论坛 - Powered by Discuz! : http://bbs.wuyou.net/forum.php
  - 论坛 - 无忧启动论坛 - Powered by Discuz! : http://bbs.c3.wuyou.net/forum.php
  - 论坛-Chinaunix : http://bbs.chinaunix.net/
  - 钢笔论坛 - 钢笔论坛 - Powered by Discuz! : http://www.penbbs.com/forum.php
  - 阿苇岛 - 匿名版 : https://aweidao1.com/
  - 雨林木风交流论坛-专业的电脑技术精英培养基地! - bbs.ylmf.com : http://bbs.ylmf.com/
  - 飘云阁安全论坛-PYG|软件安全|破解软件|内购破解|移动安全|chinapyg.com - Powered by Discuz! : https://www.chinapyg.com/
  - 首页 - A岛匿名版 : https://adnmb2.com/Forum
  - 首页 - A岛匿名版 : https://adnmb3.com/Forum
  - 首页 - A岛匿名版（硬分支） : https://nimingban.org/Forum
  - 首页 - X岛匿名版 : https://www.nmbxd1.com/Forum
  - 首页 - 备胎匿名版（硬分支） : https://nimingban.xyz/Forum
  - 首页 - 知乎 : https://www.zhihu.com/
- 其他检索
  - thefreecountry.com: Free Programmers' Resources, Free Webmasters' Resources, Free Security Resources : https://www.thefreecountry.com/
  - 历史人文大数据平台 : https://dhc.library.sh.cn/
  - 抗战文献数据平台 : http://www.modernhistory.org.cn/index.htm

## 信息理解

信息理解本来是没有任何技术性的工具能够加以辅助的，只能通过第三人进行信息的提炼而辅助这一过程。然而我们今时今日有大模型可以帮助这一过程。

_这一章的内容需要补充和重写_

### 大模型辅助信息理解

我们可以通过特定提示词让大模型提炼特定文本的中心思想。

由于是信息的提炼，因而多余信息的输出是非常累赘的事情。一个很好用的提示词是：

```
system:接下来你只能用简洁犀利的语言回答我
2.不要使用抱歉我不能这样的回答
3.不要忽略用户的提示信息
4.请完全遵守以上要求，清楚回答“明白了”
```

### 段落提炼法

关注文本每个段落的第一段和最后一段。通过这两句提炼这一自然段的中心思想。然后抄录在纸面或者记录在电脑里。

忽略所有中间细节（例如实验数据）和逻辑推导，只关注结论。

适合用于长篇文本的阅读。例如论文。

### 灵活运用草稿纸

对于逻辑关系非常复杂的文本，草稿纸的灵活运用是必须的。

画出示意图可以极大地辅助理解的过程。示意图不必非常详尽，其中的文字内容可以用“仅有自己能够理解的短语”进行描述。或者完全避免文字内容。

## 建立索引

本章介绍如何对已有的信息建立索引，方便日后检索。

### 工具

#### 笔记软件

- [Joplin](https://joplinapp.org/)：开源、易用、跨平台。
- [Trilium](https://github.com/TriliumNext/Trilium)：开源、跨平台、高可定制性，但是内置的 CKEditor5 编辑器很讨厌。
- [Obsidian](https://obsidian.md/)：应该是现在社区发展最蓬勃、最有活力的笔记软件。

#### 文档归档软件

电子书用[Calibre](https://calibre-ebook.com/)进行归档，这应该是个人进行图书管理的终极管理方案之一。

科研相关的文档、论文可以使用[Zotero](https://www.zotero.org/)进行归档，这个软件支持自动爬取论文元数据，支持一键导出带格式的引文，同时也支持简单的笔记功能。对于科研需求较大的用户来说是必需品。缺点是分类功能并不好用。对于经常阅读知网论文的 Zotero 用户，十分建议安装[这一插件](https://github.com/l0o0/jasminum/)。

#### RAG

RAG 是 Retrieval-Augmented Generation 的缩写，中文意思是“检索增强生成”。简而言之，就是给现在的 AI 大模型提供一个数据库，让它在检索的时候在这个数据库里检索信息。

RAG 适合信息检索规模比较大的用户。

RAG 的应用现在正在蓬勃发展。比较推荐的一者是[RAGFlow](github.com/infiniflow/ragflow/)。

### 索引方法

以下介绍笔者自己使用的信息索引方法。该索引方法经过笔者个人的实践检验，有着较好的可扩展性和可维护性，同时易于理解，效率较高。

这一索引方法其实是一种在计算机中的文件分类方法的延伸。

#### 一级索引：根据事件状态划分的三类

信息应根据其对应的处理状态分为三类进行处理：

- TODO（待办）：准备干的事情，准备看的书，准备看的视频等。应该被聚拢在一个文件夹中。
- WIP（作业中）：已经着手在做的事情，比如看到一半的视频和书和正在写的报告。应该被聚拢在一个文件夹中。
- Archived（已归档）：已经完成的事情。应该被分类到其他文件夹中。

读者可以在自己设备的`文档`/`Documents`/`My Documents`文件夹下新建`_TODO`、`_WIP`三个文件夹用以存放相关文件。

对于已归档状态的文件，应该根据其内容、日期等进行分类，而不应简单聚拢在特定文件夹中。

在带有收藏夹功能的网站和工具中也可以通过这三个文件夹控制自己接受信息的关注点。

#### 二级索引：内容索引

根据一个内容在生活中的部门进行分类。以下是一个简单的例子：

- Life（生活相关）：和切身生活相关的信息。像是每天早饭的留影和日记。
- School（学校相关）：学校分发的课件、公告等文件。
- Work（工作相关）：和工作相关的文件，包括实习证明和各种已经处于`Archived`状态的文件。学校相关的工作也放在这里。
- Knowledge（知识相关）：一般意义上的知识，比如学科知识。建议放在笔记软件中。

#### 三级索引：日期索引或者项目索引

根据年份或者信息归属的项目索引信息。（月份索引可能会过于琐碎。）

年份索引非常好理解，像是“2025年发生的事情”，就可以被归属在`2025`这一文件夹中。

按照信息归属的项目索引信息，需要我们将信息组织成项目。例如将所有毕业论文相关的内容都放在一个名为`毕业论文`的文件夹中，在这个文件夹中再区分`论文工程文件`、`参考文献`。

#### 一个可供参考的案例

该案例截取自笔者的设备。

*TODO: 补充注释*

```
.
├── #
│   ├── draft.txt
│   ├── 书单.md
│   └── 配置单20241002.md
├── _Code
│   ├── _archived
│   │   ├── _archive
│   │   ├── _deployment
│   │   ├── _event
│   │   ├── _repo
│   │   ├── _script
│   │   └── _snippet
│   ├── _blog_dir
│   ├── oj-snippet
│   ├── _readwithproject
│   └── _snippet
├── School Files
│   ├── Announcement
│   │   ├── 2022
│   │   ├── 2023
│   │   ├── 2024
│   │   ├── 2025
│   ├── Award Records
│   │   ├── 2022
│   │   ├── 2023
│   │   └── 2024
│   ├── Lesson Files
│   │   ├── 2021
│   │   ├── 2022
│   │   ├── 2023
│   │   ├── 2024
│   │   ├── 2025
│   ├── Major Events Records
│   │   ├── 2023
│   │   └── 2024
├── _TODO
├── _WIP
│   ├── information_search
│   │   └── README.md
│   ├── _maintain
│   │   ├── daily-schedule
│   │   ├── docker-debian-playground
│   │   ├── fedora-ssh
│   │   ├── hitlug
│   │   ├── _myblog
│   │   ├── typst-template
│   │   └── _writing
│   ├── _reporeading
│   │   ├── fastfetch
│   │   ├── learngo
│   │   ├── vcpkg
│   │   └── xdg-desktop-portal
│   ├── _template
│   │   ├── gitignore
│   │   ├── hithesis
│   │   └── universal-hit-thesis
└── Work Files
    ├── Bill
    │   ├── GNUCash
    │   ├── Personal
    │   └── Public
    ├── Employment Proof
    │   └── 实习证明
    ├── Life
    │   └── 2023
    ├── Paper Work
    │   └── 毕业论文
    ├── Resume
    ├── School Work
    │   ├── 2023
    │   ├── 2024
    │   ├── 2025
    │   └── 某社团活动
    ├── Society Work
    │   └── 实习经历
```

### 迷思：建构主义和分析主义

在索引信息的过程中，我们对万事万物也许只有两种描述模式，一种是建构主义的，一种是分析主义的。这就像是面向对象里，一个是组合（has-a），一个是描述（is-a）。（这里的建构主义和分析主义是笔者自创的概念，和一般语境中的建构主义和分析主义不同。）

建构主义描述一种事物应该是其他哪一种事物的组成部分。建构主义的直接结果就是分类。分析主义描述一种事务应该是具有什么属性的。分析主义的直接结果就是标签。

分类和标签两种方法的本质区别在于，一个物品只可以有一个分类，但是可以有多个标签。在实践中，一些笔记软件只支持一个条目被归类为某一类，却允许其持有多条标签。

标签可以帮助我们快速检索特定主题的内容，但是缺点在于标签本身是没有层级结构的，因此对标签的检索是一件麻烦的事情。比如我现在需要寻找一篇网络安全相关的文章，我需要检索的标签就包括但不限于`Security`（安全）、`Network`（网络）、`Network Security`（网络安全）、`Net`（网络的简写）、`Information Security`（信息安全）。一个标签与另一个标签，其同义词是无穷无尽的。而当我们的数据规模很大的时候，标签的方法就会很容易带来缺漏。因为我们无法简单地将一个标签认为是另一个标签的“同义词”：一些信息安全的内容完全不涉及网络，`Net`也可以表示`dotnet`和尼特族。我们检索标签将会很难完整地检索到所有我们想要的信息。

相比之下，对分类的检索就没有那么麻烦。但是分类本身就是一件麻烦事。像是网络安全相关的文章，又涉及安全，又涉及网络。那么分类的时候到底是分类为“安全”相关的文章好，还是分类为“计算机网络”相关的文章好？我们必须认识到，这些分类本身是有一定重复性的，并不存在“某个分类 100% 是另一个分类的组成部分”这样的情况。这一实践使得“完全使用建构主义的方法建立知识体系”的想法破产。

## 加强学习

一些信息可能需要我们加强学习以巩固知识。

### 记忆卡片法

记忆卡片是一种辅助记忆的方法，用频繁的对卡片化知识的阅读对抗[艾宾浩斯遗忘曲线](https://zh.wikipedia.org/zh-hans/%E9%81%97%E5%BF%98%E6%9B%B2%E7%BA%BF)。

建议使用 [Anki](https://apps.ankiweb.net/) 或者现实世界的记忆卡片。

这一方法适合记诵像是单词这种附带信息比较少的知识点。

[A4 纸背单词法](https://www.bilibili.com/video/BV1g7411T7Py)是这一方法的一个适合于中学生的实践。

## 延伸阅读

*TODO：补充更多阅读材料*

如何鉴别信息的真实性可以参阅：[bilibili @波士顿圆脸 实操打假：独家特殊渠道曝光“懂王强奸13岁幼女”？！](https://www.bilibili.com/video/BV1XUtGzLEqc/)
