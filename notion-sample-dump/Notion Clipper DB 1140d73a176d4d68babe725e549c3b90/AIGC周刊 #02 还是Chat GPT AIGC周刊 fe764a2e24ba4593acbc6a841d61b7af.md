# AIGC周刊 #02 还是Chat GPT | AIGC周刊

URL: https://op7418.zhubai.love/posts/2213903650001543168

![AIGC%E5%91%A8%E5%88%8A%20#02%20%E8%BF%98%E6%98%AFChat%20GPT%20AIGC%E5%91%A8%E5%88%8A%20fe764a2e24ba4593acbc6a841d61b7af/50dc7d68636c41908d1e6ae09d337f1f.png](AIGC%E5%91%A8%E5%88%8A%20#02%20%E8%BF%98%E6%98%AFChat%20GPT%20AIGC%E5%91%A8%E5%88%8A%20fe764a2e24ba4593acbc6a841d61b7af/50dc7d68636c41908d1e6ae09d337f1f.png)

题图使用Midjourney V4生成，提示词为：Neural network algorithm schematic, futuristic minimalist style, abstract, Greg Rutkowski

> 如无意外会在每周一更新，主要介绍上周AIGC领域发布的一些产品以及值得关注的研究成果，由于我自己是一个设计师，所以在一些专业内容的描述上可能存在问题，欢迎在渠道帮我反馈及更正。
> 

这周很多的主要内容还是Chat GPT上上周发布以后彻底引爆了全球互联网，仅仅五天注册用户破百万，这中间服务也被挤爆了好几次，淘宝和闲鱼买账号以及帮忙部署机器人的人也血赚了一波，还不知道如何注册的人可以[看这里](https://sms-activate.org/cn/info/ChatGPT?ref=2758859)，

随着不断的测试Chat GPT的一些缺点也暴露了出来，比如它的伦理限制会在被绕晕逻辑之后失效，以及涉及到它不懂得内容的时候也会一本正经的胡说八道，所以一些确定性的知识还是不能完全相信它。

当然这些缺点也无法掩盖它表现出来的革命性技术的特点，这一周利用其技术的相关工具软件也在爆发式增长，当然也有一些人对此不屑一顾认为其还是微软小冰那种东西。这里引用一下即刻YuanLiu对于最近关于Chat GPT一些现象的评价“一匹聪明的马应该看到蒸汽机就知道自己作为交通工具的时代要结束了，差一点的见到福特Model T也会意识到，当然也总有一些嘴壳硬的，非要看到波音747和磁悬浮列车才信。”

![AIGC%E5%91%A8%E5%88%8A%20#02%20%E8%BF%98%E6%98%AFChat%20GPT%20AIGC%E5%91%A8%E5%88%8A%20fe764a2e24ba4593acbc6a841d61b7af/5d896632915e45a39b476ad7fa17bae1.png](AIGC%E5%91%A8%E5%88%8A%20#02%20%E8%BF%98%E6%98%AFChat%20GPT%20AIGC%E5%91%A8%E5%88%8A%20fe764a2e24ba4593acbc6a841d61b7af/5d896632915e45a39b476ad7fa17bae1.png)

# 🤑行业动态

- Stable Diffusion v2.1发布
    - 解决了2.0发布时屏蔽负面内容用力过猛造成的人像生成问题
    - 支持生成非标准分辨率图像，比如32:9之类的
    - 来源：[https://github.com/Stability-AI/stablediffusion](https://github.com/Stability-AI/stablediffusion)

![AIGC%E5%91%A8%E5%88%8A%20#02%20%E8%BF%98%E6%98%AFChat%20GPT%20AIGC%E5%91%A8%E5%88%8A%20fe764a2e24ba4593acbc6a841d61b7af/a24ea60b8ebb495b8041fbf90c355548.png](AIGC%E5%91%A8%E5%88%8A%20#02%20%E8%BF%98%E6%98%AFChat%20GPT%20AIGC%E5%91%A8%E5%88%8A%20fe764a2e24ba4593acbc6a841d61b7af/a24ea60b8ebb495b8041fbf90c355548.png)

- 麦肯锡发布了他们的AI 现状报告。这里有一个简短的总结：自2017年以来，采用率增加了一倍多，尽管过去几年使用人工智能1的组织比例在50％至60％之间趋于平稳。一组从人工智能中看到最高财务回报的公司继续领先于竞争对手。结果显示，这些领导者在人工智能方面进行了更大的投资，采用了越来越先进的做法，以实现规模化和更快的人工智能发展，并显示出在紧张的人工智能人才市场上有更好的表现。在人才方面，我们首次仔细研究了人工智能的招聘和技能提升。数据显示，人工智能团队的多样性还有很大的提升空间，而且，与其他研究一致，多样化的团队与出色的业绩相关。来源：[https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai-in-2022-and-a-half-decade-in-review](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai-in-2022-and-a-half-decade-in-review)
- Tweve Labs为理解视频上下文的AI模型筹集了1200万美元。来源：[https://techcrunch.com/2022/12/05/twelve-labs-lands-12m-for-ai-that-understands-the-context-of-videos/](https://techcrunch.com/2022/12/05/twelve-labs-lands-12m-for-ai-that-understands-the-context-of-videos/)
- Runway宣布他们获得了5000万美元的融资，并发布了一个工具可以在几分钟的时间内训练自己的AI模型。来源：[https://runwayml.com/?utm_source=RunwaySocial&utm_medium=Twitter&utm_campaign=AITrainingRelease](https://runwayml.com/?utm_source=RunwaySocial&utm_medium=Twitter&utm_campaign=AITrainingRelease)
- Adobe将接受上传AI生成的图像并售卖。来源：[https://www.axios.com/2022/12/05/adobe-ai-made-stock-images](https://www.axios.com/2022/12/05/adobe-ai-made-stock-images)
- SellScale 筹集 340 万美元，用AI为销售团队赋能。来源：[https://www.sellscale.com/post/sellscale-raises-3-4-million-to-give-ai-superpowers-to-sales-teams](https://www.sellscale.com/post/sellscale-raises-3-4-million-to-give-ai-superpowers-to-sales-teams)

## ⚒️产品推荐

- Qatalog 2.0输入你的业务类型该产品会智能帮你生成为你定制的SaaS系统。来源：[https://qatalog.com/](https://qatalog.com/)
- Chat GPT问题模板的聚合站。来源：[https://showgpt.co/](https://showgpt.co/)
- 这个浏览器扩展可以扫描当前网页内容，并使用Chat GPT进行总结。来源：[https://github.com/clmnin/summarize.site](https://github.com/clmnin/summarize.site)
- 输入你的营销网站地址这个服务就可以用GPT-3生成关于你网站内容的人工智能客服。来源：[https://chatessential.eyelevel.ai/demo](https://chatessential.eyelevel.ai/demo)
- 使用AI驱动的代码审查工具。来源：[https://codeball.ai/](https://codeball.ai/)
- ChatGPT 和 GPT-3 的精选工具、演示和文档列表。 来源：[https://github.com/humanloop/awesome-chatgpt](https://github.com/humanloop/awesome-chatgpt)
- ChatGPT 现在可以在 Hugging Face 上使用。 来源：[https://huggingface.co/spaces/Xhaheen/ChatGPT_HF](https://huggingface.co/spaces/Xhaheen/ChatGPT_HF)
- 用于将 ChatGPT 历史下载为 PNG、PDF或链接的 Chrome 扩展。[https://github.com/liady/ChatGPT-pdf](https://github.com/liady/ChatGPT-pdf)
- ChatGPT Chrome 扩展。可以在任何网页的文本框中使用Chat GPT。[https://github.com/gragland/chatgpt-chrome-extension](https://github.com/gragland/chatgpt-chrome-extension)
- 非常方便的创建你专属的GPT机器人工具。来源：[https://www.toolbot.ai/](https://www.toolbot.ai/)
- 在浏览器中使用AI编写代码。来源：[https://www.codeium.com/](https://www.codeium.com/)
- ChatGPT 的桌面版APP，支持Mac/Windows/Linux。来源：[https://twitter.com/HiTw93/status/1601524689532133378](https://twitter.com/HiTw93/status/1601524689532133378)
- ChatGPT 的微信 Bot ,装完依赖后只需要填写 OpenAI 账号密码和微信扫码就可以使用。来源：[https://github.com/fuergaosi233/wechat-chatgpt](https://github.com/fuergaosi233/wechat-chatgpt)
- Zapier 的 OpenAI Integration 已正式发布。可以通过Zapier与其他很多应用程序一起使用GPT生成的内容。设置落地页，使用用户输入表单，让 Zapier OpenAI 应用程序进行处理（写电子邮件、生成食谱、博客文章、社交媒体帖子）并将它们放入 Google 表格，或在网站上展示。来源：[https://zapier.com/apps/openai/integrations](https://zapier.com/apps/openai/integrations)

## 🧑‍🎓学习资源

- huggingface推出了他们的深度学习课程第二版，感兴趣的可以学习一下。来源：[https://huggingface.co/deep-rl-course/unit0/introduction](https://huggingface.co/deep-rl-course/unit0/introduction)
- 使用NoCode工具创建您自己的 AI 支持的内容库。（Webflow、Airtable、Zapier 和 OpenAI）来源：[https://www.youtube.com/watch?v=4Q4fv3q78ps](https://www.youtube.com/watch?v=4Q4fv3q78ps)
- Stable Diffusion提示词书写教程。来源：[https://stability.ai/sdv2-prompt-book](https://stability.ai/sdv2-prompt-book)
- 如何利用Chat GPT帮助你生成完美的AI画图工具提示词。来源：[https://www.wordcelclub.com/ujjwal49.sol/how-to-generate-the-perfect-images](https://www.wordcelclub.com/ujjwal49.sol/how-to-generate-the-perfect-images)
- 这个网站完全使用Chat GPT生成的代码和内容来构建，只需要花费不到十分钟。来源：[https://twitter.com/replit/status/1599803817515548674](https://twitter.com/replit/status/1599803817515548674)
- 关于如何充分利用Chat GPT的一些提示和技巧。来源：[https://twitter.com/datachaz/status/1600135591877742592](https://twitter.com/datachaz/status/1600135591877742592)
- 为什么 ChatGPT 这么好？它“只是扩大的GPT-3”吗？解释Chat GPT原理的文章。来源：[https://twitter.com/DrJimFan/status/1600884299435167745](https://twitter.com/DrJimFan/status/1600884299435167745)

## 🔬精选文章

- 俞军老师关于Chat GPT能否替代搜索引擎的一些看法。来源：[https://m.okjike.com/originalPosts/638ffbb9bd99cdb26cfb9606?s=ewoidSI6ICI1OTUzOTllNGZkZmE0NzAwMTIzMDAxNmYiCn0=](https://m.okjike.com/originalPosts/638ffbb9bd99cdb26cfb9606?s=ewoidSI6ICI1OTUzOTllNGZkZmE0NzAwMTIzMDAxNmYiCn0=)
- 即刻阿法兔关于GPT的研究内容。《从GPT-1到GPT-4看ChatGPT的崛起》来源：[https://mp.weixin.qq.com/s/ALmmeyAzIZFNsRTXmVZ4aw](https://mp.weixin.qq.com/s/ALmmeyAzIZFNsRTXmVZ4aw)
- The Generalist 的 Mario 讨论关于**生成式对媒体制作和消费的潜在影响。**来源：[https://www.generalist.com/briefing/endless-media](https://www.generalist.com/briefing/endless-media)
- 来自 USV 的 Fred Wilson 写了一篇关于AI 和 web3 如何互惠互利 的简短博文。我可以看到，在任何图像都可以由 AI 生成的时代，也许 NFT 可以提供所有权。来源：[https://avc.com/2022/12/sign-everything/](https://avc.com/2022/12/sign-everything/)
- Hacker News的一个帖子，“我们现在处于人工智能的翻盖手机阶段”，“十年后每个人都会拥有独属于自己的AI助手”。来源：[https://news.ycombinator.com/item?id=33868515](https://news.ycombinator.com/item?id=33868515)
- 人工智能的春天来了吗？来源：[https://www.notboring.co/p/four-seasons-total-tech](https://www.notboring.co/p/four-seasons-total-tech)
- 纽约时报的一篇文章“ ChatGPT 的辉煌与怪异。来源：[https://www.nytimes.com/2022/12/05/technology/chatgpt-ai-twitter.html](https://www.nytimes.com/2022/12/05/technology/chatgpt-ai-twitter.html)
- 生成式AI模型还有哪些未解决的问题。来源：[https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai-in-2022-and-a-half-decade-in-review](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai-in-2022-and-a-half-decade-in-review)
- Modal背后的创始人写了一篇幕后观点《我一直在做的事情：Modal 》。（[Modal](https://erikbern.com/2022/12/07/what-ive-been-working-on-modal.html)可以让你在云中运行内容，而无需考虑基础架构。横向扩展、调度、容器化、使用 GPU、设置 Webhook 以及各种其他内容。）来源：[https://erikbern.com/2022/12/07/what-ive-been-working-on-modal.html](https://erikbern.com/2022/12/07/what-ive-been-working-on-modal.html)

## 🎆其他内容

本周尝试了一下使用[Midjourney绘制UI界面](https://m.okjike.com/originalPosts/63958263dc5954cdf508e362?s=ewoidSI6ICI1OTUzOTllNGZkZmE0NzAwMTIzMDAxNmYiCn0=)是否可行，由于它不认识字所以内容上肯定是没有逻辑的，但是美观度上令我惊喜，尤其是相关行业的落地页调性的把握，例如下面这张科幻风格游戏网站：

![AIGC%E5%91%A8%E5%88%8A%20#02%20%E8%BF%98%E6%98%AFChat%20GPT%20AIGC%E5%91%A8%E5%88%8A%20fe764a2e24ba4593acbc6a841d61b7af/e459955fd6e641dd92235c54109120ab.png](AIGC%E5%91%A8%E5%88%8A%20#02%20%E8%BF%98%E6%98%AFChat%20GPT%20AIGC%E5%91%A8%E5%88%8A%20fe764a2e24ba4593acbc6a841d61b7af/e459955fd6e641dd92235c54109120ab.png)

提示词：Landing page for futuristic sci-fi games, website, design, ux/ui, ux, ui, behance, dribbble --ar 3:2 --q 2 --v 4

感谢大家看到这里，如果又觉得有意思的相关内容也可以私信我或者给我发邮件投稿，你可以在这里找到我 | [即刻](https://web.okjike.com/me) | [推特](https://twitter.com/op7418) | [竹白订阅](https://op7418.zhubai.love/) | 微信公众号：柒肆壹捌UX |