# AIGC Weekly #06 | AIGC周刊

URL: https://op7418.zhubai.love/posts/2231725192567283712

![AIGC%20Weekly%20#06%20AIGC%E5%91%A8%E5%88%8A%20eb8dd85b8fff4416af658ec5fdf651e5/e72621e7031343c5ac421abcce8a50f7.png](AIGC%20Weekly%20#06%20AIGC%E5%91%A8%E5%88%8A%20eb8dd85b8fff4416af658ec5fdf651e5/e72621e7031343c5ac421abcce8a50f7.png)

提示词：painting with Floral, blue color, blue, blue overlay, Color Inspired Art, Nature, 8K, Color photorealistic, ultra detailed, wide angle shot, grain, cinematic, post-production, static scene, color cinematic production still, shot on 35mm film

> 如无意外会在每周一更新，主要介绍上周AIGC领域发布的一些产品以及值得关注的研究成果，由于我自己是一个设计师，所以在一些专业内容的描述上可能存在问题，欢迎在渠道帮我反馈及更正。（本期部分文案使用了Notion AI以及Chat GPT帮助润色和翻译）
> 

首先，我要向大家道歉，由于年底工作繁忙和春节休假周刊鸽了三周，这期间我对周刊内容做了很多反思。过去每期周刊内容太多，其中有很多文章深度不够，而许多产品只是底层技术的简单封装，没有参考和使用价值。

因此，从这期开始，周刊将专注于深度内容和有价值的产品发现，每个模块内容将精简到五个以内，除非有非常有价值的内容需要频繁发布。

# ❤️上周精选

## Midjourney进入中国

国内比较轰动的一件事就是Midjourney开通了官方的公众号，同时启动了微信机器人的内测。

- 微信机器人可以看作discord机器人的简易版本，默认使用V4模型不可切换模型，模型应该是V4早期版本，与discord目前的模型版本图像质量有些差距；
- 每个群多了一个Midjourney漫画的机器人，应该专门针对漫画做了专门的训练；
- 针对中文语言模型做了专门的训练，不像一些私炉就是加了个翻译器；
- 每次还是默认生成4张图片，由于微信没有discord那么完善的API，所以需要用户主动输入VX或者UX来挑选图片生成高清版本；
- 支持通过—ar 2:3命令来调整分辨率，不支持混音；
- 高清图像的分辨率比discord机器人要差，不清楚是微信压缩的原因还是主动调低了分辨率。

在测试了一段时间后，官方还发了一份问卷来调研现有测试用户的满意程度，除了常规功能的满意度调研外也询问了用户对于不同界面的接受程度（机器人公开群、机器人私人群、小程序、APP、桌面版本、网页版本、API），最后还重点询问了用户可以接受的服务价格是多少。从中可以看到他们的一些在国内的规划。问卷地址：[https://wj.qq.com/s2/11551322/efc5/](https://wj.qq.com/s2/11551322/efc5/)

如果还有想要获取测试资格的可以关注“Midjourney AI”公众号，回复“想象”会不定时发放测试资格。

![AIGC%20Weekly%20#06%20AIGC%E5%91%A8%E5%88%8A%20eb8dd85b8fff4416af658ec5fdf651e5/e2d2ba9302014890a3a90139e200801b.png](AIGC%20Weekly%20#06%20AIGC%E5%91%A8%E5%88%8A%20eb8dd85b8fff4416af658ec5fdf651e5/e2d2ba9302014890a3a90139e200801b.png)

## 微软押注Open AI

在大规模裁员之后，微软在23号宣布会在未来数年向Open AI注资数十亿美元，具体数额没有披露，有媒体报道称是 100 亿美元。此前有消息称，微软希望获得 OpenAI 的 49% 股份，对该公司的估值约为 290 亿美元。根据爆料，微软将获得 OpenAI 利润的四分之三，直到其收回投资，其他投资者将获得 49% 的股份，而 OpenAI 则保留剩余 2% 的股权。

微软的声明：[https://blogs.microsoft.com/blog/2023/01/23/microsoftandopenaiextendpartnership/](https://blogs.microsoft.com/blog/2023/01/23/microsoftandopenaiextendpartnership/)

关于Open AI的成长史以及CEO Sam Altman 的关系可以看财富杂志的这篇文章 ChatGPT黑幕：OpenAI创始人山姆奥特曼如何使用微软件数十亿打造全球最火技术 链接：

[https://archive.is/LqD2t](https://archive.is/LqD2t)

![AIGC%20Weekly%20#06%20AIGC%E5%91%A8%E5%88%8A%20eb8dd85b8fff4416af658ec5fdf651e5/bf7d0b92f6b5403ca973d39abd463879.png](AIGC%20Weekly%20#06%20AIGC%E5%91%A8%E5%88%8A%20eb8dd85b8fff4416af658ec5fdf651e5/bf7d0b92f6b5403ca973d39abd463879.png)

## 使用AI构建产品的5个建议

lex.page的创始人Nathan Baschez在推特上发布了使用AI技术构建产品的5个建议，这几个建议都挺实用的所以翻译了一下发在这里。

1. 抵制广泛的概括性。人工智能就像钢铁或电力一样，是一种广泛有用的基础技术，正在成为我们使用的几乎所有东西的一部分。无论你将人工智能整合到哪个行业中，现有的动态因素都比任何人工智能特定的建议更重要。
2. 人工智能技术不是任何人的堡垒，但这并不意味着不会建造堡垒。仅仅因为某些东西很难制造或需要很多技术专长，并不意味着它是可防御的。你知道还有什么东西很难制造，受益于规模经济，并需要稀有的技术专长吗？OLED电视，SSD和电池。但这些都几乎完全商品化了。那么真正的力量和耐久性来自哪里呢？来自它一直来的来源：规模经济，网络效应，对位，替换成本，品牌等等。不要理会告诉你不能因为使用人工智能而建立堡垒的人，但同时，如果你的堡垒计划是“没有人能复制我们，因为它太难建造了”，那么你可能是错的。
3. 使用 AI 的产品并不一定是“包装层”。这个术语背后的基本思想是，真正的价值来自基础模型，如 GPT-3 或 Stable Diffusion，而应用程序只是一个薄层，只能在允许用户访问模型时才有用。但是，大多数使用这些模型的产品并不是包装层。它们具有专门用于执行特定任务的用户界面，如帮助排序销售线索或总结法律文件，这些方式基础模型无法独立完成。将 AI 驱动的应用程序称为包装层就像称电烤箱和特斯拉为“电力的包装层”。当然，它们依赖电力，但显然它们提供了超出活电线提供的价值。
4. 忽略高度宣传 我们生活在一个历史时刻，在这里你可以发布一个简单的东西，成千上万的人会告诉你它是惊人的。它感觉很好，它给你的提升是真实的，但它是短暂的。把它当作它是。
5. 以 AI 为动力的应用程序大多不是关于 AI
如果你在建造所谓的“应用层”，你的大部分时间将花费在你所处行业中通常做的事情上：
    1. 与用户交流
    2. 了解你的数据
    3. 进行增长实验

对于 lex.page 的日常挑战来说，在 Twitter 和 Substack 上讨论 AI 理论相对不重要是一种有趣的感觉。
这让我想起了著名的（可能是错误归因）毕加索的名言：“当艺术评论家聚在一起时，他们谈论形式和结构以及意义。当艺术家聚在一起时，他们谈论哪里可以买到便宜的松脂。”
对于目前的目的，我会修改为：“当 AI 评论家聚在一起时，他们谈论对齐和可防御性和 AGI。当建造者聚在一起时，他们谈论哪里可以买到便宜的 GPU。”

这种情绪反映了一般性的真理：在任何事情上都要追求卓越，大部分都是靠努力工作并细致处理细节。执行是指数级的。 “大想法”只是一种种子。种子如何展开才是最重要的。

![AIGC%20Weekly%20#06%20AIGC%E5%91%A8%E5%88%8A%20eb8dd85b8fff4416af658ec5fdf651e5/fc8aa83cfacc4337aea3b2ef60ccfa44.png](AIGC%20Weekly%20#06%20AIGC%E5%91%A8%E5%88%8A%20eb8dd85b8fff4416af658ec5fdf651e5/fc8aa83cfacc4337aea3b2ef60ccfa44.png)

# ⚒️产品推荐

## Playground AI

可以通过文本描述精确修改图片的某些细节，比如将夏天变成秋天，修改人物头发颜色等。

工具应该使用了pix2pix的相关技术，原理和内容可以看这个链接：[https://www.timothybrooks.com/instruct-pix2pix/](https://www.timothybrooks.com/instruct-pix2pix/)

来源：[https://playgroundai.com/create](https://playgroundai.com/create)

![AIGC%20Weekly%20#06%20AIGC%E5%91%A8%E5%88%8A%20eb8dd85b8fff4416af658ec5fdf651e5/31e24718705d48e9938980589bc312de.png](AIGC%20Weekly%20#06%20AIGC%E5%91%A8%E5%88%8A%20eb8dd85b8fff4416af658ec5fdf651e5/31e24718705d48e9938980589bc312de.png)

## Magician

之前介绍过的Figma AI插件Magician开启了公测，插件支持文字生成图像，图像生成图像，也支持对已有文案进行润色，比较特色的功能是支持从文案生成风格一致的界面icon。需要收费才能使用，9$/月或者99$/年。有点贵了感觉。

来源：[https://magician.design/#pricing](https://magician.design/#pricing)

![AIGC%20Weekly%20#06%20AIGC%E5%91%A8%E5%88%8A%20eb8dd85b8fff4416af658ec5fdf651e5/48c98bbfba104ceabf37f83d633c9d02.png](AIGC%20Weekly%20#06%20AIGC%E5%91%A8%E5%88%8A%20eb8dd85b8fff4416af658ec5fdf651e5/48c98bbfba104ceabf37f83d633c9d02.png)

## MusicLM-从文本生成音乐

google出品，可以使用不同的音乐提示来创建不同的音频元素，可以使用音频元素来创建多种音乐作品，不同的音乐作品可以使用不同的音频元素来创建。

来源：[https://google-research.github.io/seanet/musiclm/examples/](https://google-research.github.io/seanet/musiclm/examples/)

![AIGC%20Weekly%20#06%20AIGC%E5%91%A8%E5%88%8A%20eb8dd85b8fff4416af658ec5fdf651e5/652bb66856ae414c936f80cf3fd47f42.png](AIGC%20Weekly%20#06%20AIGC%E5%91%A8%E5%88%8A%20eb8dd85b8fff4416af658ec5fdf651e5/652bb66856ae414c936f80cf3fd47f42.png)

## Supernormal

通过与谷歌会议等多个软件打通，使用 AI 创建精彩的会议记录，Supernormal 是一个 AI 平台，可帮助您将会议记录的速度提高 20 倍。上周获得了1000万美元的融资。

来源：[https://supernormal.com/](https://supernormal.com/)

![AIGC%20Weekly%20#06%20AIGC%E5%91%A8%E5%88%8A%20eb8dd85b8fff4416af658ec5fdf651e5/9ee15882156642b7a75a6c1d5daed7c0.png](AIGC%20Weekly%20#06%20AIGC%E5%91%A8%E5%88%8A%20eb8dd85b8fff4416af658ec5fdf651e5/9ee15882156642b7a75a6c1d5daed7c0.png)

## WatchNow AI

输入相关内容，这个工具会帮助你推荐10电影，不止使用人名和类别，也可以使用感觉之类的形容词，例如“积极向上的电影等”，添加到列表中的标题越多，推荐就越好。

来源：[https://www.watchnowai.com/](https://www.watchnowai.com/)

![AIGC%20Weekly%20#06%20AIGC%E5%91%A8%E5%88%8A%20eb8dd85b8fff4416af658ec5fdf651e5/795abd3f6d5d4313ac3a24b5e98a88b1.png](AIGC%20Weekly%20#06%20AIGC%E5%91%A8%E5%88%8A%20eb8dd85b8fff4416af658ec5fdf651e5/795abd3f6d5d4313ac3a24b5e98a88b1.png)

## Voice Pen AI

用AI将音频内容转化为文章，使用场景比如会议的录音，为播客生成文字稿和总结，为视频教程生成文字版文案。

来源：[https://voicepen.ai/](https://voicepen.ai/)

![AIGC%20Weekly%20#06%20AIGC%E5%91%A8%E5%88%8A%20eb8dd85b8fff4416af658ec5fdf651e5/f58dd67d26ca4257b4ec1729b859c9d0.png](AIGC%20Weekly%20#06%20AIGC%E5%91%A8%E5%88%8A%20eb8dd85b8fff4416af658ec5fdf651e5/f58dd67d26ca4257b4ec1729b859c9d0.png)

# 🧑‍🎓学习资源

## 学习如何利用工具创造一个这样的虚拟形象

同理也可以使用这种方法为自己做一个Vtuber的皮套。

来源：[https://twitter.com/yokodechef/status/1618553099177857025](https://twitter.com/yokodechef/status/1618553099177857025)

## Runway Academy教程

了解如何通过 Runway Academy，将任何视频剪辑片段变成 AI 图像的风格。

来源：[https://twitter.com/runwayml/status/1618647085687128066](https://twitter.com/runwayml/status/1618647085687128066)

## 🔬精选文章

## 什么是人工智能以及它将如何影响营销人员

本文介绍了，AIGC以及它如何对现有的广告营销产生影响，主要聚焦于内容生产方面，比如广告文案以及广告素材。

来源：[https://foundationinc.co/lab/artificial-intelligence-for-marketers/](https://foundationinc.co/lab/artificial-intelligence-for-marketers/)

## 提示驱动设计

本文介绍了一种新的设计方式提示驱动设计，提示驱动设计是软件使用 AI 驱动的命令栏作为导航或输出的主要工具的地方。我们发现它非常令人兴奋，因为它可以使应用程序更易于访问、功能更强大并且几乎可以普遍适用。

来源：[https://www.felicis.com/news/prompt-driven-design](https://www.felicis.com/news/prompt-driven-design)

## OpenAI 雇佣的肯尼亚工人每小时工资不到 2 美元

时代周刊文章，调查了Open AI如何与非洲当地公司合作将充满负面信息的AI标注工作外包给每小时公司不到2美元的肯尼亚人。

来源：[https://time.com/6247678/openai-chatgpt-kenya-workers/](https://time.com/6247678/openai-chatgpt-kenya-workers/)

## 2023 年 10 项突破性技术

AI生成图像技术被麻省理工学院评选为2023年的10项突破性技术之一。其他技术包括基因编辑、电动汽车、大众市场的军用无人机等。

来源：[https://www.technologyreview.com/2023/01/09/1064864/image-making-ai-10-breakthrough-technologies-2023/](https://www.technologyreview.com/2023/01/09/1064864/image-making-ai-10-breakthrough-technologies-2023/)

## 驾驭 AI 革命：设计师如何保持竞争力

人工智能正在改变我们的设计方式以及在设计行业取得成功所需的技能。本文将探讨人工智能对设计的影响以及设计师如何为未来做好准备。

来源：[https://uxdesign.cc/navigating-the-ai-revolution-how-designers-can-stay-competitive-7798bc664210](https://uxdesign.cc/navigating-the-ai-revolution-how-designers-can-stay-competitive-7798bc664210)

## 设计师如何从今天开始在工作中使用人工智能

人工智能文本到图像工具乍一看可能感觉“神奇”，但现在在训练数据和实施中存在许多问题，需要解决方案（和法律变更）来使其更具道德性和可行性，可用于商业工作。如果您乐于避免使用这些工具制作完整的插图，那么有很多更合乎道德、更小的方法可以将它们包含在您的产品或网页设计过程中。这里有一些你今天可以使用的，以及我可以看到未来发展的方向。

来源：[https://uxdesign.cc/ways-to-use-ai-in-product-design-today-ad70e3311e92](https://uxdesign.cc/ways-to-use-ai-in-product-design-today-ad70e3311e92)

感谢大家看到这里，如果又觉得有意思的相关内容也可以私信我或者给我发邮件投稿，你可以在这里找到我 | [即刻](https://web.okjike.com/me) | [推特](https://twitter.com/op7418) | [竹白订阅](https://op7418.zhubai.love/) | 微信公众号：柒肆壹捌UX |

本文来自

[AIGC周刊](https://op7418.zhubai.love/)

每周一更新，主要介绍上周AIGC领域发布的一些产品以及值得关注的研究成果