# Awesome-ChatTTS

Awesome-ChatTTS 整理和汇总了 ChatTTS 项目的常见问题和相关资源，是 ChatTTS 的最佳入门指南。

如果您觉得有用，还请打赏个 Star 支持一下。

* [快速体验](#快速体验)
* [热门分支](#热门分支)
* [参数说明](#参数说明)
* [固定音色](#固定音色)
* [安装指南](#安装指南)
* [常见问题](#常见问题)
* [报错速查](#报错速查)

## 快速体验

|                                                         网址                                                         | 亮点                       |
|:------------------------------------------------------------------------------------------------------------------:|--------------------------|
|                                    [ChatTTS Web](https://chattts.in/playground)                                    | 原版网页版体验                  |
|                                 [ChatTTS-Forge Web](https://chattts.in/playground)                                 | Forge 网页版体验              |
|                  [ChatTTS-OpenVoice Web](https://huggingface.co/spaces/Hilley/ChatTTS-OpenVoice)                   | OpenVoice 网页版体验          |
|     [Colab](https://colab.research.google.com/github/6drf21e/ChatTTS_colab/blob/main/chattts_webui_mix.ipynb)      | Colab 一键部署，需要有 Google 账号 |
|                        [Win/Mac](https://pan.baidu.com/s/1t3XddrF8KBJ2dYqmwvqOQw?pwd=nmhx)                         | Win/Mac 安装包，界面美观还能降噪     |
|                                  [Linux](https://pypi.org/project/chattts-fork/)                                   | Python 整合包，使用命令行安装和使用    |
|                                        [Samples](http://ttslist.aiqbh.com/)                                        | 提供了一些音色种子的示例，可以直接体验      |


## 热门分支

|                                      项目                                      |                                     Star                                      | 亮点                               |
|:----------------------------------------------------------------------------:|:-----------------------------------------------------------------------------:|----------------------------------|
|             [2noise/ChatTTS](https://github.com/2noise/ChatTTS)              |          ![Star](https://img.shields.io/github/stars/2noise/ChatTTS)          | 源仓库，问题较多，请参见下方解决方案               |
|    [jianchang512/ChatTTS-ui](https://github.com/jianchang512/ChatTTS-ui)     |     ![Star](https://img.shields.io/github/stars/jianchang512/ChatTTS-ui)      | 整理了详细的安装说明， 尤其是 GPU 相关问题         |
|          [6drf21e/ChatTTS_colab](https://github.com/6drf21e/ChatTTS_colab)           |      ![Star](https://img.shields.io/github/stars/6drf21e/ChatTTS_colab)       | Google Colab 一键部署，还有音色抽卡功能       |
|            [yihong0618/ChatTTS](https://github.com/yihong0618/ChatTTS)             |        ![Star](https://img.shields.io/github/stars/yihong0618/ChatTTS)        | Pypi 包一键安装，便于小白体验项目效果            |
|           [lenML/ChatTTS-Forge](https://github.com/lenML/ChatTTS-Forge)            |       ![Star](https://img.shields.io/github/stars/lenML/ChatTTS-Forge)        | 提供了 ChatTTS 封装，适合技术流深入研究         |
|         [AIFSH/ComfyUI-ChatTTS](https://github.com/AIFSH/ComfyUI-ChatTTS)          |      ![Star](https://img.shields.io/github/stars/AIFSH/ComfyUI-ChatTTS)       | ComfyUi 版本，可作为工作流节点引入            |
|               [Kedreamix/ChatTTS](https://github.com/Kedreamix/ChatTTS)                |        ![Star](https://img.shields.io/github/stars/Kedreamix/ChatTTS)         | 技术向的源代码解读，可以帮助更好的理解技术原理          |
|            [CyberWon/ChatTTS-API](https://github.com/CyberWon/ChatTTS-API)            |       ![Star](https://img.shields.io/github/stars/CyberWon/ChatTTS-API)       | 增强版 API 接口，带有流式输出能力              |
| [Jackiexiao/ChatTTS-api-ui-docker](https://github.com/Jackiexiao/ChatTTS-api-ui-docker) | ![Star](https://img.shields.io/github/stars/Jackiexiao/ChatTTS-api-ui-docker) | 提供 腾讯云 Docker 镜像，仅支持带 CUDA 的 GPU |
| [HKoon/ChatTTS-OpenVoice](https://github.com/HKoon/ChatTTS-OpenVoice) |                 ![Star](https://img.shields.io/github/stars/HKoon/ChatTTS-OpenVoice)                 | 使用 OpenVoice 进行声音克隆后生成新的语音       |
| [TommyZihao/ChatTTS_Tutorials](https://github.com/TommyZihao/ChatTTS_Tutorials) |                 ![Star](https://img.shields.io/github/stars/TommyZihao/ChatTTS_Tutorials)                 | 同济子豪兄ChatTTS手把手视频教程：基础、进阶、大模型玩法       |

---

## 视频教程

|                                                                    视频                                                                     | 亮点           |
|:-----------------------------------------------------------------------------------------------------------------------------------------:|--------------|
|                      [零度解说](https://www.bilibili.com/video/BV1wT421v7ZN/?vd_source=6773fc664ee1e277b8a2290d66ebb7a3)                      | 详细的安装和使用教程   |
|                      [ZTFS](https://www.bilibili.com/video/BV1nZ421p74z/?vd_source=6773fc664ee1e277b8a2290d66ebb7a3)                      | Mac M1 部署教程  |
| [王-寳寳](https://www.bilibili.com/video/BV1Ji421U74a/?spm_id_from=333.337.search-card.all.click&vd_source=6773fc664ee1e277b8a2290d66ebb7a3) | Windows 部署教程 |


---

## 参数说明

本项目在原版项目的基础上，增加了更多的参数，方便用户进行更细致的控制。

![配置项说明](readme/web-ui.png)

### 情感控制

* **speed** : 控制音频速度，范围为 0-9，数字越大，速度越快
* **temperate** : 控制音频情感波动性，范围为 0-1，数字越大，波动性越大
* **top_P** ：控制音频的情感相关性，范围为 0.1-0.9，数字越大，相关性越高
* **top_K** ：控制音频的情感相似性，范围为 1-20，数字越小，相似性越高

### 文本控制

* **Refine text** : 控制是否对文本进行口语化处理，取消勾选则后面三个选项无效
* **oral** : 控制文本口语化程度，范围为 0-9，数字越大，添加的“就是”、“那么”之类的连接词越多
* **laugh** : 控制文本是否添加笑声，范围为 0-9，数字越大，笑声越多
* **break** : 控制文本是否添加停顿，范围为 0-9，数字越大，停顿越多

### 种子控制

* **Audio Seed** : 配置音色种子值，不同种子对应不同音色，不同种子间差异性较大
* **Text Seed** : 配置情感种子值，不同种子对应不同情感，不同种子间差异性较小

---

## 固定音色

经过代码审查和实际测试，指定音色种子值每次生成 `spk_emb` 和重复使用预生成好的 `spk_emb` 效果有细微差异，但基本一致，因此建议直接使用相同的 `Audio Seed` 值。

在 [samples](https://github.com/libukai/ChatTTS-Control/tree/main/samples) 目录下提供了一些音色种子的示例，可以通过这些示例来选择合适的音色种子。

例如 `output2.wav` 是 `Audio Seed` 为 2 的音色种子对应的音频，`output111.wav` 是 `Audio Seed` 为 3 的音色种子对应的音频。

### 男生

| Seed | 类型 | 年龄 | 风格   |
|:----:|:--:|:--:|------|
| 111  | 男声 | 青年 | 文艺范  |
| 333  | 男声 | 青年 | 食草系  |
| 666  | 男声 | 中年 | 白领   |
| 7777 | 男声 | 中年 | 港系配音 |
| 9999 | 男声 | 中年 | 低沉深邃 |

### 女生

| Seed | 类型 | 年龄 | 风格   |
|:----:|:--:|:--:|------|
|  2   | 女声 | 青年 | 情感丰富 |
|  4   | 女声 | 中年 | 感情深邃 |
| 1111 | 女声 | 中年 | 清澈干净 |
| 3333 | 女声 | 中年 | 淡然平静 |

## 安装指南

本安装指南适用于需要运行源仓库代码的用户，小白用户建议使用 [快速体验](#快速体验) 中的方法。

1. 根据设备类型，下载 [Miniconda](https://docs.anaconda.com/free/miniconda/) 并安装
2. 在终端中下载项目代码
``` bash
https://github.com/libukai/ChatTTS-Control.git
```
3. 进入项目目录，安装基本依赖
``` bash
cd ChatTTS-Control
pip install -r requirements.txt
```
4. 安装中文依赖
``` bash
conda install -c conda-forge pynini=2.1.5 && pip install WeTextProcessing
```
5. 出现如下报错，Windows 设备需要按 [教程](https://www.cnblogs.com/ajianbeyourself/p/17654155.html) 配置环境路径
```bash
ModuleNotFoundError : No module named'Cython'
```
5. 运行 web-ui
``` bash
python webui.py

# 首次运行会下载模型，如果可以科学上网请耐心等待下载完成
# 如果无法下载，可以参考 **模型无法下载** 问题中的解决方案修改代码
# 显示以下信息，则表示运行成功：

Running on local URL:  http://0.0.0.0:8080
```
6. 打开浏览器访问 http://localhost:8080

## 常见问题

源仓库代码中的问题较多，可以根据以下清单快速解决。

### 依赖版本过低

原版项目中 `requirement.txt` 中列出的依赖版本较老，在部分环境下可能会出现报错，可以根据报错信息安装更高版本。

本项目建议使用 Python 3.10，`torch` 及相关依赖升级至 2.3.0。

```conf
omegaconf~=2.3.0
torch~=2.3.0
torchaudio==2.3.0
tqdm~=4.66.4
einops~=0.8.0
vector-quantize-pytorch~=1.14.24
transformers~=4.41.1
vocos~=0.1.0
ipython==8.25.0
huggingface-hub~=0.23.2
gradio~=4.32.2
numpy~=1.26.4
modelscope==1.15.0
```

### 模型无法下载

原版项目运行需要从 HuggingFace 下载对应的模型，如果不能顺畅科学上网，那么就无法完成这一步。作为替代方案，请从 [modelscope](https://www.modelscope.cn/models/pzc163/chatTTS/summary) 或者 [hf-mirror](https://hf-mirror.com/2Noise/ChatTTS) 上下载模型，并配置本地路径。

1. 在终端中安装 modelscope 依赖

``` bash
pip install modelscope
```

2. 修改 webui.py 中的代码

``` python
# 第 10 行添加导入依赖
from modelscope import snapshot_download

# 第 102 行添加模型下载代码
model_dir = snapshot_download('pzc163/chatTTS')

# 第 104 行修改模型路径
chat.load_models(source='local', local_path=model_dir)
```
![modelscope.png](readme/modelscope.png)

### 音频无法保存

通过脚本运行时，音频保存官方推荐使用 torchaudio，实测最新版本已经可以正常运行。如果运行有问题，也可以使用 soundfile 库进行音频保存。

 1. 官方示例中 torchaudio 代码有误，需要进行修正：

``` python
import torchaudio
#  需要将 chat.infer 生成的文件对象修正为 wavs
wavs = chat.infer(text, skip_refine_text=True, params_refine_text=params_refine_text,  params_infer_code=params_infer_code)
torchaudio.save("output2.wav", torch.from_numpy(wavs[0]), 24000)
```

2. 也可以使用 soundfile 库进行音频保存：

``` python
import soundfile

wavs = chat.infer(text, skip_refine_text=True, params_refine_text=params_refine_text,  params_infer_code=params_infer_code)
soundfile.write("output1.wav", wavs[0][0], 24000)
```

### 语气标签被读出

出现这个问题是因为官方代码处理中文标点符号时覆盖不全，例如 `？`、`…` 等符号没有被处理，导致模型生成时出错。

可以手动删除类似的中文标点符号，或者修改 `ChatTTS/utils/infer_utils.py` 中的代码，在 103 行的 `character_map` 的字典中添加缺失的标点符号。

```Python
character_map = {
    '…': '',
    '—': ',',
    '＿': ',',
    '？': ',',
    }
```

### GPU 无法使用

GPU 至少需要 4G 显存，否则将强制使用 CPU，相关问题可以参考 [ChatTTS-ui](https://github.com/jianchang512/ChatTTS-ui) 项目中的说明

## 报错速查

1、`load_models() got an unexpected keyword argument 'source'`

详见 **常见问题 - 模型无法下载**

2、`cannot import name 'CommitOperationAdd' from 'huggingface_hub'`
   
详见 **常见问题 - 模型无法下载**

3、 `FileNotFoundError：［Erzno 2］ No such file or directory： 'C：\\Users\\xxx\\.cache\\huggingface\\hub\\models--2Noise--ChatTTS\\snapshots\`

详见 **常见问题 - 模型无法下载**

4、`local variable 'Normalizer' referenced before assignment`

需要根据 **安装指南** 完成环境配置后，再安装 `pynini` 和 `WeTextProcessing` 依赖

``` bash
conda install -c conda-forge pynini=2.1.5 && pip install WeTextProcessing
```

5、`Couldn't find appropriate backend to handle uri output1.wav and format wav.`

详见 **常见问题 - 音频保存**

6、`Could not find a version that satisfies the requirement torch~=2.1.0`

详见 **常见问题 - 依赖版本**

7、`ModuleNotFoundError : No module named'Cython'`

详见 **安装指南**

---

## 代码说明

本项目代码在原版项目代码的基础上进行了一些优化和整理，主要包括以下几个方面：

1. 使用国内模型下载代码方式，减少了可能出现的模型下载失败的问题。
2. 抽离了更多参数，优化版 web-ui 中可以更加方便地进行调整。
3. 添加了遗漏的需处理的中文标点字符，修复了生成的语音中可能出现的读出控制单元的问题。
4. 增加了多音字的初步处理，主要是“得”和“地”，使生成的语音听起来更加自然流畅。
5. 增加了长文本分段功能，分段处理后自动再合并为单个音频文件，避免了过长的文本生成效果失控的问题。
6. 增加了 script.py 示例脚本，包含了常见问题中解决方案的说明 。

## 项目趋势

[![Star History Chart](https://api.star-history.com/svg?repos=libukai/Awesome-ChatTTS&type=Date)](https://star-history.com/#libukai/ChatTTS-Control&Date)
