---
title: Breiman访谈实录
date: '2016-12-02T12:01:16+00:00'
author:
  - Leo Breiman
  - Richard Olshen
categories:
  - COS访谈
tags:
  - breiman
  - 数据科学
  - 机器学习
  - 统计学
  - 统计计算
slug: a-conversaton-with-leo-breiman
forum_id: 419175
meta_extra: 翻译：张晔、成慧敏、李宇轩；审稿：高涛、侯澄钧、丁鹏、魏太云；编辑：王佳、杨舒仪
---

> COS编辑部按：本文是一篇Richard Olshen对Leo Breiman的采访稿（[原文发表在Statistical Science](http://projecteuclid.org/download/pdf_1/euclid.ss/1009213290)）。翻译工作已经得到作者授权。翻译: 张晔、成慧敏、李宇轩。审校：高涛、侯澄钧、丁鹏、魏太云。此外，郑重感谢施涛、丁鹏、郁彬老师为文章的翻译指导和版权沟通提供的帮助。

![Leo Breiman](https://uploads.cosx.org/2012/02/Leo_Breiman.jpg)

1928年1月28日，Leo Breiman生于纽约。5年后，他们家搬到了旧金山，然后Leo开始了他的学业。在他读初中的时候，他们家又搬去了洛杉矶。1945年，Leo从Roosevelt高中毕业后考进了加州理工学院，在那里他花了4年时间主修物理。1950年，Leo拿到了哥伦比亚大学的数学硕士学位，1954年，他又拿到了加州大学伯克利分校的数学博士学位。

Leo对科学和数学有着广泛的兴趣，包括信息论和博弈论。他曾参与汽车交通、空气质量和有毒物质识别等方向的研究。 他写过一篇著名的关于概率论的毕业论文，他是分类回归树（CART, Classification and Regression Trees）及其配套软件_CART_<sup><i>R</i></sup>的四位作者之一，另外他还写了两本专著。Leo和Jerome Friedman一起开创了ACE（alternating conditional expectations）算法，该算法描述了因变量和自变量之间的非线性回归关系。 他开创性地提出将“bagging”和“arcing”这两种需要大量计算的方法用于分类，目前很多学者对此十分感兴趣。

Leo的职业履历包括，加州大学洛杉矶分校（UCLA）数学系教职，13年的独立咨询顾问，加州大学伯克利分校（UC Berkeley）统计系教授，同时也是该校统计计算实验室的创始人兼主任。 另外，他还是斯坦福大学和耶鲁大学的客座教授。 由于他的诸多贡献，Leo被授予数理统计研究所（Institute of Mathematical Statistics）和美国统计协会（American Statistical Association）的荣誉基金。 同时，他还是美国艺术与科学学院（American Academy of Arts and Sciences）的选举成员，并被加州大学授予Berkeley Citation荣誉奖项。

Leo Breiman是一个兴趣广泛的人，他不仅是专业的统计学家和概率学家，还在其他方面也取得了很多成就。他在Catskills当过服务员，在Merchant Marine当过洗碗工，同时他是一名探寻过热带雨林核心地带的背包客，是一群来自墨西哥农村孩子的慈爱父亲，是Santa Monica学校董事会的主席，是他美丽小屋的建筑师，还是一个技艺高超的雕刻家。Leo和他的妻子Mary Lou，居住在加州伯克利，他们育有两个女儿，Rebecca和Jessica。

采访者简介：Richard Olshen，斯坦福大学生物统计教授，生物统计方向（Division of Biostatistic）首席科学家，卫生研究和政策系（Department of Health Research and Policy）的副主任，斯坦福大学电气工程系和统计系兼职教授。该访谈于1999年2月19日在Leo和他的妻子Mary Lou的家中进行。

**Olshen**：Leo，今天能来到这里，我感到非常荣幸。我是你的粉丝，在跟你合作之前（事实上，是我认识你之前）我从你的著作中学习到了很多。我了解到你是在洛杉矶的Boyle Heights长大的，Boyle Heights在那个时候是什么样的？

# BOYLE HEIGHTS

**Breiman**：Boyle Heights那时候还是个贫穷犹太人和工薪犹太人聚居的贫民区，与墨西哥贫民区相邻。基本上，它是第一代移民的贫民区。我的父母，同龄小伙伴的父母都是移民。

而且我们都是去罗斯福高中上学，这所高中致力把移民的后代培养成医生、律师和科学家。 这是一个很美好的地方。 你可以走进一家熟食店，从泡菜桶里拿出一根泡黄瓜，然后沿着街道一直走，欣赏晾晒在两边的意大利腊肠。这些对于来自纽约下东区（纽约市曼哈顿区沿东河南端一带，犹太移民聚居地）年幼的我来说可都是高档货。

**Olshen**：也许还有更好的天气。

**Breiman**：是的。

**Olshen**：你什么时候把对数学和科学的兴趣结合起来的呢？

**Breiman**：我在高中的时候对几何很感兴趣，因为几何是第一门让我印象深刻的科目。 你知道吗，当你解决完代数或者加减乘除之类的问题之后，挑战几何问题是一件全然不同而且令人着迷的事，以至于我们一群人在研究它的时候根本停不下来。

**Olshen**：关于罗斯福高中所在的社区你还有什么其他的能告诉我们的吗？是什么促使你对加州理工学院(Caltech)感兴趣并真正加入加州理工学院的呢？

**Breiman**：嗯，虽然罗斯福周边那时候从社会经济学的角度看是洛杉矶最穷的社区之一，但从办学角度看罗斯福高中是一流的。 而这其中的原因也许和Bronx科学高中之所以成为一流高中的原因是一样的。

这里充满了有激情的移民家庭的儿女，大家都明确地知道一定要上大学。 而激发我去加州理工学院的原因，是我母亲听说加州理工学院是西海岸最好的研究型大学，于是她决定她儿子应该去加州理工学院。

**Olshen**：你有兄弟姐妹吗？

**Breiman**：没有。

**Olshen**：所以唯一的儿子干什么真的非常重要。

**Breiman**：没错。

# 加州理工学院

**Olshen**：能跟我讲一下你还在加州理工学院的时候，那儿是什么样的吗？

**Breiman**：好的。那年申请加州理工学院的有几千人，但是最终录取的只有250人。为了能被录取，你必须参加共计16个小时的考试，因为他们完全不认你的高中成绩。 你必须参加数学、物理、化学和英语四科的考试，每科考四小时。这是我们所有人都绞尽脑汁的16个小时。

在加州理工学院的第一年，我确实表现得很好，也拿到了奖学金。但是第二、三、四年，我变得越来越烦闷，我厌倦了每天听到的不是科学就是工程，这让我开始封闭起来。这个地方就像是一个科学修道院。

所以，我的成绩开始急剧下滑，在我最后一年时，我的主修科目物理得到了4个D。

**Olshen**：这是促使你去加州大学伯克利分校研究生院的原因吗？

# 哥伦比亚大学研究生院

**Breiman**：不是，实际上是虽然我毕业时的物理成绩太差了，但是我还是对数学很感兴趣。虽然我在数学方面成绩很好，并且到处申请，最终只有纽约的哥伦比亚大学接收了我。我的父母还是挺贫穷的，所以没法承担我在哥大的学费。

但是由于之前打工存了一些钱，我最终还是去了哥大。然后我用1年的时间在哥大获得了数学硕士学位，但是实际上我最开始去哥大时是想主修哲学的。

当我到了哥大之后，我和当时赫赫有名的哲学系主任Erwin Edwin交谈了一番。他语重心长地拍了拍我，说道，“你看，我两个最优秀的博士生现在都没找到工作。你为什么不待在数学系，然后上一些哲学系的课看看呢？”

然后我就上了一些哲学系的课，比如说美学和希腊哲学等等。 这都不是我想要的，所以最终，我还是决定回归数学。

**Olshen**：能告诉我们具体的时间吗？

**Breiman**：那是1950年的时候，我从哥大拿到硕士毕业学位1年之后，我申请了伯克利的数学系，他们接受了我。为了能支付学费，我一个暑假都在Catskills（卡次启尔山脉，位于纽约的南部）当服务员，另一个暑假则在美国商船学院（Merchant Marine）打工。

**Olshen**：美国商船学院（Merchant Marine）听起来挺棒的。

# 伯克利研究生院

**Breiman**：是的，在我20岁之前，我这样打工挣了很多钱。我在船上当洗碗工，一下船就得去监考，监考是所有伯克利助教必须干的事。从码头叫了一辆出租车，我迅速地奔向大一新生考试的地方Dwinelle，所以——

**Olshen**：所以你的航海生涯和数学生涯交错进行？

**Breiman**：确实是。

**Olshen**：太牛了。能跟我们讲讲David Blackwell对你的影响吗？可以讲讲其他跟你一起在伯克利学习的人吗？我其实是想把这些问题和这两个主题联系起来：一个是Shannon–Breiman–MacMillan理论(Breiman, 1957)，另外一个是你在博弈论方向的研究成果(Breiman, 1960)。

**Breiman**：好的，我当时是在伯克利的数学系，那会儿还没有独立的统计系。那个时候，Neyman招揽了几位知名学者，比如说Michel Loève。当时，我上的概率论这门课就是他教的，我非常喜欢这门课，我喜欢概率论。

这是一门很好的课，一门大概只有10个学生的课。Manny Parzen也在这个课堂里，还有Howard Tucker，还有一两个后来在统计界声名远扬的人。然后我写了一篇论文，但是Michel Loève是一个完美主义者，他让我在论文上不断改进。

**Olshen**：我情不自禁地回忆起来，我大一刚入学那会儿，我的导师就是Michel Loève。当时作为一名大一新生，我战战兢兢地去办公室找他，他对我说的第一句话就是，”你最好全部课程都得A，不然我会把你从窗户扔出去。”

**Breiman**：这听起来很像是Michel的风格，所以每次我写完论文觉得这已经很不错的时候，Michel都会说“我不知道”。Harold Cramer来到了伯克利一学期，我在他组织的研讨会上提交了我的论文结果。

他说，“我必须跟Michel好好谈谈，我觉得这篇论文已经很不错了。” 但是，这时候一件更加重要的事情发生了，我收到了一个来自征兵局的通知，通知上说“注意！你已经用尽了所有的延期时间，我们希望在30天之后看到你。”

所以我给Michel提交了我最新一版论文的复件，同时把那个征兵局的通知也放在上面。Michel盯着它看了很久，然后说，“好吧，我们必须让你尽快离开这里了。”大概在两周之后，他组织了论文的最后答辩，然后我的论文获得了通过，我当时激动极了。离开伯克利之后，我服役了将近两年。

**Olshen**：等一下，让我们往回倒一下。你的毕业论文和Shannon–Breiman–MacMillan理论有关，还是和你的博弈论研究有关呢？

**Breiman**：都不是。事情是这样的，当时军队有个规定是，如果你能找到工作，你就可以提前两个月出去，所以我写信给Neyman教授，他给了我一个代理助理教授的工作，于是我就回来了，也就是那个时候我开始结识了David Blackwell。

我们那个时候一起开研讨会，他经常拿一些笔记来问我，“你会证明这个、这个和这个吗？” 有一次，他给的一个笔记上写着，“你能证明这个几乎必然可以收敛于下面的式子吗？” 我想了好些天，然后我觉得我可以做到，我觉得我已经有思路了，Shannon–Breiman–McMillan理论(Breiman, 1957)就是这么诞生的。和Dave Blackwell一起工作十分鼓舞人心，他思考问题的方式真的非常了不起。

**Olshen**：是Dave Blackwell促使你进入博弈论这个领域的吗？

**Breiman**：不是的，这完全是因为我自己。我当时在思考凯利（Kelly）规则。

**Olshen**：跟我讲讲怎么回事。

**Breiman**：凯利规则大概是说，如果你在一个有利的赌局中下赌注，你就可以赢得无穷多的钱。这也不是一定的，但是至少你的期望收益会是无穷的。我思考了一下凯利规则的结果，然后意识到从中可以推导出参加有利于自己的赌局时的最优策略。

这是我研究博弈论的动机，完全是因为机缘巧合。David没有参与进来，而且我觉得他应该对博弈论并不感兴趣。

# 在墨西哥卖冰

**Olshen**：大家都知道你涉猎广泛，其中你在墨西哥卖冰那件事非常吸引我，但是我到现在也不是很了解，你能跟我讲讲这事儿吗？

**Breiman**：好的，实际上那是因为我的几个朋友在1964年或者1965年去了Puerto Vallarta，具体年份我记不太清楚了，但是正好就是在Night of the Iguana(译者注：即《巫山风雨夜》，1964年上映的电影，Puerto Vallarta是片中一行人的目的地，在墨西哥)这部电影上映之后的一年。 当时，Puerto Vallarta还只是一个小城镇，在那里所有的水必须煮沸才能饮用（译者注：美国人一般都是直饮自来水的，而墨西哥的自来水因为质量问题并不能直饮）。

还有就是，如果有人在你的饮料中加了冰块，千万不要喝。 因为当地的冰块都是用当地的水做的，都充满了细菌。所以我的朋友就想出了一个点子：把纯化的制冰机送到墨西哥，并且建立一个专门净化冰的工厂，这个想法同样让我觉得很有趣。

我觉得这很棒，我说，“我也要投资”。接下来他们买了一栋旧得几乎摇摇欲坠的建筑，叫做El Bucanero。 他们在这里建立起了冰厂，这是一个伟大的成功。然后这个厂净化出来的冰在Puerto Vallarta远近皆知，因为他们从冰的中间把杂质吸出来，所以看起来像一个甜甜圈。在Puerto Vallarta，无论你走到哪，你都可以看到一杯装有甜甜圈冰块的饮料。没多久，市长的儿子也决定开始做净化冰的生意。 果然，我们所有的顾客都跑去光顾市长儿子的生意了。所以我们的生意就黄了，但是净化冰这件事持续下来了，这挺棒的。

**Olshen**：听起来不错。

**Breiman**：嗯，是的。

# 在UCLA的几年

**Olshen**：现在我要继续和你谈谈你在UCLA的职业生涯了，其实我是想问一些我一直非常想知道的事。 就是你怎么想到写Probability(Breiman,1968)这本杰作呢？

**Breiman**：我加入UCLA是因为，我在伯克利只有一份署理职位（译者注：署理职位一般不能超过6个月）。 那时的规则非常严格，如果你是一名伯克利的博士生，那么你铁定不能在伯克利找到你的第一份工作。那么接下来对我来说，去UCLA似乎是最好的选择了。

所以我走进了UCLA数学系大楼说，“我是来求职的。”他们收到了一些关于我的信件，然后我获得了一份工作。我在这儿一待就待了7年，实际上我很快就拿到了终身教授的职位。我是他们唯一的一名概率学家，所以我教研究生概率论的课程，教了大概3到4年。

在整个教学过程中，我一直专注于概率论中的证明，直到搞懂内在的原理。

在UCLA待了大概7年之后，我对我自己说，“Leo，你天生就不是做抽象数学的料，它虽然很有趣，但不是你该做的工作。”于是，我辞职了。

**Olshen**：到那时，你已经写了这本书了吗？

**Breiman**：还没有。

**Olshen**：那个时候还没有吗？

**Breiman**：没有。

**Olshen**：好吧。

**Breiman**：所以我拿出了放在我退休金中的钱，然后我花了6个月的时间专门来写这本书。 这是相当长的一段时间，因为写这本书需要很强的纪律性。 但是同时这个过程又充满了乐趣，它是我的处女作。

因此，当3、4年前SIAM([美国]工业及应用数学学会)找到我说，“我们想在经典系列中再版你的书”时，我喜出望外。

**Olshen**：我听说你在UCLA工作期间，还去了非洲。

**Breiman**：是的，确实是这样。我想要一个不同寻常的休假，所以我去了联合国教科文组织（UNESCO），然后我对他们说，“我不想在大学里教书，你们能给我什么别的机会呢？” 最后联合国教科文组织告诉我，“我们有一个在利比亚当教育统计学家的机会给你。”

所以我就以一名教育统计学家的身份去了利比亚，那么他们需要什么呢？他们需要知道全国所有学校里的学生有多少人。为什么这会是个难题呢？因为整个国家只有50英里铺设好的道路。很多学校都在热带雨林丛林里，这些地方看起来根本没法进入。所以我们组了大概20支队伍，以骑车、划船和走路的方式走遍全国，深入到那些小村庄，把学校里的孩子们都叫出来，然后数一下人数。

所以我住在那里，艰苦跋涉去了很多边远地区，经过了各种热带雨林丛林中通往村庄的隧道。 很神奇的是，当我到达村庄的时候，小孩子们会过来搓我的皮肤，看看能不能把我皮肤上的白色搓下来。 那是一种非常有趣的体验。我几乎爱上了在非洲的生活，但是很遗憾要离开那里。

**Olshen**：跟我讲讲你与Bill Meisel的合作，以及你是如何去TSC公司（Technology Services Corpoeration）工作的。

# 作为独立顾问

**Breiman**：从UCLA辞职之后，我花光了我的退休金，很显然我需要干一些别的事儿来养活我自己。 所以我四处询问，得知当时Rand旗下的SDC公司（Systems Development Corpoeration），有一大笔联邦科研经费用于高速公路交通研究。

我之前写过一篇关于交通流量服从泊松分布的文章(Breiman, 1963)，而且我认识一个从事道路交通研究的人，他对我说，“你为什么不给SDC当咨询顾问呢？”所以接下来的一年我就给SDC当咨询顾问了。 研究高速公路交通流量数据长什么样以及它的统计特征是什么，这是一件充满乐趣的事。

之后这笔科研经费花完了，所以我又开始四处询问。另一位顾问Pete Payne告诉我，“我觉得TSC在招聘顾问。”所以我去TSC应聘，Bill Meisel面试了我。我们交谈了一会儿之后，他说，“OK，你被录用了，你什么时候可以开始呢？”Bill是一个十分有趣的人，因为他在南加州大学（USC）工程系任教过。

**Olshen**：你之前在加州理工学院的时候就认识他吗？

**Breiman**：不，完全不认识。他还写过一本关于模式识别的书。 TSC基本上就有一个雷达室，一个防御策略研究室，不是一个很大的公司，里面大概就有五六十个技术人员。 Bill当时就管理这些奇奇怪怪但是没多大价值的部门，然后他决定集中精力让它成为一个环保部门。

所以我开始给环保部门当顾问，我们两个开始写提案给EPA（Environmental Protection Agency，美国环保署）和加利福尼亚州空气污染董事会等。我们开始赢得了很多赞成和支持。 我开始做一些由EPA资助的空气污染研究、水污染研究和其他各种各样诸如此类的工作。 我们遇到的很多问题都涉及到大量的数据，比如说在一个重要项目里我们有7年每天每小时的空气污染数据，涉及到450个和空气污染相关的变量。 那时我们尝试预测洛杉矶盆地第二天的臭氧浓度。

Bill非常有助于我思考分类和回归的问题。对于EPA和周围很多其他提供研究经费的地方来说，大多数的问题都是预测和分类，这是一个热门领域。 Bill对于这个领域还是挺熟悉的，是他推动我进入了这个领域。

**Olshen**：听起来这是_CART_<sup><i>R</i></sup>(Breiman et al., 1984)的开始。

**Breiman**：是的，说的没错。我们在研究预测问题，诸如第二天洛杉矶盆地的臭氧浓度， 高速公路上的一氧化碳浓度，还有一些其他的研究，比如是否能识别出摩尔斯电码是从哪个手机上发送的（这是我们为间谍机构做的事）？或者我们能否通过声呐返回技术识别出潜水艇是俄罗斯的还是美国的？或者我们能否通过雷达回波技术识别出战舰是俄罗斯的还是美国的？很多这些问题都是迷人的分类问题。同时，对于几乎一切能看到的有趣的统计需求，Bill他都会提交经费申请。

比如，我们做的其中一项是科罗拉多州刑事法庭的出庭推迟研究，我们也为刑事法庭系统做了一些其它的工作。我也EPA设计了一些调查，以及指导EPA如何管理调查结果。

因此，从这一大堆不同的工作中我对统计学有了更加深刻的认识，我也学会了在尝试解决问题时，如何使用统计学和处理数据。这些回答了你的问题吗？

# 在SANTA MONICA参加校董事会和教数学

**Olshen**：当然了。现在看来，这些工作全部或者说很大一部分都是在Santa Monica进行的。我对你在Santa Monica进行的其他工作很好奇，比如说，Santa Monica校董会，你是怎么参与其中的工作，还成为它的领导者的？

**Breiman**：好的，让我从稍早一点说起。我的朋友和我了解到在Puerto Vallarta以北30英里有个小村子叫Mezcalse。尽管那时候我还只是个单身汉，但是我在同时照顾两三个孩子。他们是我朋友们的孩子，他们去了沙特阿拉伯工作，同时认为那里不适合带上小孩。

所以他们算是把孩子托付给我。其中一个是小男孩，两个年长一点的女孩带着他玩儿。我想找另一个男孩来平衡一下，但我找不到，因为没有哪家父母愿意把孩子交给我照顾。这时有人建议我，何不从Mezcales村那里收养一对墨西哥小男孩呢？

我经历了美墨两国的官僚主义地狱，但我还是排除万难让这两个小孩和我住在了同一屋檐下。那时我住在Topanga Canyon。他们和我的美国小孩一道上当地的语法学校，这是巨大的成功。

我收养他们的一个理由是：那个村子里全是自耕农，而且只有旅游业一个大产业，所以学英语是这些孩子们摆脱自耕农的唯一出路。到那一年年底，这些孩子们已经可以用英语交谈了。

他们讲得非常流利。所以接下来的夏天，我让头两个孩子回到了他们父母身边，他们的父母非常高兴，为我带来了另外三个。如此持续了7年，我总共养大了21个孩子。这时我对Santa Monica的校区情况已经了解得非常清楚了。

另外，本地的老师都很喜欢我的墨西哥小孩，而且——

**Olshen**：从Topanga Canyon到Santa Monica的学校是一趟挺长的旅程。

**Breiman**：是的。我当时还是单身，当着顾问。所以我要非常小心地安排一切。不管怎样，我最后搬到了Santa Monica，因为Santa Monica相关部门抓住我了。我的意思是，他们发现我其实住在Topanga，那里属于洛杉矶校区。所以孩子们要去洛杉矶的学校，那里的教学水平可不大好。我用了一个住在Santa Monita的朋友的地址，送他们去Santa Monica上学。他们去那个房子访问，发现了这个事情，然后他们告诉我——

**Olshen**：他们是指？

**Breiman**：他们是指Santa Monica校区的官员们。

**Olshen**：明白了。

**Breiman**：他们告诉我，“要么你在30天内搬到Santa Monica，要么这些孩子得退学。”所以我搬去了Santa Monica。我对这个校区的各方面情况已经了解得十分清楚了。

当我还在UCLA的时候，我已经认定，孩子们接受数学教育的方式错得一塌糊涂，他们惶恐地将数学看成一门可怕又无聊的科目，和他们身边的日常世界没有一点关系。所以我决定亲自教两个五年级生数学。我教的其中一个孩子在UCLA——他们开设了一所实验学校，面向有情绪障碍症的孩子——另一个在一所中上水平的学校，并且——

**Olshen**：你为此付出很多吗？

**Breiman**：不，不。相反我过得相当愉悦。孩子们也很快乐。我们玩了各种各样的游戏。他们并不知道他们在搞数学，但是他们在学习诸如如何玩战舰游戏。同时他们还学笛卡尔几何，学代数，总之他们在游戏的引导下学习各种复杂的东西。

并且，你知道吗，我们会玩这样的游戏：“好，那是多远？这堵墙多高？”孩子们就会猜，然后我试着绕着圈子问，“不爬上去，我们要怎样才能量出它到底有多高？”，诸如此类。

一方面，我所有的孩子都在Santa Monica的学校上学，另一方面，我对如何在语法学校教数学很感兴趣。这两个原因让我觉得Santa Monica校区需要我，所以我去参加了校董会的竞选。

有趣的是，Santa Monica认识我的人很少。当我跑去教师工会谋求背书，跟他们说的时候，他们回应是：“我们挺喜欢你说的东西，但是我们不能支持你，因为你根本没有胜算。”而民主党的人也不支持我，因为他们说，“啊，你在这里没有缴费。”

但我非常努力，我发起了一个效果良好的选举宣传，我到处和人谈话，挨家挨户拜访，站在超市里派发传单。最后，令我自己和别人都大吃一惊的是，我获选了。

**Olshen**：你是怎样当上校董会主席的？

**Breiman**：那时候，Santa Monica校董会主要由本地商人组成。那时的Santa Monica还是一个相当保守的城市。本地商人尊重我对教育感兴趣这个事实。所以他们先是提名我当副主席，而副主席会在下一年自动接任主席。我必须说校董会的商人们对于提高Santa Monica的教育质量有着真实诚挚的兴趣——比校董会里其他的政治人物和一些激进派的成员都要真挚。

**Olshen**：算上你的写作以及在两所大学的教学，还有你在私立学校的教学生涯，你教了许多人。你有没有找到教育的一种通用的哲学主题或者精神，不论对象是Santa Monica的五年级生还是伯克利的天才研究生都适用的那种。

或者说有没有什么不变的主题，这些主题是渗透到了你不同程度教学和你的写作中的？你刚才谈到了让数学变得有意思，并且让数学联系到我们周围的生活——

**Breiman**：有的

**Olshen**：——比如说？

**Breiman**：让我仔细想想。和孩子们在一起，我可以确定地说他们学习数学失败的结症在于转化的过程，也就是说，他们无法把教给他们的乘法或者其他别的来自这个封闭小世界（指数学）的东西和他们现实的生活中实际的内容对应起来。

这和他们处理单词问题时的无能为力很相似。在单词问题里面，你必须做的事情就是拿起英语，使用魔法词汇“令 x 等于”。换句话来说，你必须将英语文本翻译成数学。

我觉得那些数学很好的人就是那些可以将真实世界和数学世界对应起来，将我们说的话翻译成数学语言的人。我认为这贯穿了我所有级别的教学。我们从一个明确的问题开始，在进一步抽象之前我发觉我会先构思好解决整个问题的流程。在把问题变抽象之前，你要尝试把问题具体化。

# 回到伯克利以及统计计算实验室(SCF)

**Olshen**：谢谢，接下来，你是怎样来到伯克利的？还有，为什么会来？

**Breiman**：在我当咨询顾问期间，我获得不少回到（用我朋友的话来说就是“改邪归正”）大学工作的工作机会。我也感到很诧异，不过我不是特别想去，因为我在咨询行业工作得十分愉快。在那儿我一直在解决实际问题，用数据说话，这些都是我很热爱的。

但有天我忽然接到Peter Bickel打来的一个电话， 他说：“你要不要来伯克利讲一个学期的课，搞个讨论班？”然后我说：“好啊。” 于是我回到了伯克利，度过了一段愉快的时光。

之后，我回到了洛杉矶，大约一年后，我接到另一个电话——我记得这次是 Dave Brillinger 打来的，他问我：“你愿意来这担任教职吗？”

现在看来，确实那时世界上只有一个地方可以说服我回去学术界，那就是伯克利。我在这里完成了（博士）研究生工作，仍还有很多朋友，我爱这里，所以，我回答他：“好。”

**Olshen**：当你来到这里的时候，你是已经有一个创立统计计算实验室的想法了？还是说，随着时间发展你逐渐有了这个想法呢？跟我讲讲这个过程，你是如何争取资源，如何管理，以及在你看来，它的未来会变成怎样。

**Breiman**：可以的话，先让我准备大约一分钟吧，Richard.

**Olshen**：好的。

**Breiman**：你看，当我离开大学的时候，某种意义上，我已经破釜沉舟，断了回大学的路。因为这些年，大概13年里，我都只是一个咨询顾问，好像只出了一本出版物，我的意思是，你不会付钱给一个咨询顾问让他去出书，你付钱是为了让他解决问题的。

所以我觉得，伯克利居然给了我一个高级教职，这很不寻常啊。而且，我都不知道这件事情他们是怎样操作的。好像没有人适合告诉我内情。我想有朝一日我会去问个水落石出的。

**Olshen**：但这个任命还没有带来什么坏消息，也许随它去就好了。不过，还是给我讲讲关于统计计算专业的事情。

**Breiman**：事情是这样。我到伯克利的时候，系里所有的计算基本上都是在中央计算实验室楼下做完的。

**Olshen**：埃文斯楼楼下？

**Breiman**：就在埃文斯楼里。他们有一个大的多核主机，我们系里只有一个小的 PDP-11 (译者注：一款DEC公司出售的16位微机)，它的主内存只有32kb，还有其他各种各样的问题。我记得我第一次去中央计算实验室时，我问他们，“你们有什么统计包吗？”

他们回答，“啊，我们貌似有 BMDP (译者注：由加州大学洛杉矶分校的 Wilfrid Dixon 开发的一个统计软件包)。不过，我们没有整个包，我们只有一部分。”

于是我又问，“那好，你知道你们有哪些部分？”

他们却说，“我们得先去看看，找找看吧。”

我原计划教多元分析。很显然，如果要挖掘各种数据的关联，我们系必须要有一个合适的计算实验室，这样看的话，埃文斯的地下室显示不适合。所以，我心中暗想，“好，我要做的第一件事，就是建立一个足够好的计算实验室。”

那是1980年，我们可以买到的最好的微机是VAX 750。它的售价在我们的价格范围内。它有一个16位系统，内存很大，打折之后售价大约75,000美元。

**Olshen**：做这些事情，有来自学校当管理层的支持吗？还是说全都是统计系的功劳？

**Breiman**：都是统计系的功劳。我们可没钱啊。

**Olsehn**：嗯哈。

**Breiman**：你懂的，我所有的，只有手中咯咯作响的一只锡杯。

**Olshen**：还有墨西哥的制冰机！

**Breiman**：对。所以我开始到处打电话，看看能不能找到联邦机构为 VAX 提供资金。 最后我找到海军研究办公室(ONR)的 Ed Wegaman 。 我对他说，“Ed， 如果我们还想做一丁点儿应用研究，我们就一定得要有电脑。”

他问：“多少钱？”

我答道：“7.5万美元。”

他说：“好，给我发一份计划书。”

最后Ed帮搞定这些事情。那是我们第一台VAX 。我们把他组装起来，招了个研究生做系统管理员。自此之后，事情变得轻松了————一旦你破开冰层，事情就变得简单了。后面我们还拿到了许多捐款和赠送，现在我们有4个全职高级成员，每年管理着2000账号，还有大量的计算资源，也为经济系和生物统计系提供计算支持。

**Olshen**：在你组建SCF的同时，伯克利UNIX小组也开始崭露头角。统计和伯克利UNIX小组之间有什么联系吗？在VAX上也跑 UNIX或者VMS吗？

**Breiman**：关于这个，有个很有意思的故事。我来伯克利的时候，David Freedman还是主席。而Dave ，我觉得他和我在伯克利就职有很大关系，因为他和我相互了解很久了。那时Dave还用我们的PDP-11， 他被计算深深吸引住了。

PDP-11当时运行着UNIX，而数学系的家伙有问题却需要在RISTUS操作系统下解决（这是一种可以在 PDP-11 上跑的操作系统）。所以我们有个协议，4天跑UNIX三天跑 RISTUS。所以呢，Dave Freedman 每隔三天或者四天，就要跑去更换操作系统，重启电脑，如此循环折腾。

**Olshen**：哈哈，有意思！

**Breiman**：是的：）

# CART, ACE, PIMPLE, THE LITTLE BOOTSTRAP, BAGGING, BOOSTING 和 ARCING

**Olshen**：现在，让我们继续下个问题。我想听听你近年来的研究工作。不分顺序，我能想到的是 ACE (Breiman and Friedman, 1985), PIMPLE (Breiman, 1991), the little bootstrap (Breiman, 1992), bagging (Breiman, 1996a, 1996b), boosting (Freund and Schapire, 1996, 1997), arcing (Breiman, 1998), 和 _CART_<sup><i>R</i></sup>。不管以后会怎样，但它们现在很流行，已经不是统计学的私房话了。

**Breiman**：大概可以从 UCLA 辞职之后开始吧。我认为最重要的工作就是你也参与了的CART，那真是一段激动人心的时期，所有的创意想法在你、我还有Jerry Friedman和Chuck Stone之间来回碰撞。

不过，CART那本书(Breiman et al., 1984)出版后，我想我们全部——也许你不像其余三个那么严重——都厌倦了跟树相关的思考。我们一口气干得太猛，有点腻了。所以我们的兴趣转向了别的地方。但Jerry和我还一直保持着讨论。

Jerry和我都是被Bill Meisel招进到TSC当顾问的。所以在我来伯克利之前，我和Jerry已相熟多年了。而Jerry 和我能继续保持着讨论，主要原因是我觉得我俩是为数不多的关心高维数据分析的统计学家。

我们的一个话题，一个非常重要的问题——那是86年或者87年—— John Tukey一直在讨论的问题，“在线性回归中如何做变量变换，以取得更好的预测效果？你应该用 log _X_还是用 _X_? 还是其他方式？”

Jerry和我花了一段时间来仔细推敲这个问题，忽然发现可以使用交替光滑的技巧来处理这个问题。我越想越激动，而我正好有一台旧苹果电脑，是一个第一代有64kb内存的桌面电脑。它有一个彩色屏幕可以让你编程，所以我打电话给 Jerry，说：“Jerry，快来，我在苹果上写代码，来看看它会不会有效。”

然后我们输入 _Y_ = _A_ log _X_ + _B_ 这样来模拟数据，在Apple上跑了ACE 的早期版本。每次在苹果的屏幕上输出一次迭代结果的时候，我们可以看到变换的迹(trace)(译者注: 一个矩阵的迹是其特征值的总和，亦即其主对角线上各元素的总和。)

那台苹果电脑很慢，看到一个迹的结果后，Jerry 和我就去喝杯啤酒，然后再回来看下一次迭代得到的迹。到了半夜，终于可以判断，这该死的东西可以收敛到 _X_ 的对数。我知道我们成功了，之后我们需要做的事情就是写下来，加上理论和更多的实验。

而我们之所以把这个技术命名为 ACE，缘起于这样一个小故事：Jerry和我有天在Shattuck Avenue 酒吧喝酒，讨论该起个怎样的名字。Jerry坚持叫ACE, 因为这个名字很帅，而且它是交替条件期望(alternating conditional expectations)的缩写。不过我不太愿意，我说：“Jerry，这有点过了。我们怎能叫它ACE呢？”

然后忽然，Jerry 指着街对面，那里恰好有一个单词 “ACE”。 他说：“看那个。”好像那冥冥中自有天意一样。确实，我们当时看到的是Ace硬件商店的招牌。于是我相信Jerry 是对的，它应该叫ACE (Breiman and Friedman, 1985).

**Olshen**：噢，那命名PIMPLE (Breiman, 1991) 也这样有故事吗？

**Breiman**：不。PIMPLE不一样。我——

**Olshen**：先给简单讲点PIMPLE ？

**Breiman**：好的。我当时对泛涵逼近很感兴趣，因为你可以把很多多元回归问题看作加了噪声的泛涵逼近。所以我读了很多高维泛涵逼近的文献。

在泛函逼近方法中，它们常用单变量函数乘积的和来逼近函数。就是说，如果你有一个核函数 `\(K(x, y)\)`， 你可以用`\(F_i(x)\)`乘以`\(G_i(y)\)`的积来逼近它。看到这里时，我仿佛醍醐灌顶，我想：“为什么不试试将函数展开成简单函数乘积这种办法来做回归的逼近呢？”

而乘积符号是pi(译者注：`\(\Pi\)`), 这便是pi的来历。然后pi之后的单词是 “implementation（实现）”，那么，自然而然的它们缩写是什么呢？PIMPLE啊!

**Olshen**：那arcing, bagging 和 boosting这些算法呢？

**Breiman**：嗯，这些算法很迷人。在过去5年，预测方面有突破性的进展。而我认为，组合预测器就是两个大突破之一。这个想法就是，嗯，我们假设你用CART，它是一个相当好的分类器，但还不够好。我的意思是，在某些情况下，神经网络好得多。

**Olshen**：嗯，在适当训练的情况下？

**Breiman**：是的。

**Olshen**：跟一个没有训练好的CART相比？

**Breiman**：对。就是如此。我想我当时一直在考虑这个问题。我曾写过一篇关于线性回归中的变量子集选取的文章。我发现线性回归中的子集选取问题非常不稳定。如果你稍微扰动一下数据，回归的五个最好的变量就会变成另外的五个。所以我想：“我们可以通过给数据加扰动把它稳定下来，得到五个最好的预测变量。然后再次扰动数据，再拿到五个最好的变量，最后把这些五变量的预测器作一个平均。”这样做的效果确实很好，在Annals上也发了一篇文章(Breiman, 1996b) 。

而CART也有同样的特性。你知道的，如果你稍微改变数据，你会得到一棵非常不同的树。所以我就想，“那好，为什么我不试试在CART上做同样的事情呢？如果我改变数据生成一棵树，然后再次改变数据，生成另一棵树，最后取它们的均值或者让它们投票选出票数最多的类，没准我能提高准确性。”

所以问题变成怎样扰动数据？我那时候意识到，基于理论上的考量，最好就是从原始的数据集出发，从中自抽样(bootstrap)，根据自抽样样本生成新的树，再自抽样获取新的样本，在上面再生成另外的树。最后，如果是回归，我们就取它们预测的均值；如果是分类，就让它们投票选票数最多的类。

我把这种方法命名为 “bagging”，意思是“自抽样聚合”。它的结果非常漂亮，有效提高了预测精度，令人非常振奋。而后， Yoav Freund 和 Robert Schapire (Freund and Schapire, 1996, 1997) 想出了一个算法，叫作 Adaboost。 Adaboost 采取了让训练误差尽可能快下降到零的技巧将分类器组合在一起。它确实相当快，在大多数我见过的数据集里面，它用3到4个分类器就能把训练误差降低到0。

但很有趣的是，即使在训练误差下降到零之后，你继续往Adaboost算法里面组合更多的分类器，测试集的误差会在训练机误差为零之后依然下降。甚至在你组合了，比如说，一百个分类器之后，测试集误差还在下降。

你去看Adaboost的时候，你会发现，它用了一种比较复杂的方法，去增加那些在上一轮里面被误判的样本的权重，新的训练集就是根据这个权重去取样，而不是像bagging 那样等概率地抽样，之后把新的训练集交给分类算法去训练。这个算法效果好得不可思议。

在人们见过的大部分数据集里面，Adaboost比bagging 好很多。这是一个惊人的发现，简直就是化腐朽为神奇。就是，你用一个分类器，比方说一个常见的CART, 它是一个好的分类，但又不是特别好，但是用了Adaboost算法之后，这个编程很简单，只需要迭代调用 CART，它就变成一个顶级分类算法。

所以问题变成：为什么这个复杂的算法做得这么好？

**Olshen**：嗯，我们稍缓一下。我们现在在讨论boosting ?

**Breiman**：对，是Adaboost。 当人们说起boosting的时候，通常就是讨论Adaboost。 它是一个巧妙奇怪且不是那么好理解的算法。

**Olshen**：那acing (Breiman, 1998) 呢？

**Breiman**：arcing是这样来的。我第一次思考Adaboost 并仔细观察它的时候，它的思路变得很清楚。它增加了那些难以分类的样本的权重，即在两类边界上的观测样本。

所以你仔细思索这个方法，就会有一整套的算法可以做同样的事情。你可以写出很多这种增加可能被错误分类的样本的权重的算法，而最后结果都相当好。我把这类或自适应抽样，或自适应调权重，以及组合的算法统称为 acing。也就是说，我可以给出一个特定的arcing算法能与Adaboosting相媲美。

当然，组合方法、boosting和bagging，不必一定使用树来做，几乎所有分类器都可以去做。这套组合逻辑适用于所有回归问题和分类问题。比如有一篇仅使用了简单超平面的分类器的好文章，不过超平面是随机超平面(Ji and Ma, 1997)，用 arcing 算法将这些随机超平面组合起来后，便得到了惊人的好结果。

所以你看，整个事情变得越来越有趣了。

# 人口普查

**Olshen**：好的，继续进行对大数据集研究的讨论，不过会与之前我们讨论内容大不相同，你可以谈谈你在人口普查调整这块的工作吗？

**Breiman**：我想想，在大约1987或1988年的时候吧，有一天David Freedman突然对我说：“走，咱们一起去吃午饭。”

当我们一起吃午饭的时候，他说：“你愿意去人口普查委员会，参与制定1990年的人口普查计划吗?”

我说：“不，我还不想那样。但我会告诉你我想干什么。我会参与人口普查计划，但我不想加入到委员会中。”于是他便让Ken Watcher加入了委员会。

Ken做的很好。在1989年末开始准备1990年的普查时，Dave给我打了个电话，大意是“普查就好像是我自己的血肉一样,我希望你加入这次普查。”于是我只好对他说“行。”

之后Dave和我开始奔波，前往各类为2000年普查而设立的普查办公室。他真的和一些调查员一起走街串巷，去观察普查是如何实施的。

在这些工作结束之后，大家分成了两拨人。一拨是直接负责计数的人，而另一种是调整人口普查结果的人。错过普查的人数估计大约为总人口的2%，大概是五百万人，调整的方法主要是基于捕获再捕获的想法。我先对这个想法做个简单介绍。

这是一个很简单的想法。假设你想知道一个湖里有多少条鱼。所以你去到那开始一直钓鱼，每次你钓上来一条鱼，你都会在它的背上作一个红色标记。

你最终完成并数了一下所有标记的鱼，一共10000条。你推测你自己已经钓完了所有的鱼，但并不太确定。所以你接下来要做的事情是一周后回到这个湖边，然后抓100条鱼，看一看它们之中有多少是背上有记号的。

现在你抓了一百条鱼，并且看一看它们之中有多少背上有标记。如果刚开始你确实钓完了湖中所有的鱼，那现在这100条里的每一条背上应该都有标记。但是你看着它们,发现只有98条背上有记号，所以你就会发现自己第一次钓的时候，有2%的鱼没上钩过。

池塘中一共有超过10000条鱼，而我事实上低估了2%。不过这里面有一个大问题：有些人发现两条在背上没有标记的鱼，可能它们其中的一条背上是原本有标记的，但被擦掉了。那么这个比率将不再是2%，而会下降到了1%。

可能还有些人还仔细检查了另一条鱼,并且发现可能这条鱼背上也是有个标记的，这种情况下100条鱼中全是标记的鱼，说明你第一次钓鱼进行估计时并没有少算。所以，你必须要知道100条鱼中有多少条是背上有标记的，这样才能准确地估计少算量。

现在，为了估计在1990年普查时的少算量，他们先做了普查，在普查之后他们又做了一个小样本的调查，我记得好像是50000户家庭吧，我记不太清具体的数字了。之后他们尝试通过匹配小型普查和原始普查的人，来观察两次调查的一致程度有多高。

举个例子，如果在小型调查中，有2%的人在原始普查中找不到，他们就会猜测普查的少算量为2%。同样，对于那些小型普查和原始普查没有匹配上的人，在了解了他们的特点和所在地的情况之后，调查员们也就可以知道错过普查的人都具有什么特点，以及这些人所在地的情况如何。

所以现在的问题是，这种调整的精确度有多高？这变成了一个很重要的法律案件，因为众议院里各州的议员席位数量是根据普查的人口数量来分配的，所以很多州都希望进行普查调整，他们都感觉自己州被少算了。

因此，普查调整意味着一小部分议会的席位可能由一州转向另外一州。此外，从联邦政府流向各个城市和各州数以亿计的钱，也是基于人口普查的数据。所以，究竟是采取原始的普查数据还是调整后的普查数据，这个问题是一个政治和经济的大问题。

所以我说：“好，Dave，这就是我要做的事情。”普查局已经用上千页的文档，来讲述大量的调整估计法，“我会一页一页的仔细查看那些方法，并且看看这个调整进程的准确性。”

我在工业届得到的经验是，如果你有一个数据集，你首先要做的事情是，尝试去确定目前你的数据质量如何，有多少是缺失的，有多少是错误的等等。这些都是历经挫折后才能学到的经验。于是我开始了审查，而结果让我十分惊讶。

检查过程中，我发现很多所谓的调整，是由于明显的错误而导致的。我们要意识到，一方面，小型调查中你获得了100个美国人的100份资料；另一方面，你又拿了在原始普查中的100份资料，但问题是他们之中的多少是能匹配上的？

很多时候人们在普查时给的是不同的名，他们提供了不同的年龄、性别，你没办法将它们对应的那么好。你需要匹配了99%的人，才能有50%概率确定少算量就是2%。但核心问题是，由于美国人的流动性、移民社会地位等等因素的影响，匹配精度根本不可能达到99%。

如果你用了那些数据做调整并且评估了的话，错误会越来越多。正如你所知道的，我最终在Statistical Science (Breiman,1994)写了一大篇文章，归纳了所有我之前基于普查文档所做的研究，给出了结论：由于有不良数据，而且主要是在匹配时的错误，造成了超过80%的人口普查结果进行了有问题的调整。

然而，Richard，接下来的事却让我大跌眼镜。普查委员会承认，它内部的出版物中至少有57%的内容是有关1990年调整，确实是不良数据造成的。你可能会认为在被1990年的数据和评估打击如此之狠之后，他们应该不会再这么做了。因为如果有些环节失败了,你就不能再去重复了。好吧，他们在2000年所做的事情更有意思。他们竟然又做了一遍，但是却不评估了!

# 建议

**Olshen**：Leo，你在统计学、统计计算、概率和教学这些方面有广泛的兴趣和贡献，你想对那些现如今想从事这个方向工作的年轻人提什么建议呢？他们应该学些什么以及为什么?

**Breiman**：好吧，Richard，在某种程度上，我感觉我好像分裂了一样。因为我可能会告诉他们：“不要去学统计。”我感觉在一定程度上，统计的学术方向可能已经迷失了。当我离开咨询顾问的职位，回到伯克利时，我感觉我好像进入了爱丽丝梦游仙境一样。意思就是，就统计应用的角度而言，我知道工业机构和政府在发生些什么，但是目前进行的学术研究却似乎离我们无比遥远，好像只是抽象数学的某一分支一样。前阵子我们这一学科的一位老前辈说：“我们需要保持Wald的精神不朽。”但别忘了，在Wald时期以及统计与数据割裂之前，那是Fisher的鼎盛时期，而Fisher相信统计的存在是为了预测、解释和处理数据的。(译者注：Fisher认为统计是为了预测、解释、处理数据；但Wald在此基础上将根据数据进行决策加入到了统计的范围内。)

在你今天早晨来之前，我翻出来了Webster词典并且找到了统计的定义，它是这么定义的：“收集、处理和分析事实或数据，并展示某种事物的主要信息。”如果使用单个动词来描述它，就是”一门收集、分类、处理并且分析事实和数据的科学。”

然后，如今统计的学术圈里都没有那个定义了。举个例子,我正在看Annals（译者注：Annals和JASA都是顶级统计期刊），我估计二十篇里页也就一篇有数据或者把它的方法应用到了某种数据上吧，JASA里的比例也高不到哪里去。所以我的观点是：统计中吸引人的东西与目前的学术研究已经相去甚远，分道扬镳了。

在过去的五六年里,我与机器学习和神经网络领域的人走的很近，因为他们正在为一些复杂的、困难的预测问题做一些非常重要的应用工作。他们以数据为方向，所做的也与Webster对统计的定义相一致，然而，他们几乎全都不是受过训练的统计学家！

所以我认为如果我现在要给年轻人提建议的话，学统计学，我持保留意见。但最后，我可能还是会说：“去学统计吧，但一定记住，统计的精髓之处是在收集和利用数据，来解决现实世界中有趣而又重要的问题。”

# 艺术家

**Olshen**：谢谢！从我们今天谈话的房间，甚至是整个房子的风格可以看出，你的兴趣爱好涉猎颇广。你能谈谈作为艺术家的你是什么样子的吗？

**Breiman**：嗯，当我在洛杉矶做咨询顾问的时候，我只用花很少的时间就可以挣不少钱，所以我便有大把的空闲时间。我记得我初次来到伯克利时的第一个室友，他是主修艺术的，我很喜欢他，他便鼓励我去做雕刻，而且我也用粘土做出了一些东西，我当时并没有想太多。

所以在洛杉矶这段空闲时光里，我便在UCLA Extension报了一个雕刻班。那里有一个很棒的老师，他鼓励我们去做各种各样疯狂的事情。在那我还认识了Alf Peterson，咱俩曾和他见过一次面，他在威尼斯有一家铸铜的铸造厂，是一个了不起的人，他对我说：“如果你想练习的话，就来我的铸造厂吧，我会展示给你看如何做这些事情。”

我用粘土、蜡和风屏做了一个人物。就在那，在那个角落，就是我的第一个“天使”（指向雕塑）。我拿着它去到了Alf的铸造厂，他说：“好，我将给您展示如何铸铜。”

他向我展示了如何制作那个“天使”的模子，如何制作底盘，如何把它们放到烤炉中，如何注入铜等等。我十分好奇，被这一切深深地吸引了。我觉得这些都很有意思，所以我从那时起就保持了这个爱好，热衷这些东西。

最近我开始用石头雕刻，也非常有意思！所以你会发现你周围石制的头像到处都是。这是一项漫长的工作，你需要坚持用锤子和凿子不断敲打。

**Olshen**：我觉得我的问题已经问完了。Leo你还有什么简短的想法吗？刚才的采访是否有趣呢？

**Breiman**：非常有趣，Richard。你知道，有时候我对统计感到很伤心。现在有很多聪慧的人加入到这个领域中，我希望统计学能变得更好，而不是变更坏。

**Olshen**：或许你自己的例子会给大家带来正面积极的影响。谢谢你，Leo！

**Breiman**：那将是我的荣幸，Richard。
