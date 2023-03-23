# 打造你的赛博 Coser #2 没有好电脑也想玩？Colab部署StableDiffusion保姆级教程 | AIGC周刊

URL: https://op7418.zhubai.love/posts/2239983151969951744

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/2f4e3e7bc7eb4da98874945fc04ef5fd_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/2f4e3e7bc7eb4da98874945fc04ef5fd_2076989541495611392.png)

# 写在前面

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/8c5d1307afbe4bb890671472390418cb_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/8c5d1307afbe4bb890671472390418cb_2076989541495611392.png)

这期主要介绍白嫖谷歌Colab部署StableDiffusion的过程，如果你用的mac或者PC没有好显卡可以看这个教程，如果你有性能比较好的PC，建议去看我之前写的[《打造你的赛博 Coser-StableDiffusion模型及 LoRA 插件保姆级教程》](https://op7418.zhubai.love/posts/2238998671356555264)。

上周大家可能都被[勘云工造](https://space.bilibili.com/3081011)的这一套图片刷屏了，虽然我之前一直也在关注StableDiffusion的进展，但更多还是集中在官方模型的进度上，再加上其实SD部署起来比较麻烦。由于官方大版本模型没有进行大更新所以在Noval之后就没再关注了。所以看到这套图片的我也震惊了，细节处理的非常好，同时图片分辨率非常高基本上猛的一看跟拍摄的没啥区别了。

最近补了一下课，研究了一下带来这这些变化的原因，主要是因为开源之后社区玩家的一些努力带来了很多细分领域质量很高的模型，同时还有LoRA这个功能的加入使得使用模型和训练模型的成本不断降低。

# 教程开始

一、这次用的是巴哈姆特上的一个台湾一键部署脚本，首先打开[这个链接](https://colab.research.google.com/drive/1lekLF7iib6M1R-NCylS0VMTF4wve-XuV?usp=sharing)就会看到谷歌Colab的界面了。首先需要点击图示右上角的链接（这里我已经是链接状态所以没有按钮），如果你没有登录谷歌会让你先登录。

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/b6dcc904a60247468609b8eae8db63e0_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/b6dcc904a60247468609b8eae8db63e0_2076989541495611392.png)

二、接下来我们需要依次运行下面的几个部分，首先鼠标放在第一部分那个框框上，点击图示的图标。等待它运行完毕，如果运行完毕了，这个框框会有虚线描边，启动图标左边也会出现一个绿色对号。

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/0408b4b9e1af4d37a3d62ecb322fb10c_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/0408b4b9e1af4d37a3d62ecb322fb10c_2076989541495611392.png)

三、接下来第二部分先不要点击运行我们需要先设置模型它预先设置了几个常用的模型这里我们选择ChilloutMix这个。（那有的人说我不想用预设的怎么办，那这个时候你就可以把你想用的模型的下载链接天在下面sd_url:后面的输入框里。那有人说我去哪里找下载链接呢这里以ChilloutMix举例，[https://civitai.com/](https://civitai.com/models/6424/chilloutmix) 的模型详情页图示的位置右键复制链接地址就行了。）之后我们点击运行等待加载完成（点击后会有个警告选【仍然运行】就行），可能需要等待几分钟，只要那个按钮还在转圈就没事。

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/7dd29928464342bab17878685fb980c8_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/7dd29928464342bab17878685fb980c8_2076989541495611392.png)

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/7373d2f41fdc4c2bbaa228c4321706fe_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/7373d2f41fdc4c2bbaa228c4321706fe_2076989541495611392.png)

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/1edba22b8b084559869547624e867381_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/1edba22b8b084559869547624e867381_2076989541495611392.png)

四、模型的部分运行完成后我们来设置LoRA，这个脚本默认内置了几个常见的LoRA，需要的话直接勾选就行，如果不想用它预设的话，在【lora_urls:】之后的输入框输入LoRA的下载链接就行，链接的获取方式跟上面的模型位置一样。多个下载链接的话中间用英文的逗号隔开。设置好之后我们点击这一步的运行按钮。

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/bf3625d72b154a1aa4ed5eaf6c02362c_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/bf3625d72b154a1aa4ed5eaf6c02362c_2076989541495611392.png)

五、之后的【进阶设置】和【建立环境】没什么需要设置的我们依次点击运行就可以。建立环境这一步第一次执行可能时间会比较久大概持续五分钟左右，请耐心等待。

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/d26c780ab7e344d0992ae6d6a36f06fa_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/d26c780ab7e344d0992ae6d6a36f06fa_2076989541495611392.png)

六、之后的启动Web UI这一步我们不用等待运行结束了，等到它出现图里面的链接的时候点击链接就行。之后浏览器就会打开我们熟悉的Web UI界面。需要说明的是免费的Colab部署成功后持续12小时，也就是说12小时里面你无论在任何地方访问这个链接都是可以画图的，这一点比PC好很多。

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/2fd9b7b1d9394774a54906361858d8ca_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/2fd9b7b1d9394774a54906361858d8ca_2076989541495611392.png)

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/d1fb78c1b63a4bc7aa7af5d9b6285069_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/d1fb78c1b63a4bc7aa7af5d9b6285069_2076989541495611392.png)

七、启动界面之后我们大概介绍一下基本界面要素，红色模型选择模型这里我们选择图示这个【chilloutmix_NiPrunedFp32.safetensors [95afa0d9ea]】、黄色表示提示词如果你用过midjourney等其他AI画图工具的话应该知道这个输入框的意思，它用来输入你想要生成图片的文字描述。蓝色是反向提示词用来输入一些你不想出现的内容，与midjourney不同StableDiffusion是没有色情和暴力内容的屏蔽的如果你不想图片里出现不该出现的内容的话就需要在这里描述一下。绿色的生成按钮应该都清楚了，点击之后就会在左下角的空白区域生成图片。这时候你可以试着生成一张图片了。

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/3b3e873b6d8b46bab5b059dce55e65d1_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/3b3e873b6d8b46bab5b059dce55e65d1_2076989541495611392.png)

八、接下来我们介绍一下如何使用LoRA，这个UI和之前的PC版有些不同，首先我们先点击红色框的位置，界面上会出现一个新的部分，接着我们切换到黄色的LoRA TAB，蓝色的部分就是我们可以使用的LoRA了。

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/e195f4fb7fe74d3c8ef798e2a904b0ff_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/e195f4fb7fe74d3c8ef798e2a904b0ff_2076989541495611392.png)

九、这个UI的LoRA使用也有所不同我们点击想要使用的LoRA的卡片，会发现提示词那里出现了一行字。那就是这行字被框住的数字来控制混合LoRA的权重，比如图里第一个LoRA我给了0.8的权重，第二个LoRA我给了0.6的权重。

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/415cff8322ed4743aa781255bb52c79c_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/415cff8322ed4743aa781255bb52c79c_2076989541495611392.png)

十、调整完成后你肯定要问了，我去哪里找这些提示词呢一般civitai网站模型主页下面作者的例图上都会有对应图片的关键词我们可以从那里复制改动一下就行。比如下图这个：可以看到除了提示词和反向提示词之外还有些其他参数，我会在下图按顺序标注这些参数在Web UI的位置。Seed这个不需要关注，除了Sampler、CFG scale、Steps之外，图片的宽高也需要我们注意这里建议默认使用512*768或着反过来，这样生成的速度比较快。这些内容都填写完成后，我们就可以点击右侧的【生成】按钮了。下面这里是我使用的提示词和反向提示词。

```
<lora:koreanDollLikeness_v10:0.8> <lora:japaneseDollLikeness_v10:0.6>masterpiece,best quality,official art,extremely detailed CG unity 8k wallpaper,1girl, ultra high res, (photorealistic:1.4), golden hour lighting, open white shirt, black tie, face, close up, (platinum blonde hair:1), blue eyes, short hair, looking at viewer, facing front, smiling,
```

```
paintings, sketches, (worst quality:2), (low quality:2), (normal quality:2), lowres, normal quality, ((monochrome)), ((grayscale)), skin spots, acnes, skin blemishes, age spot, glan,nsfw, lowres, bad anatomy, bad hands, text, error, missing fingers, extra digit, fewer digits, cropped, worst quality, low quality, normal quality, jpeg artifacts, signature, watermark, username, blurry, bad feet, man,
```

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/a7787703e3534d4380fe35f09df4a0b5_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/a7787703e3534d4380fe35f09df4a0b5_2076989541495611392.png)

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/6fe92db7a8da4ea39e394f3596c94fb1_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/6fe92db7a8da4ea39e394f3596c94fb1_2076989541495611392.png)

十一、这个时候想必大家的图片也已经生成了，那有的朋友可能要问了512*768这个分辨率太低了啊，基本没办法法出去，手机看全是马赛克，为什么别人的图片那么清楚。我直接提高宽高行不行。这里我们就要介绍图里的这个HIRES FIX功能了，它可以在你生成的低分辨率的图片上无损放大你的图片，而不用占那么多算力，设置的话大家可以先按我图里的设置来。

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/572f6bcfdfb14cc2a4f30c100af1bd35_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/572f6bcfdfb14cc2a4f30c100af1bd35_2076989541495611392.png)

十二、好了这就是我们生成的小姐姐了，我们的速成教程到这里就结束了。你的图像是什么样的呢，欢迎发送邮件或者在[即刻](https://okjk.co/tHKbWQ)、[推特](https://twitter.com/op7418)和我交流。

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/938e8ea2b7884620b715af25af12dedd_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser%20#2%20%E6%B2%A1%E6%9C%89%E5%A5%BD%E7%94%B5%E8%84%91%E4%B9%9F%E6%83%B3%E7%8E%A9%EF%BC%9FColab%E9%83%A8%E7%BD%B2StableDiffusion%E4%BF%9D%E5%A7%86%E7%BA%A7%20bc80493aeecd4cfa9a010540b344bc59/938e8ea2b7884620b715af25af12dedd_2076989541495611392.png)

# 最后的建议

- 图片如果忘记保存的话会保存在你的谷歌云盘里可以去云盘里面找。
- 如果觉得Colab生成的太慢可以升级成pro版本，每个月8美元还好，比电脑便宜多了。
- 关于关键词的书写这是一个长期积累的过程，每个大神都有自己的技巧，大家可以多去看大神们公开的关键字自己进行总结和思考。
- 很多人可能会遇到手部或者肢体出现一些不该出现的问题，这类问题我们可以通过【局部重绘】功能或者重新生成来解决。目前这类问题出现的比例还是比较高的，我相信会随的发展慢慢解决现在已经比之前好多了。
- StableDiffusion是开源的我们现在享受的很多便利的成果都是大神们无私贡献出来的，希望大家在有些成果后也能通过自己的方式回馈社区，保证社区的良性发展。

```
最后为了感谢王凯大佬的帮忙推广，这里介绍一下他的小报童 AI项目商业解析
主要研究可以变现的AI项目，群里也有很多大佬。
https://xiaobot.net/p/aiyanjiu?refer=a99b14af-e977-43a8-9c7b-2ca3808386b9
```

```
感谢大家看到这里，如果有觉得有意思的相关内容也可以私信我或者给我发邮件投稿。
你可以在这里找到我：即刻 |推特|竹白订阅| 微信公众号：歸藏的AI工具箱 |邮箱：guohao631@gmail.com
```