---
layout: post
title: "AI数字绘画：何时从AIGC迈向AIAD？"
categories:
  - 可以攻玉
tags:
  - 城市设计
  - AI绘画
---
# 引言

## AI数字绘画技术的发展历程

最近一年多的时间里AI技术凭借大模型和新的算法在诸多领域产生了可见的突破性进展，对于普通人而言基于AI的图像处理和文本处理技术已经逐步改变了我们的生活。AI绘画技术悄然兴起然后受到广泛的关注，这是一个如此典型的范例一方面让我们感受到了AI的强大，另一方面又不得不重新思考我们与AI的关系：我们是不是马上会被技术替代了？

首先来看看这一波AI绘画技术发展的历程：
	- 2021年1月，OpenAI 公布了 DALL-E，奠定了扩散模型在这一波技术发展中的重要性。
	- 2021年10月，开源的文本生成图像工具 disco-diffusion诞生，此后有相当多的基于此的产品出现。
	- 2022年7月，OpenAI旗下人工智能在线绘图应用DALL·E 2在7月份的公测。
	- 2022年8月，stability.ai开源了Stable Diffusion , 这是目前可用性最高的开源模型，很多商业产品都基于此，如 NovelAI。10月18日，Stability.ai宣布完成 1.01 亿美金的种子轮融资，估值达 10 亿美金。
	- 自从几个重要的开源模型发布以来，基于次开发的一些门槛较低的AI绘画生成平台多次在社交网络上爆红，早几个月的Midjourney以及近期国内发布的意间AI等产品吸引了众多没有技术背景的素人参与AI创作和讨论，并开启了诸多商业渠道的流量密码。（更多相关内容推荐阅读《[万字解读AI绘画商业化之路：工具、作品与版权](https://mp.weixin.qq.com/s/RQXR2F0Z7302e_6YbH2lgQ)》《[从起因到争议，在 AI 生成艺术元年聊聊 AI](https://sspai.com/post/76277)》）

## 站在这个时间点讨论AI绘画与设计

除了猎奇和投机，也已经有很多相关行业的从业人员从各个方面讨论了**AIGC(Artificial Intelligence Generated Content)** 对于各个行业的影响，最多的包括艺术创作行业与设计行业。由于早期的AI模型（disco-diffusion等）相对于现实的场景更擅长生成富有想象力和艺术感的作品，有很多讨论集中在【AI创作是否能称之为艺术？】【AI绘画如何辅助创意生成？】

当时AI生成的真实感作品质量还相当捉襟见肘，所以并没有什么讨论围绕在环境设计（建筑、规划、景观、城市设计等）相关的领域。然而随着模型的快速迭代，仅仅经过不到一年的时间现在最新的模型已经在真实风格作品上有可圈可点的表现，之前被诟病的诸如【人物失真】等问题也一一得到解决。

最早想要写这么一篇文章是在9月左右，尽管由于各种原因拖拖沓沓了两个月，但是所幸这两个月还尚未发生重大的变革让这篇文章成为一纸旧闻。在这里我主要想探讨在这个时间节点的AI数字绘画技术对于环境设计行业意味着什么？有哪些现在已经可以被实现的新的工作流程/方式？并且基于现在各方面的技术成熟度聊聊AIGC在何时可以迈入**AIAD（Artificial Intelligence Aided Design, 人工智能辅助设计）**？

## 关于训练模型等技术细节

我并不想在文中过多地涉及技术细节，因为我希望探讨的是更一般的情况而不是某个具体的模型与参数的性能。所以把自己在尝试过程中的技术相关的内容写在这里。

首先我大多数情况下使用的模型都是部署在colab上的stable diffusion模型，早期的时候使用的是没有GUI版本的，最近使用的都是带GUI的版本，相对来说更为易用。如果有尝试的意向可以参考以下的内容：
 1. [AI数字绘画 stable-diffusion 保姆级教程](https://mp.weixin.qq.com/s?__biz=MzkyOTIxMDAzNw==&mid=2247492892&idx=1&sn=c69e4d2782098efc644b151dbd2049d5&chksm=c20faec6f57827d0442f5697b1a5a31ee15933956e45302411ecbee3b8708c5b218bd8e1d4e9&scene=21&token=1095602716&lang=zh_CN#wechat_redirect)
 2. [Best & Easiest Way to Run Stable Diffusion for Free (WebUI)](https://bytexd.com/best-way-to-run-stable-diffusion-for-free/)
 3. [fast-stable-diffusion Github](https://github.com/TheLastBen/fast-stable-diffusion)

接下来简单地说一下为什么采用stable diffusion。

最主要的原因是它完全免费，配合colab的话甚至不用消耗自己的算力，相对来说同期的Midjourney，NovelAI等都是有限额或需要付费的。

其次尽管部署难度相对其他打开即用的平台更高一点，但若作为生产力工具评估的话这点学习成本完全不算什么，并且是一次部署长期使用。

第三尽管不同的模型有着各种优势，在我测试的当口相对来说大家可能都更推崇Midjourney的质量，但根据我的考察其质量的优势还是体现在少量图片生成时的创意程度似乎更高，在不进行反复调试的情况下生成的图片更加符合我们的需要，但这个特点在生产环节的重要性被缩小了，在现在这个阶段我们并不期望AI能为我们直接生成作品（因为环境设计也并不是以图像作为成品提交方式的），我更看重在快速迭代和修改中呈现出的创意和可使用的意象，在这个需求中自己部署的模型采用批量训练的方法一次训练几十上百张图片可能是会更常用的方式。

# 当下的AI能如何帮助我们做设计？

## 单纯的text2img效果怎么样，能做效果图吗

使用AI绘画的第一步当然是text2img，顾名思义就是通过文本生成图像，一般需要输入一定长度的文本描述（prompt），AI首先通过语义的模型理解文本的含义，然后再基于此生成图像。这样生成的特点是能最大化表现AI模型的创意，往往输入者在一开始对要画什么并没有特别具体的想象，而是希望AI生成一些出人意料的结果。很多模型都有官方的prompt编写指南，但基本上需要包括三方面内容：主体内容、要素/特征、风格。也由于使用文本表达，很多太过具体的描述如空间方位等很难被AI精确地理解，当然还有一个原因在于为了保证生成图片的合理性和质量，生成的时候往往会对文本的内容进行重新采样，也就是说写的所有内容不一定都会对AI的创作产生影响。所以很多prompt的写法并不在于事无巨细地描述，而是通过有明显导向的词语让AI知道你想要什么，比如网上与建筑相关的prompt中最为神奇的词汇莫过于【Zaha】，仅仅四个字母就可以让你生成突破想象的奇幻建筑……

由于这样的特征，文本生成最适合用来寻找灵感，输入一些较为模糊的意向和要素进行大批量的生成，然后在其中挑选一些尚可的结果作为设计或表现的参考。其实这样的方式在其他的设计领域如婚礼设计、服装设计等已经有所应用，只是相对来说环境设计对真实性的要求更高。

那么AI现在能生成什么样的图片呢？其实如果去[Lexica](https://lexica.art/)这样的网站上就可以看到已经有相当多跟城市相关的优质作品，只不过由于大多数和CG艺术相关并不是非常写实：
![](https://github.com/Boycetoon/MinusType/blob/master/image/AI%E6%95%B0%E5%AD%97%E7%BB%98%E7%94%BB/1..jpg?raw=true)

其中有的图像质感已经相当不错，比如参照Lexica上的案例生成的未来城市的一组图片：
![](https://github.com/Boycetoon/MinusType/blob/master/image/AI%E6%95%B0%E5%AD%97%E7%BB%98%E7%94%BB/2..jpg?raw=true)
**prompt:**  Futuristic glasgow with buildings and skyscraper, green square, multi-layerd trees, Air platform and bridges sunny day, volumetric light, reflections, hyperdetailed, artstation, cgsociety, 8 k

其实在我刚开始尝试AI绘图的时候网络上已经有建筑或景观设计师尝试生成了更加真实的图像：

![](https://github.com/Boycetoon/MinusType/blob/master/image/AI%E6%95%B0%E5%AD%97%E7%BB%98%E7%94%BB/3.jpg?raw=true)

从上面生成的结果已经可以看出在真实感上现阶段的AI已经表现得相当不错，整体图像粗略来看不太容易看出违和之处，尽管如果放大细看还是能找出不少瑕疵。但是这种【基本不违和】的能力对于生成看起来真实的图像十分重要，这代表了需要有基本正确的空间关系、光照和阴影等，尽管这些细节仔细看来仍然是【不正确的】，但是毕竟大多数人也不会用画法几何的眼光来审视所有的图像。也就是这种【基本不违和】的能力让AI绘画有了更多的可能性。

为了试验AI在更复杂场景生成的可能性和创意能力，我继续尝试了以滨水城市为主题的批量生成：

![](https://github.com/Boycetoon/MinusType/blob/master/image/AI%E6%95%B0%E5%AD%97%E7%BB%98%E7%94%BB/4.jpg?raw=true)
 **prompt:**  a beautiful rendering of city near by river,  low-rise buildings with roof garden and multi-story platforms, high-rise skyscrapers crowded in center,  built by wood and metal and other modern materials, designed by SOM and MVRDV , amazing parks  in front of fiver, clear sky with sunlight,  8k, octane render, architecture photography, hyper detailed,  epic lighting
 
可以看到由文字批量生成的图片构图的多样性十分丰富，尽管整体风格还是相似，但是却能生成各种类型的场景，说明文字的详细描述对于图像的约束力有限，同时生成的这种随机性能为方案早期的创意阶段带来一些新的可能。反过来说，由于生成的图像太不一致，没法将这些图看作是一套方案，也就是说每张图都有其随机性，之间是没有关联的，由于这样的特性让AI生成无法满足方案及之后过程的工作需要，毕竟要是每张图都是不同的样子，那本身就是对设计的消解。

## img2img是现在更好的选择吗

要是让设计师想象一种理想的与AI交互的方式，那么多半会是自己画一张设计草图然后让AI生成完整的方案，可见相对于文字而言传统的设计流程其实更加依赖图像信息。现有模型中img2img功能就可以在这个方面进行一定的探索，相对于text2img来说它需要另外输入一张原始图片供AI学习然后生成结果，这个过程中文字prompt和输入的原始图片共同影响最终的结果。

当了解这个功能的基本运行过程后，作为设计师的一个想要尝试的就是：是否可以输入一张手绘的方案草图或者建模软件中的体块模型让AI帮助我们深化方案？

![](https://github.com/Boycetoon/MinusType/blob/master/image/AI%E6%95%B0%E5%AD%97%E7%BB%98%E7%94%BB/5..jpg?raw=true)
![](https://github.com/Boycetoon/MinusType/blob/master/image/AI%E6%95%B0%E5%AD%97%E7%BB%98%E7%94%BB/6..png?raw=true)
*以上两张图中第一张都为原图*
 
我尝试了将比较简单的体块模型和分析图作为输入来生成，虽然确实能得到一些意料之外的结果，但是这些结果似乎比较难和生产环境中的具体需求结合起来。可以发现AI并没有生成逼真的效果图，而是生成了类似分析渲染图的样式，这似乎是由于AI对于输入图片的学习是均等的。我们都能理解一张图片由色彩要素（颜色、材质、阴影、光照）和形态要素（形态结构、空间关系）组成，我们其实原本希望AI着重学习草图中的大体形态关系，而对具体的材质、景别、微观样式等进行深化。然而不如我们所愿，扩散算法对图像的学习似乎是不区分颜色和结构的， 所以当我们想要它学习形态结构（也就是方案）的时候它往往会对颜色过度学习而对形态学习不足，结果就好像它在帮我们出方案而不是做效果图。

考虑到输入图像的特点，这似乎告诉我们对输入的图像有更高的要求：如上面所说，最好能在颜色和结构两个方面都对AI做出指引。一开始想到的是手绘草图的形式确定色彩和结构，但现于个人绘画水平没有进行更多的尝试，另一个问题是涂色的草图容易被AI学习出更接近卡通或者绘画的风格。所以后来我想到的是在一个白模底稿的基础上迁移另一个图片的颜色来达到合成的效果，然后以迭代的形式多次训练图像以控制生成的方向。

![](https://github.com/Boycetoon/MinusType/blob/master/image/AI%E6%95%B0%E5%AD%97%E7%BB%98%E7%94%BB/7..png?raw=true)
**prompt:** a beautiful 3D rendering of waterside  port city,  low-rise buildings with roof garden and multi-story platforms, built by wood and metal and other modern materials, designed by SOM and MVRDV , amazing parks  in front of fiver, Villa residential area, clear sky with sunlight,  8k, octane render, architecture photography, hyper detailed,  epic lighting
 
最终确实生成了看似效果图的图像，但是其另外一个缺陷缺依然明显，那就是输入图像的影响控制是全局的，但是往往我们希望它深化的只是其中一部分。比如上图中我希望它对于码头重点建筑可以有多样的变化，但周边的环境最好尽量不要在形态和布局上有太大的变化。这就要求模型能允许我们对图像的各个区域分别设置学习的强度。

所幸现在的模型中已经提供了一个相近的功能，允许对输入的图像进行蒙版绘制，然后单独控制蒙版部分的强度。Midjourney已经支持了绘制的时候直接通过不同透明度的方式来控制学习的强度，但由于这个控制可能需要反复试验我暂时没有进行更深入的使用。不过使用这个功能也能实现一些设计过程中一些常用的需求，比如说建筑方案比选：

![](https://github.com/Boycetoon/MinusType/blob/master/image/AI%E6%95%B0%E5%AD%97%E7%BB%98%E7%94%BB/8..png?raw=true)

在这个例子中蒙版内生成的内容能较好地符合周边环境特征，当然如玻璃反射等的效果还是相当不足，不过也说明了上面提到的流程的可能性。早在stable diffusion刚刚开源的时候网上就出现了对应的ps插件，能根据ps中的蒙版、基础图像和文字描述来生成局部的结果，然后将多个局部拼合在一起成为完整的作品（[https://www.youtube.com/watch?v=dD9vpO2zaJw](https://www.youtube.com/watch?v=dD9vpO2zaJw)）。我认为要是希望AI能在正式的生产环境中起到作用这样的流程是值得推广的。

**那么就现在而言有没有什么相对更加成熟和可用的流程呢？**
就我近期的使用体验而言现在用AI来根据参考图生成意向图是一个相对可用的应用场景。由于前面提到的一些缺陷：随机性太高、对细微结构的学习不足、对输入图片在颜色和结构都有要求，我们可以直接将一张小场景（非鸟瞰）的效果图或者实景图作为参考图输入让AI来帮我们生成构图和配色相近的意象图。

这里以一个步行街道的效果图作为例子：

![](https://github.com/Boycetoon/MinusType/blob/master/image/AI%E6%95%B0%E5%AD%97%E7%BB%98%E7%94%BB/9..png?raw=true)
**prompt:** Bustling and fashionable commercial street with transportation of the future, green plants, parks with people activate, clear sky and sunlight, volumetric light, reflections, hyperdetailed, artstation,8 k, octane render

可以看到当输入的图像本身的质量较高时输出的图像也相当不错，并且在整体构图和景别和原图接近的基础上衍生出了足够的变化。这种方式能解决两个问题：其一是没找到十分贴切的意象图，则可以用一张构图相近的效果图来尝试生成需要的意象图；其二是如果找到想用的意象图存在版权等问题，为了避免陷入侵权的麻烦可以用AI生成一张接近原图的意象图。

更进一步地，可以把前面加工原图的思路用上，如果不是特别满意原图的景别，可以在原图的基础上进行适当的颜色调整再作为输入。AI的【基本不违和】能力能帮助你把调色调得十分离谱的图像变成一眼看不出毛病的真实效果。这里我用一张水边的商业街作为例子，在对原图进行调色、涂抹增加要素、通过反相改为夜景的调整之后分别输入生成不同景别的意象图。

![](https://github.com/Boycetoon/MinusType/blob/master/image/AI%E6%95%B0%E5%AD%97%E7%BB%98%E7%94%BB/10..png?raw=true)
**prompt:** Bustling and fashionable commercial street near by river, low rise buildings in front of water,  wood and other warm modern materials,  high-rise buildings with glass rearwards， green plants, parks with people activate,  shops, clear sky and sunlight, volumetric light, reflections, hyperdetailed, artstation,8 k, octane render, 3d rendering

## 小结一下

前面讲了很多都是我自己的一些尝试，另外一些没有实现的则是合理的推测。总结一下现在AI绘画技术的特征以及我们能如何利用这些特征：
 
1. 这一代的AI生成图像相对于上一代（GAN为主的模型）来说较为突出的优势是已经可以生成【基本不违和】的图像，这是十分重要的一项能力。用扩散模型生成图像现在几十秒就能生成一张，然而如果要用渲染流程则需要花费数十倍甚至百倍的时间。基于这种能力以及现在不断提高的模型速度，现阶段AI对于环境设计来说最主要的场景还是在短时间生成大量的图像作为灵感参考或者意象使用，以几十秒一张的速度基本上半个小时就能生成上百张图片，配合其本身就相对优越的创造力（随机性），有可能为设计者带来更多的想法。
2. 更为细致的和高要求的生成也并不是说现在就做不了，前面提到了这需要对输入的控制条件有较高的要求，可能设计师学会“如何和AI对话”也需要一定的时间。但就我看来，更精细的控制也是AIGC技术向后发展特别是工业化比较重要的方向，或许不久之后就会基于现在这些表现还不错的模型调教出专门面向环境设计师的设计辅助工具。
3. 最后，尽管前两点说法相对乐观，但是不可否认的是环境设计是在三维空间中做设计，而现在这些AIGC模型则是学习的二维图像，虽然成果能够在一些工作环节中起作用，但是改变不了它无法理解空间的事实。这些工具能一定程度上改变我们的工作方式，但并不是变革发生的渊薮。

# 我们将如何走向AIAD?

虽然前面的结论是现在这些图像生成的模型并不能为环境设计相关行业带来变革性的改变，但实际上技术的发展并不仅仅在这一端，在不太被人知晓的方面已经有相当多的技术在逐步发展和成熟，我们离AIAD的变革或许并没有那么遥远。

由于我对大部分技术并没有深入的研究，这里说的仅仅是基于我对这些技术的直观理解的一些想法。

首先比较容易想到的就是扩散模型如此好用，那就可以将它从二维迁移到三维，用三维数据来训练模型。这样可以解决前面提到的一个根本性问题：如果生成的不是图片而是三维模型，那就可以用一个模型来生成多张效果图，保证都来自于一个方案。其实这个方向已经有了有了一些初步的尝试（[https://dreamfusion3d.github.io/gallery.html](https://dreamfusion3d.github.io/gallery.html)）。相信按照之前扩散模型发展的速度，出现一些可用的模型并不是遥远的事情。

第二其实反过来从环境设计专业内想，其实我们并不需要特别复杂的三维模型生成的算法，生成式设计（Generative Design）早就在相关领域被研究了多年，已经有相当多的成熟的方案，不管是基于规则的还是基于数据和算法的（GAN模型）都已经有了不少商用产品。AI绘图的技术能帮我们看到更多可能性的还是在表现上面，尽管现在的方案生成产品可能也自带一些快速表现的功能，但大都基于传统的建模-渲染流程，效率和效果都差强人意。AI绘图的特点正好能在这些方面进行弥补，首先它相比渲染足够快，其次它不仅是对原模型的渲染，还能对一些细节进行调整和优化，比如设计中的商业氛围、人群活动等本身不属于方案，但对于方案表现较为重要的部分，传统流程中都还是通过建模或后期的方式，今后AI绘图或许能在这样的场景下发挥得更好。

第三回到比较近期的考虑，前面提到现有的技术（模型）对于一些生产环节的需求其实已经基本满足，但是一方面缺少对设计师的引导和教育，传统的设计师或许还不知道如何理解和使用AI类工具。另一方面专门针对这一领域的工具现在还没有，比如国内很多基于stable diffusion的工具都通过预设风格等方式提高了易用程度，对我们而言也可以通过调整预设风格，输入更多相关的图像调整模型，设计更适合设计师日常交互的工具等方式来让眼前的这一步走得更快。但事实上单单一个行业的设计师作为用户的市场是有有限的，商业驱动下或许并没有那么多的动力来进行开发，设计师或许应该更加积极主动地进行交流探索，为未来将会到来的变革做好准备。