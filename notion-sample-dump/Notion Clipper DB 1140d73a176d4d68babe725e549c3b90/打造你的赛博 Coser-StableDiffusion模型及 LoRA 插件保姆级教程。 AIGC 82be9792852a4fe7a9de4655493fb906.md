# 打造你的赛博 Coser-StableDiffusion模型及 LoRA 插件保姆级教程。 | AIGC周刊

URL: https://op7418.zhubai.love/posts/2238998671356555264

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/47290873f01249e2a46ef02d4aa4232b_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/47290873f01249e2a46ef02d4aa4232b_2076989541495611392.png)

# 写在前面

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/ede6e2215c404a78a2aedfe01acb1209_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/ede6e2215c404a78a2aedfe01acb1209_2076989541495611392.png)

这期主要介绍PC部署StableDiffusion的过程，如果你用的稍微好一些的PC可以看这个教程，如果你用的Mac或者显卡不太行，建议去看我之前写的[《打造你的赛博 Coser #2 没有好电脑也想玩？Colab部署StableDiffusion保姆级教程》](https://op7418.zhubai.love/posts/2239983151969951744)。

上周大家可能都被[勘云工造](https://space.bilibili.com/3081011)的这一套图片刷屏了，虽然我之前一直也在关注StableDiffusion的进展，但更多还是集中在官方模型的进度上，再加上其实SD部署起来比较麻烦。由于官方大版本模型没有进行大更新所以在Noval之后就没再关注了。所以看到这套图片的我也震惊了，细节处理的非常好，同时图片分辨率非常高基本上猛的一看跟拍摄的没啥区别了。

最近补了一下课，研究了一下带来这这些变化的原因，主要是因为开源之后社区玩家的一些努力带来了很多细分领域质量很高的模型，同时还有LoRA这个功能的加入使得使用模型和训练模型的成本不断降低。

这期我会介绍一下如何快速上手SD模型，过程中会使用一些整合包之类的工具，目的就是让大家快速出图，有了成果之后才有更多学习的兴趣。如果你担心整合包会有风险的话，也可以去看官方的安装教程：[https://github.com/AUTOMATIC1111/stable-diffusion-webui#installation-and-running](https://github.com/AUTOMATIC1111/stable-diffusion-webui#installation-and-running)，我这里是在本地部署的，我的系统是Windows11显卡是RTX 4070Ti，M1 Mac和纯CPU理论上也是可以使用的，但是由于生态较小会有非常多的问题，所以这类同学推荐使用Colab云端部署，这个我会单独出一期教程。注意StableDiffusion Web UI的最低可用显存为4GB，各位可以去搜一下自己显卡的显存，比这个低的话不建议本地部署了，会用的非常痛苦。

## 教程开始

一、首先我们需要下载一个StableDiffusion的整合包，这里我使用的是B站的 秋葉aaaki 大佬制作的整合包，点这里前往[秋葉的视频下载](https://www.bilibili.com/video/BV17d4y1C73R/?spm_id_from=333.788.video.desc.click&vd_source=e99f85042059f2864f5cca20d71575f0)，评论里有下载链接（没有直接提供下载链接是因为直接搬运别人的成果不太礼貌），下载完成后直接解压就行，注意文件夹不要有中文。

（更新内容：才发现秋叶把所有下载内容都删了，可以去下载[星空的整合包](https://www.bilibili.com/video/BV16j411A7BL/?spm_id_from=333.1007.top_right_bar_window_history.content.click&vd_source=e99f85042059f2864f5cca20d71575f0)启动器也支持的，或者从这里下载[备份的秋叶整合包](https://pan.baidu.com/s/1DkWLkS3R8jWc5TCGRCcn0Q?pwd=2bn2)，同时提醒大家遵纪守法不要利用模型做违法的的事情，所有相关责任都由工具使用者承担）

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/478d718b507845cf8d09a9dedccdd19b_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/478d718b507845cf8d09a9dedccdd19b_2076989541495611392.png)

二、接下来我们还是去[秋葉的这个视频](https://www.bilibili.com/video/BV1ne4y1V7QU/?spm_id_from=333.1007.top_right_bar_window_history.content.click&vd_source=e99f85042059f2864f5cca20d71575f0)，下载Web UI的启动器，有了可视化的启动器界面之后我们更新模型安装插件就会方便很多不用面对头疼的命令行终端了。将下载完成的启动器解压缩复制到刚才的整合包文件中去，点击启动器图标就可以启动了。

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/d3ee822d95b44b67a054fa4c58d9d4d4_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/d3ee822d95b44b67a054fa4c58d9d4d4_2076989541495611392.png)

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/c0a4270860c442e788a2b46356435017_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/c0a4270860c442e788a2b46356435017_2076989541495611392.png)

三、打开启动器之后我们需要做两个工作首先点开版本管理点击一键升级更新我们的模型，接下来点开扩展管理，点击一键更新更新我们的扩展。

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/f7ee8f7147d0486b8ee3e7c185ed9977_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/f7ee8f7147d0486b8ee3e7c185ed9977_2076989541495611392.png)

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/2b26efd55f904a478fef7e817a68ca8e_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/2b26efd55f904a478fef7e817a68ca8e_2076989541495611392.png)

四、做完上面两步之后我们终于可以启动我们的StableDiffusion界面了，点击启动器左侧一键启动里的一键启动按钮等待终端信息滚动结束后，就会自动打开Web UI的界面。这个时候恭喜你你已经迈出了成功的一大步。

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/adce4c35b4e84e27be208b0faeb27ec1_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/adce4c35b4e84e27be208b0faeb27ec1_2076989541495611392.png)

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/877197a560d44c9184e62601a7005c3d_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/877197a560d44c9184e62601a7005c3d_2076989541495611392.png)

五、做完上面的一步的时候理论上你已经可以使用StableDiffusion生成图片了，这里我们介绍一下这个界面最重要的几个位置，下图红色的输入框用来输入提示词，如果你用过midjourney等其他AI画图工具的话应该知道这个输入框的意思，它用来输入你想要生成图片的文字描述。蓝色部分叫反向提示词用来输入一些你不想出现的内容，与midjourney不同StableDiffusion是没有色情和暴力内容的屏蔽的如果你不想图片里出现不该出现的内容的话就需要在这里描述一下。绿色的生成按钮应该都清楚了点击之后就会在左下角的空白区域生成图片。这时候你可以试着生成一张图片了。

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/8007971af2914e9cbe9abc0777ddc655_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/8007971af2914e9cbe9abc0777ddc655_2076989541495611392.png)

六、想必你刚才已经试着生成了一张图片了，是不是发现你生成的图片和上面大佬的图片区别非常大，这里主要的区别除了提示词之外就是底模型的不同和LoRA这个插件。首先介绍一下底模型了，StableDiffusion由于是开源的所以可以在原有模型的基础上自行训练模型的，之前我们熟知的Noval就是这一类，这次我们使用的是ChilloutMix这个模型，我们需要先去模型分享网站civitai下载对应模型。[https://civitai.com/models/6424/chilloutmix](https://civitai.com/models/6424/chilloutmix)

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/32fdc7a01a63464cbef36155e47d24e2_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/32fdc7a01a63464cbef36155e47d24e2_2076989541495611392.png)

七、下载完成后将模型文件解压放到整合包目录的models\Stable-diffusion中，之后启动我们的Web UI，在图示位置切换我们刚下载的模型。

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/cf9fded87f324caeaf59d0e0df13500f_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/cf9fded87f324caeaf59d0e0df13500f_2076989541495611392.png)

八、底模型切换完成后我们需要安装LoRA的插件，启动我们的Wbe UI切换到【扩展】tab下的【可用】一栏点击【加载自】按钮，在列表中找到，Kohya-ss Additional Networks这个插件点击右侧的【Intall】按钮，可能需要等待一会安装完成后【可用】tab下的【重启并应用用户界面】，重启之后如果看到顶层TAB上多了【Additional Networks】，就说明插件已经安装成功了。

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/e905595555034b88bf13530e1b337703_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/e905595555034b88bf13530e1b337703_2076989541495611392.png)

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/c7fe3578ba0a41488d5a3154570d3a6c_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/c7fe3578ba0a41488d5a3154570d3a6c_2076989541495611392.png)

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/788563617cd44c2c9c8dd9809126ba9b_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/788563617cd44c2c9c8dd9809126ba9b_2076989541495611392.png)

九、接下来我们就需要下载我们喜欢的LoRA文件并使用了，我们还是去civitai网站，这里我使用的是现在比较火的[Korean Doll Likeness](https://civitai.com/models/7448/korean-doll-likeness)以及[Taiwan Doll Likeness](https://civitai.com/models/7716/taiwan-doll-likeness)两个LoRA，将两个文件下载完成后，把文件移动到整合包目录里的\extensions\sd-webui-additional-networks\models\lora位置。

十、移动完成以后我们关掉Web UI重新从启动器启动，在下图图示位置就能找到你的LoRA文件了，你也可以在civitai下载你喜欢的其他LoRA。好了接下来我们就正式可以生成小姐姐图片了。

十一、与底模型不同LoRA是可以多个混合使用的，这里我下载两个LoRA就是为了避免Korean Doll Likeness生成的脸型过于单一的问题。接下来我们先点击下图的【启用】按钮，然后分别选择我们刚才下载的两个LoRA文件，右侧的混合权重那里一般建议0.6-0.8就行，你想要哪个模型的特点明确一些就把哪个调的高一些。

十二、调整完成后你肯定要问了，我去哪里找这些提示词呢一般civitai网站模型主页下面作者的例图上都会有对应图片的关键词我们可以从那里复制改动一下就行。比如下图这个：可以看到除了提示词和反向提示词之外还有些其他参数，我会在下图按顺序标注这些参数在Web UI的位置。Seed这个不需要关注，除了Sampler、CFG scale、Steps之外，图片的宽高也需要我们注意这里建议默认使用512*768或着反过来，这样生成的速度比较快。这些内容都填写完成后，我们就可以点击右侧的【生成】按钮了。

```
<koreanDollLikeness_v10:0.66>, best quality, ultra high res, (photorealistic:1.4), 1girl, sleeveless black dress, studio, bare shoulders, cute, (Kpop idol), (aegyo sal:1), (platinum blonde hair:1), ((puffy eyes)), looking at viewer, facing front, smiling, laughing
```

```
Negative prompt: paintings, sketches, (worst quality:2), (low quality:2), (normal quality:2), lowres, normal quality, ((monochrome)), ((grayscale)), skin spots, acnes, skin blemishes, age spot, glans, nsfw, nipples
```

```
Size: 512x768, Seed: 2637068123, Steps: 28, Sampler: DPM++ SDE Karras, CFG scale: 8, Model hash: a757fe8b3d, Hires steps: 20, Hires upscale: 1.75, Hires upscaler: Latent (bicubic antialiased), Denoising strength: 0.45
```

十三、这个时候想必大家的图片也已经生成了，那有的朋友可能要问了512*768这个分辨率太低了啊，基本没办法法出去，手机看全是马赛克，为什么别人的图片那么清楚。我直接提高宽高行不行。这里我们就要介绍图里的这个HIRES FIX功能了，它可以在你生成的低分辨率的图片上无损放大你的图片，而不用占那么多算力，设置的话大家可以先按我图里的设置来。

十四、好了这就是我们生成的小姐姐了，我们的速成教程到这里就结束了。你的图像是什么样的呢，欢迎发送邮件或者在[即刻](https://okjk.co/tHKbWQ)、[推特](https://twitter.com/op7418)和我交流。

![%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/d73c953c53864b8c928e9082fc604f6c_2076989541495611392.png](%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E8%B5%9B%E5%8D%9A%20Coser-StableDiffusion%E6%A8%A1%E5%9E%8B%E5%8F%8A%20LoRA%20%E6%8F%92%E4%BB%B6%E4%BF%9D%E5%A7%86%E7%BA%A7%E6%95%99%E7%A8%8B%E3%80%82%20AIGC%2082be9792852a4fe7a9de4655493fb906/d73c953c53864b8c928e9082fc604f6c_2076989541495611392.png)

## 最后的建议

- 关于关键词的书写这是一个长期积累的过程，每个大神都有自己的技巧，大家可以多去看大神们公开的关键字自己进行总结和思考。
- 有的人说如果没有我想要生成的角色或者风格的LoRA怎么办，其实Web UI是支持自己训练模型的，相关内容可以去看[秋葉的这个视频](https://www.bilibili.com/video/BV1fs4y1x7p2/?spm_id_from=333.999.0.0&vd_source=e99f85042059f2864f5cca20d71575f0)。
- 很多人可能会遇到手部或者肢体出现一些不该出现的问题，这类问题我们可以通过【局部重绘】功能或者重新生成来解决。目前这类问题出现的比例还是比较高的，我相信会随的发展慢慢解决现在已经比之前好多了。
- StableDiffusion是开源的我们现在享受的很多便利的成果都是大神们无私贡献出来的，希望大家在有些成果后也能通过自己的方式回馈社区，保证社区的良性发展。

```
感谢大家看到这里，如果有觉得有意思的相关内容也可以私信我或者给我发邮件投稿。
你可以在这里找到我：即刻 |推特|竹白订阅| 微信公众号：歸藏的AI工具箱 |邮箱：guohao631@gmail.com
```