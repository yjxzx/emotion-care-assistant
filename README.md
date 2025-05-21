# 实时识别情绪识并加以关怀

# 📆 第一阶段 · 第1周任务安排（2025年5月15日～5月18日）

## 🎯 项目名称：实时识别情绪并加以关怀系统

## 🧠 本周核心目标
- 明确系统结构与功能模块
- 初步调研 FER / DeepFace 等工具的可行性
- 撰写项目目标与技术路线草稿
- 完成项目功能图绘制与 Git 初始化

---

## ✅ 每日任务计划清单

### 🗓️ 5月15日（周四）
- [ ] 阅读并运行 FER 官方示例代码（GitHub: [justinshenk/fer](https://github.com/justinshenk/fer)）
- [ ] 尝试调用摄像头实现情绪检测测试（fer.Video()）
- [ ] 梳理 FER 支持的情绪种类，并记录识别精度及响应速度
- [ ] 记录使用中遇到的报错、环境依赖问题

---

### 🗓️ 5月16日（周五）
- [ ] 阅读 DeepFace 文档（GitHub: [serengil/deepface](https://github.com/serengil/deepface)）
- [ ] 对比 DeepFace 与 FER 的异同（精度、体积、依赖、语音支持）
- [ ] 查阅两篇与“实时情绪识别”相关的论文（建议使用 arXiv / Google Scholar）
  - 示例关键词：`real-time facial emotion recognition deep learning`
- [ ] 摘要笔记：记录论文中采用的方法、使用的数据集、适用场景

---

### 🗓️ 5月17日（周六）
- [ ] 绘制系统功能结构图（建议使用 draw.io）
  - 包括：摄像头采集 → 表情识别 → 情绪分类 → 安慰反馈（语音/音乐）→ 用户界面展示
- [ ] 将结构图导出为 `.png` 图片，保存至 `/picture/` 文件夹
- [ ] Markdown 中插入图片（用于 README.md 说明）
- [ ] 创建本地 Git 仓库（如未完成）并上传现有文档与图像资源

---

### 🗓️ 5月18日（周日）
- [ ] 撰写项目说明初稿（建议用 Word 或 Markdown）
  - 包含内容：
    - 项目背景与意义
    - 项目目标（识别 + 关怀）
    - 技术选型（FER / DeepFace / OpenCV / Flask）
    - 实现方式与系统框架图
- [ ] 项目文件夹结构初步整理（如创建 `src/`, `static/`, `templates/`, `docs/`, `picture/`）
- [ ] 更新 GitHub 仓库并推送项目初稿内容

---
好的，这是 `deepface` README 文件的中文翻译：

---

# deepface

<div align="center">

[![Downloads](https://static.pepy.tech/personalized-badge/deepface?period=total&units=international_system&left_color=grey&right_color=blue&left_text=总下载量)](https://pepy.tech/project/deepface)
[![Stars](https://img.shields.io/github/stars/serengil/deepface?color=yellow&style=flat&label=%E2%AD%90%20stars)](https://github.com/serengil/deepface/stargazers)
[![Pulls](https://img.shields.io/docker/pulls/serengil/deepface?logo=docker)](https://hub.docker.com/r/serengil/deepface)
[![License](http://img.shields.io/:license-MIT-green.svg?style=flat)](https://github.com/serengil/deepface/blob/master/LICENSE)
[![Tests](https://github.com/serengil/deepface/actions/workflows/tests.yml/badge.svg)](https://github.com/serengil/deepface/actions/workflows/tests.yml)
[![DOI](http://img.shields.io/:DOI-10.17671/gazibtd.1399077-blue.svg?style=flat)](https://doi.org/10.17671/gazibtd.1399077)

[![Blog](https://img.shields.io/:blog-sefiks.com-blue.svg?style=flat&logo=wordpress)](https://sefiks.com)
[![YouTube](https://img.shields.io/:youtube-@sefiks-red.svg?style=flat&logo=youtube)](https://www.youtube.com/@sefiks?sub_confirmation=1)
[![Twitter](https://img.shields.io/:follow-@serengil-blue.svg?style=flat&logo=x)](https://twitter.com/intent/user?screen_name=serengil)

[![Patreon](https://img.shields.io/:become-patron-f96854.svg?style=flat&logo=patreon)](https://www.patreon.com/serengil?repo=deepface)
[![GitHub Sponsors](https://img.shields.io/github/sponsors/serengil?logo=GitHub&color=lightgray)](https://github.com/sponsors/serengil)
[![Buy Me a Coffee](https://img.shields.io/badge/-buy_me_a%C2%A0coffee-gray?logo=buy-me-a-coffee)](https://buymeacoffee.com/serengil)

<div align="center">
  <a href="https://trendshift.io/repositories/4227" target="_blank"><img src="https://trendshift.io/api/badge/repositories/4227" alt="serengil%2Fdeepface | Trendshift" style="width: 250px; height: 55px;" width="250" height="55"/></a>
  <!--
  <a href="https://www.producthunt.com/posts/deepface?embed=true&utm_source=badge-featured&utm_medium=badge&utm_souce=badge-deepface" target="_blank">
      <img src="https://api.producthunt.com/widgets/embed-image/v1/featured.svg?post_id=753599&theme=light" alt="DeepFace - A Lightweight Deep Face Recognition Library for Python | Product Hunt" style="width: 250px; height: 54px;" width="250" height="54" />
  </a>
  -->
</div>

<!--
[![Hacker News](https://img.shields.io/badge/dynamic/json?color=orange&label=Hacker%20News&query=score&url=https%3A%2F%2Fhacker-news.firebaseio.com%2Fv0%2Fitem%2F42584896.json&logo=y-combinator)](https://news.ycombinator.com/item?id=42584896)
[![Product Hunt](https://img.shields.io/badge/Product%20Hunt-%E2%96%B2-orange?logo=producthunt)](https://www.producthunt.com/posts/deepface?embed=true&utm_source=badge-featured&utm_medium=badge&utm_souce=badge-deepface)
-->

<!-- [![DOI](http://img.shields.io/:DOI-10.1109/ICEET53442.2021.9659697-blue.svg?style=flat)](https://doi.org/10.1109/ICEET53442.2021.9659697) -->
<!-- [![DOI](http://img.shields.io/:DOI-10.1109/ASYU50717.2020.9259802-blue.svg?style=flat)](https://doi.org/10.1109/ASYU50717.2020.9259802) -->

</div>

<p align="center"><img src="https://raw.githubusercontent.com/serengil/deepface/master/icon/deepface-icon-labeled.png" width="200" height="240"></p>

DeepFace 是一个轻量级的 Python [人脸识别](https://sefiks.com/2018/08/06/deep-face-recognition-with-keras/)和面部属性分析（[年龄](https://sefiks.com/2019/02/13/apparent-age-and-gender-prediction-in-keras/)、[性别](https://sefiks.com/2019/02/13/apparent-age-and-gender-prediction-in-keras/)、[情绪](https://sefiks.com/2018/01/01/facial-expression-recognition-with-keras/)和[种族](https://sefiks.com/2019/11/11/race-and-ethnicity-prediction-in-keras/)）框架。它是一个混合人脸识别框架，封装了**当前最先进的**模型：[`VGG-Face`](https://sefiks.com/2018/08/06/deep-face-recognition-with-keras/)、[`FaceNet`](https://sefiks.com/2018/09/03/face-recognition-with-facenet-in-keras/)、[`OpenFace`](https://sefiks.com/2019/07/21/face-recognition-with-openface-in-keras/)、[`DeepFace`](https://sefiks.com/2020/02/17/face-recognition-with-facebook-deepface-in-keras/)、[`DeepID`](https://sefiks.com/2020/06/16/face-recognition-with-deepid-in-keras/)、[`ArcFace`](https://sefiks.com/2020/12/14/deep-face-recognition-with-arcface-in-keras-and-python/)、[`Dlib`](https://sefiks.com/2020/07/11/face-recognition-with-dlib-in-python/)、`SFace`、`GhostFaceNet`、`Buffalo_L`。

[`实验`](https://github.com/serengil/deepface/tree/master/benchmarks)表明，**人类在人脸识别任务上的准确率为 97.53%**，而这些模型已经达到并超过了这个准确率水平。

## 安装 [![PyPI](https://img.shields.io/pypi/v/deepface.svg)](https://pypi.org/project/deepface/)

安装 deepface 最简单的方法是从 [`PyPI`](https://pypi.org/project/deepface/) 下载。它会自动安装库本身及其依赖项。

```shell
$ pip install deepface
```

或者，您也可以从源代码安装 deepface。源代码可能包含尚未在 pip 版本中发布的新功能。

```shell
$ git clone https://github.com/serengil/deepface.git
$ cd deepface
$ pip install -e .
```

安装库后，您就可以导入并使用其功能了。

```python
from deepface import DeepFace
```

**现代化的人脸识别流程** - [`演示视频`](https://youtu.be/WnUVYQP4h44)

现代化的[**人脸识别流程**](https://sefiks.com/2020/05/01/a-gentle-introduction-to-face-recognition-in-deep-learning/)包含 5 个常见阶段：[检测](https://sefiks.com/2020/08/25/deep-face-detection-with-opencv-in-python/)、[对齐](https://sefiks.com/2020/02/23/face-alignment-for-face-recognition-in-python-within-opencv/)、[归一化](https://sefiks.com/2020/11/20/facial-landmarks-for-face-recognition-with-dlib/)、[表示](https://sefiks.com/2018/08/06/deep-face-recognition-with-keras/)和[验证](https://sefiks.com/2020/05/22/fine-tuning-the-threshold-in-face-recognition/)。DeepFace 在后台处理所有这些常见阶段，您无需深入了解其背后的所有过程。您只需一行代码即可调用其验证、查找或分析函数。

**人脸验证** - [`演示视频`](https://youtu.be/KRCvkNCOphE)

此函数验证人脸对是否为同一个人。它期望输入精确的图像路径。也支持传递 numpy 数组或 base64 编码的图像。然后，它将返回一个字典，您只需检查其 `verified` 键即可。

```python
result = DeepFace.verify(img1_path = "img1.jpg", img2_path = "img2.jpg")
```

<p align="center"><img src="https://raw.githubusercontent.com/serengil/deepface/master/icon/stock-1.jpg" width="95%" height="95%"></p>

**人脸识别** - [`演示视频`](https://youtu.be/Hrjp-EStM_s)

[人脸识别](https://sefiks.com/2020/05/25/large-scale-face-recognition-for-deep-learning/)需要多次应用人脸验证。为此，deepface 提供了一个开箱即用的 `find` 函数来处理此操作。它将在数据库路径中查找输入图像的身份，并返回 pandas DataFrame 列表作为输出。同时，面部数据库的面部嵌入向量存储在 pickle 文件中，以便下次更快地搜索。结果的大小将是源图像中出现的人脸数量。此外，数据库中的目标图像也可以包含多个人脸。

```python
dfs = DeepFace.find(img_path = "img1.jpg", db_path = "C:/my_db")
```

<p align="center"><img src="https://raw.githubusercontent.com/serengil/deepface/master/icon/stock-6-v2.jpg" width="95%" height="95%"></p>

**面部属性分析** - [`演示视频`](https://youtu.be/GT2UeN85BdA)

DeepFace 还带有一个强大的面部属性分析模块，包括[`年龄`](https://sefiks.com/2019/02/13/apparent-age-and-gender-prediction-in-keras/)、[`性别`](https://sefiks.com/2019/02/13/apparent-age-and-gender-prediction-in-keras/)、[`面部表情`](https://sefiks.com/2018/01/01/facial-expression-recognition-with-keras/)（包括生气、恐惧、中性、悲伤、厌恶、高兴和惊讶）和[`种族`](https://sefiks.com/2019/11/11/race-and-ethnicity-prediction-in-keras/)（包括亚洲人、白人、中东人、印度人、拉丁美洲人和黑人）的预测。结果的大小将是源图像中出现的人脸数量。

```python
objs = DeepFace.analyze(
  img_path = "img4.jpg", actions = ['age', 'gender', 'race', 'emotion']
)
```

<p align="center"><img src="https://raw.githubusercontent.com/serengil/deepface/master/icon/stock-2.jpg" width="95%" height="95%"></p>

年龄模型的平均绝对误差（MAE）为 ± 4.65；性别模型的准确率为 97.44%，精确率为 96.29%，召回率为 95.05%，如其[教程](https://sefiks.com/2019/02/13/apparent-age-and-gender-prediction-in-keras/)所述。

**实时分析** - [`演示视频`](https://youtu.be/-c9sSJcx6wI), [`React 演示第一部分`](https://youtu.be/IXoah6rhxac), [`React 演示第二部分`](https://youtu.be/_waBA-cH2D4)

您也可以对实时视频运行 deepface。`stream` 函数将访问您的网络摄像头并同时应用人脸识别和面部属性分析。如果函数能连续 5 帧聚焦到一张脸，它就会开始分析该帧。然后，它会显示结果 5 秒钟。

```python
DeepFace.stream(db_path = "C:/database")
```

<p align="center"><img src="https://raw.githubusercontent.com/serengil/deepface/master/icon/stock-3.jpg" width="90%" height="90%"></p>

即使人脸识别是基于单样本学习（one-shot learning），您也可以使用一个人的多张面部图片。您应该如下图所示重新组织您的目录结构。

```bash
user
├── database
│   ├── Alice
│   │   ├── Alice1.jpg
│   │   ├── Alice2.jpg
│   ├── Bob
│   │   ├── Bob.jpg
```

如果您打算直接从浏览器执行人脸验证或分析任务，[`deepface-react-ui`](https://github.com/serengil/deepface-react-ui) 是一个使用 ReactJS 构建的独立仓库，依赖于 deepface API。

在这里，您还可以找到各种人脸识别模型的实时演示：

<p align="center"><img src="https://sefiks.com/wp-content/uploads/2020/02/deepface-cover.jpg" width="90%" height="90%"></p>

| 任务                 | 模型     | 演示视频                                  |
| ---                  | ---      | ---                                     |
| 人脸识别             | DeepFace | [`视频`](https://youtu.be/YjYIMs5ZOfc) |
| 人脸识别             | FaceNet  | [`视频`](https://youtu.be/vB1I5vWgTQg) |
| 人脸识别             | VGG-Face | [`视频`](https://youtu.be/tSU_lNi0gQQ) |
| 人脸识别             | OpenFace | [`视频`](https://youtu.be/-4z2sL6wzP8) |
| 年龄和性别           | -        | [`视频`](https://youtu.be/tFI7vZn3P7E) |
| 种族和民族           | -        | [`视频`](https://youtu.be/-ztiy5eJha8) |
| 情绪                 | -        | [`视频`](https://youtu.be/Y7DfLvLKScs) |
| 明星脸查找           | -        | [`视频`](https://youtu.be/RMgIKU1H8DY) |

**嵌入向量 (Embeddings)** - [`演示视频`](https://youtu.be/OYialFo7Qo4)

人脸识别模型基本上将面部图像表示为多维向量。有时，您需要直接获取这些嵌入向量。DeepFace 提供了一个专用的 `represent` 函数。`represent` 函数返回一个嵌入向量列表。结果的大小将是图像路径中出现的人脸数量。

```python
embedding_objs = DeepFace.represent(img_path = "img.jpg")
```

嵌入向量可以如下[绘制](https://sefiks.com/2020/05/01/a-gentle-introduction-to-face-recognition-in-deep-learning/)。每个槽对应一个维度值，维度值用颜色强调。与二维码类似，插图中的垂直维度不存储信息。

<p align="center"><img src="https://raw.githubusercontent.com/serengil/deepface/master/icon/embedding.jpg" width="95%" height="95%"></p>

**人脸识别模型** - [`演示视频`](https://youtu.be/eKOZawGR3y0)

DeepFace 是一个**混合**人脸识别包。它目前封装了许多**当前最先进的**人脸识别模型：[`VGG-Face`](https://sefiks.com/2018/08/06/deep-face-recognition-with-keras/)、[`FaceNet`](https://sefiks.com/2018/09/03/face-recognition-with-facenet-in-keras/)、[`OpenFace`](https://sefiks.com/2019/07/21/face-recognition-with-openface-in-keras/)、[`DeepFace`](https://sefiks.com/2020/02/17/face-recognition-with-facebook-deepface-in-keras/)、[`DeepID`](https://sefiks.com/2020/06/16/face-recognition-with-deepid-in-keras/)、[`ArcFace`](https://sefiks.com/2020/12/14/deep-face-recognition-with-arcface-in-keras-and-python/)、[`Dlib`](https://sefiks.com/2020/07/11/face-recognition-with-dlib-in-python/)、`SFace`、`GhostFaceNet` 和 `Buffalo_L`。默认配置使用 VGG-Face 模型。

```python
models = [
    "VGG-Face", "Facenet", "Facenet512", "OpenFace", "DeepFace",
    "DeepID", "ArcFace", "Dlib", "SFace", "GhostFaceNet",
    "Buffalo_L",
]

result = DeepFace.verify(
  img1_path = "img1.jpg", img2_path = "img2.jpg", model_name = models[0]
)

dfs = DeepFace.find(
  img_path = "img1.jpg", db_path = "C:/my_db", model_name = models[1]
)

embeddings = DeepFace.represent(
  img_path = "img.jpg", model_name = models[2]
)
```

<p align="center"><img src="https://raw.githubusercontent.com/serengil/deepface/master/icon/model-portfolio-20240316.jpg" width="95%" height="95%"></p>

根据实验，FaceNet、VGG-Face、ArcFace 和 Dlib 表现更优 - 更多详情请参见 [`BENCHMARKS`](https://github.com/serengil/deepface/tree/master/benchmarks)。下表列出了 DeepFace 中各种模型的实测分数以及它们原始研究中报告的分数。

| 模型           | 实测分数 | 声明分数     |
| -------------- | -------- | ------------------ |
| Facenet512     | 98.4%    | 99.6%              |
| 人类           | 97.5%    | 97.5%              |
| Facenet        | 97.4%    | 99.2%              |
| Dlib           | 96.8%    | 99.3 %             |
| VGG-Face       | 96.7%    | 98.9%              |
| ArcFace        | 96.7%    | 99.5%              |
| GhostFaceNet   | 93.3%    | 99.7%              |
| SFace          | 93.0%    | 99.5%              |
| OpenFace       | 78.7%    | 92.9%              |
| DeepFace       | 69.0%    | 97.3%              |
| DeepID         | 66.5%    | 97.4%              |

在 DeepFace 中使用这些模型进行实验可能会与原始研究有所差异，这是因为采用了不同的检测或归一化技术。此外，有些模型仅发布了其骨干网络，没有预训练权重。因此，我们使用的是它们的重新实现，而不是原始的预训练权重。

**人脸检测和对齐** - [`演示视频`](https://youtu.be/GZ2p2hj2H5k)

人脸检测和对齐是现代人脸识别流程中重要的早期阶段。[实验](https://github.com/serengil/deepface/tree/master/benchmarks)表明，检测可以将人脸识别准确率提高多达 42%，而对齐可以将其提高多达 6%。Deepface 中封装了 [`OpenCV`](https://sefiks.com/2020/02/23/face-alignment-for-face-recognition-in-python-within-opencv/)、[`Ssd`](https://sefiks.com/2020/08/25/deep-face-detection-with-opencv-in-python/)、[`Dlib`](https://sefiks.com/2020/07/11/face-recognition-with-dlib-in-python/)、[`MtCnn`](https://sefiks.com/2020/09/09/deep-face-detection-with-mtcnn-in-python/)、`Faster MtCnn`、[`RetinaFace`](https://sefiks.com/2021/04/27/deep-face-detection-with-retinaface-in-python/)、[`MediaPipe`](https://sefiks.com/2022/01/14/deep-face-detection-with-mediapipe/)、`Yolo`、`YuNet` 和 `CenterFace` 检测器。

<p align="center"><img src="https://raw.githubusercontent.com/serengil/deepface/master/icon/detector-portfolio-v6.jpg" width="95%" height="95%"></p>

所有 deepface 函数都接受可选的 `detector_backend` 和 `align` 输入参数。您可以使用这些参数在这些检测器和对齐模式之间切换。OpenCV 是默认的检测器，默认情况下对齐是开启的。

```python
backends = [
    'opencv', 'ssd', 'dlib', 'mtcnn', 'fastmtcnn',
    'retinaface', 'mediapipe', 'yolov8', 'yolov11s',
    'yolov11n', 'yolov11m', 'yunet', 'centerface',
]
detector = backends[3]
align = True

obj = DeepFace.verify(
  img1_path = "img1.jpg", img2_path = "img2.jpg", detector_backend = detector, align = align
)

dfs = DeepFace.find(
  img_path = "img.jpg", db_path = "my_db", detector_backend = detector, align = align
)

embedding_objs = DeepFace.represent(
  img_path = "img.jpg", detector_backend = detector, align = align
)

demographies = DeepFace.analyze(
  img_path = "img4.jpg", detector_backend = detector, align = align
)

face_objs = DeepFace.extract_faces(
  img_path = "img.jpg", detector_backend = detector, align = align
)
```

人脸识别模型实际上是 CNN 模型，它们期望标准尺寸的输入。因此，在表示之前需要进行大小调整。为避免变形，deepface 在检测和对齐后根据目标尺寸参数添加黑色填充像素。

<p align="center"><img src="https://raw.githubusercontent.com/serengil/deepface/master/icon/detector-outputs-20240414.jpg" width="90%" height="90%"></p>

[RetinaFace](https://sefiks.com/2021/04/27/deep-face-detection-with-retinaface-in-python/) 和 [MtCnn](https://sefiks.com/2020/09/09/deep-face-detection-with-mtcnn-in-python/) 似乎在检测和对齐阶段表现更优，但它们的速度要慢得多。如果您的流程速度更重要，那么您应该使用 opencv 或 ssd。另一方面，如果您考虑准确性，那么您应该使用 retinaface 或 mtcnn。

RetinaFace 的性能即使在人群中也非常令人满意，如下图所示。此外，它还具有令人难以置信的面部关键点检测性能。高亮的红点显示了一些面部关键点，如眼睛、鼻子和嘴巴。这就是为什么 RetinaFace 的对齐分数也很高。

<p align="center"><img src="https://raw.githubusercontent.com/serengil/deepface/master/icon/retinaface-results.jpeg" width="90%" height="90%">
<br><em>黄色天使 - 费内巴切女子排球队</em>
</p>

您可以在此 [仓库](https://github.com/serengil/retinaface) 中找到有关 RetinaFace 的更多信息。

**人脸防伪 (Face Anti Spoofing)** - [`演示视频`](https://youtu.be/UiK1aIjOBlQ)

DeepFace 还包含一个防伪分析模块，用于判断给定图像是真实的还是伪造的。要激活此功能，请在任何 DeepFace 任务中将 `anti_spoofing` 参数设置为 True。

<p align="center"><img src="https://raw.githubusercontent.com/serengil/deepface/master/icon/face-anti-spoofing.jpg" width="40%" height="40%"></p>

```python
# 人脸检测中的防伪测试
face_objs = DeepFace.extract_faces(img_path="dataset/img1.jpg", anti_spoofing = True)
assert all(face_obj["is_real"] is True for face_obj in face_objs)

# 实时分析中的防伪测试
DeepFace.stream(db_path = "C:/database", anti_spoofing = True)
```

**相似度** - [`演示视频`](https://youtu.be/1EPoS69fHOc)

人脸识别模型是常规的[卷积神经网络](https://sefiks.com/2018/03/23/convolutional-autoencoder-clustering-images-with-neural-networks/)，它们负责将人脸表示为向量。我们期望同一个人的两张人脸应该比不同人的两张人脸[更相似](https://sefiks.com/2020/05/22/fine-tuning-the-threshold-in-face-recognition/)。

相似度可以通过不同的度量标准计算，例如[余弦相似度](https://sefiks.com/2018/08/13/cosine-similarity-in-machine-learning/)、角距离、欧几里得距离或 L2 归一化欧几里得距离。默认配置使用余弦相似度。根据[实验](https://github.com/serengil/deepface/tree/master/benchmarks)，没有哪种距离度量标准明显优于其他度量标准。

```python
metrics = ["cosine", "euclidean", "euclidean_l2", "angular"]

result = DeepFace.verify(
  img1_path = "img1.jpg", img2_path = "img2.jpg", distance_metric = metrics[1]
)

dfs = DeepFace.find(
  img_path = "img1.jpg", db_path = "C:/my_db", distance_metric = metrics[2]
)
```

**API** - [`演示视频`](https://youtu.be/HeKCQ6U9XmI), [`Docker 演示视频`](https://youtu.be/9Tk9lRQareA)

DeepFace 也提供 API 服务 - 更多详情请参见 [`api 文件夹`](https://github.com/serengil/deepface/tree/master/deepface/api/src)。您可以克隆 deepface 源代码并使用以下命令运行 API。它将使用 gunicorn 服务器启动一个 rest 服务。这样，您就可以从外部系统（如移动应用程序或 Web）调用 deepface。

```shell
cd scripts

# 直接运行服务
./service.sh

# 通过 docker 运行服务
./dockerize.sh
```

<p align="center"><img src="https://raw.githubusercontent.com/serengil/deepface/master/icon/deepface-api.jpg" width="90%" height="90%"></p>

API 涵盖了人脸识别、面部属性分析和向量表示功能。您需要以 http post 方法调用这些函数。默认的服务端点将是人脸识别的 `http://localhost:5005/verify`，面部属性分析的 `http://localhost:5005/analyze`，以及向量表示的 `http://localhost:5005/represent`。API 接受图像作为文件上传（通过表单数据），或作为精确的图像路径、URL 或 base64 编码的字符串（通过 JSON 或表单数据），为不同的客户端需求提供了灵活的选项。[这里](https://github.com/serengil/deepface/tree/master/deepface/api/postman)有一个 Postman 项目，可以帮助您了解如何调用这些方法。

**大规模人脸识别** - [`播放列表`](https://www.youtube.com/playlist?list=PLsS_1RYmYQQGSJu_Z3OVhXhGmZ86_zuIm)

如果您的任务需要在大型数据集上进行人脸识别，您应该将 DeepFace 与向量索引或向量数据库结合使用。这种设置将执行[近似最近邻](https://youtu.be/c10w0Ptn_CU)搜索而不是精确搜索，使您能够在包含数十亿条目的数据库中毫秒级识别一张脸。常见的向量索引解决方案包括 [Annoy](https://youtu.be/Jpxm914o2xk)、[Faiss](https://youtu.be/6AmEvDTKT-k)、[Voyager](https://youtu.be/2ZYTV9HlFdU)、[NMSLIB](https://youtu.be/EVBhO8rbKbg)、[ElasticSearch](https://youtu.be/i4GvuOmzKzo)。对于向量数据库，流行的选项有 [Postgres 及其 pgvector 扩展](https://youtu.be/Xfv4hCWvkp0)和 [RediSearch](https://youtu.be/yrXlS0d6t4w)。

<p align="center"><img src="https://raw.githubusercontent.com/serengil/deepface/master/icon/deepface-big-data.jpg" width="90%" height="90%"></p>

相反，如果您的任务涉及在中小型数据库上进行人脸识别，您可以采用关系数据库，如 [Postgres](https://youtu.be/f41sLxn1c0k) 或 [SQLite](https://youtu.be/_1ShBeWToPg)，或 NoSQL 数据库，如 [Mongo](https://youtu.be/dmprgum9Xu8)、[Redis](https://youtu.be/X7DSpUMVTsw) 或 [Cassandra](https://youtu.be/J_yXpc3Y8Ec) 来执行精确的最近邻搜索。

**加密嵌入向量** - [`PHE 演示`](https://youtu.be/8VCu39jFZ7k), [`PHE 教程`](https://sefiks.com/2025/03/04/vector-similarity-search-with-partially-homomorphic-encryption-in-python/), [`FHE 演示`](https://youtu.be/njjw0PEhH00), [`FHE 教程`](https://sefiks.com/2021/12/01/homomorphic-facial-recognition-with-tenseal/)

尽管向量嵌入向量无法逆向还原为原始图像，但它们仍然包含类似指纹的敏感信息，因此其安全性至关重要。加密嵌入向量对于更高安全性的应用至关重要，以防止可能操纵或提取敏感信息的对抗性攻击。传统的加密方法（如 AES）非常安全，但在安全利用云计算能力进行距离计算方面存在局限性。在此，[同态加密](https://youtu.be/3ejI0zNPMEQ)允许在没有私钥的情况下对加密数据进行计算，为云端计算提供了一个强大的替代方案。

```python
from lightphe import LightPHE

# 在本地构建一个加法同态密码系统 (例如 Paillier)
cs = LightPHE(algorithm_name = "Paillier", precision = 19)

# 定义源和目标的明文向量
alpha = DeepFace.represent("img1.jpg")[0]["embedding"]
beta = DeepFace.represent("target.jpg")[0]["embedding"]

# 在本地加密源嵌入向量 - 不需要私钥
encrypted_alpha = cs.encrypt(alpha)

# 在云端计算加密嵌入向量和明文嵌入向量的点积 - 不需要私钥
encrypted_cosine_similarity = encrypted_alpha @ beta

# 在本地解密相似度 - 需要私钥
calculated_similarity = cs.decrypt(encrypted_cosine_similarity)[0]

# 验证
print("same person" if calculated_similarity >= 1 - threshold else "different persons")
```

<p align="center"><img src="https://raw.githubusercontent.com/serengil/deepface/refs/heads/master/icon/encrypt-embeddings.jpg" width="60%" height="60%"></p>

在这个方案中，我们利用云的计算能力来计算加密的余弦相似度。然而，云端并不知道它实际执行的计算。这就是同态加密的**魔力**！只有本地持有私钥的一方才能解密加密的余弦相似度，并确定这对图像是否代表同一个人或不同的人。查看 [`LightPHE`](https://github.com/serengil/LightPHE) 库以了解更多关于部分同态加密的信息。

作为部分同态加密的替代方案，您也可以选择使用全同态加密。在这种情况下，您将计算加密嵌入向量之间的点积，而不是加密嵌入向量和明文嵌入向量之间的点积。要了解更多关于全同态加密的信息，请查看 [`CipherFace`](https://github.com/serengil/cipherface) 库。但是，请记住，FHE 的计算成本远高于 PHE。

### 扩展应用

DeepFace 也可以用于有趣且富有洞察力的应用，例如：

**找到与你相像的明星** - [`演示视频`](https://youtu.be/jaxkEn-Kieo), [`实时演示`](https://youtu.be/RMgIKU1H8DY), [`教程`](https://sefiks.com/2019/05/05/celebrity-look-alike-face-recognition-with-deep-learning-in-keras/)

DeepFace 可以分析您的面部特征，并将其与名人进行匹配，让您发现自己最像哪位名人。

<p align="center"><img src="https://raw.githubusercontent.com/serengil/deepface/master/icon/celebrity-look-alike.jpg" width="55%" height="55%"></p>

**判断孩子更像父母中的哪一方** - [`演示视频`](https://youtu.be/nza4tmi9vhE), [`教程`](https://sefiks.com/2022/12/22/decide-whom-your-child-looks-like-with-facial-recognition-mommy-or-daddy/)

DeepFace 也可以用来比较孩子的脸与父母或亲戚的脸，以确定孩子更像谁。

<p align="center"><img src="https://raw.githubusercontent.com/serengil/deepface/master/icon/parental-look-alike-scaled.jpg" width="90%" height="90%"></p>

## 贡献

非常欢迎提交 Pull Request！如果您计划贡献一个较大的补丁，请先创建一个 issue，以便首先解决任何前期问题或设计决策。

在创建 PR 之前，您应该通过运行 `make test && make lint` 命令在本地运行单元测试和代码风格检查。一旦发送 PR，GitHub 测试工作流将自动运行，单元测试和代码风格检查作业将在批准前在 [GitHub actions](https://github.com/serengil/deepface/actions) 中可用。

## 支持

支持项目的方式有很多 - 给 GitHub 仓库点亮⭐️只是其中之一 🙏

如果您确实喜欢这项工作，那么您可以在 [Patreon](https://www.patreon.com/serengil?repo=deepface)、[GitHub Sponsors](https://github.com/sponsors/serengil) 或 [Buy Me a Coffee](https://buymeacoffee.com/serengil) 上提供财务支持。此外，如果您成为金牌、银牌或铜牌赞助商，贵公司的徽标将显示在 GitHub 的 README 文件中。

<a href="https://www.patreon.com/serengil?repo=deepface">
<img src="https://raw.githubusercontent.com/serengil/deepface/master/icon/patreon.png" width="30%" height="30%">
</a>

<!--
<a href="https://github.com/sponsors/serengil">
<img src="https://raw.githubusercontent.com/serengil/deepface/refs/heads/master/icon/github_sponsor_button.png" width="37%" height="37%">
</a>

<a href="https://buymeacoffee.com/serengil">
<img src="https://raw.githubusercontent.com/serengil/deepface/master/icon/bmc-button.png" width="25%" height="25%">
</a>
-->

<!--
此外，您可以通过在 Hacker News 和 Product Hunt 上为我们的帖子投票来帮助我们接触更广泛的受众。

<div style="display: flex; align-items: center; gap: 10px;">
  <a href="https://news.ycombinator.com/item?id=42584896">
    <img src="https://hackerbadge.vercel.app/api?id=42584896&type=orange" style="width: 250px; height: 54px;" width="250" alt="Featured on Hacker News">
  </a>

  <a href="https://www.producthunt.com/posts/deepface?embed=true&utm_source=badge-featured&utm_medium=badge&utm_souce=badge-deepface" target="_blank">
    <img src="https://api.producthunt.com/widgets/embed-image/v1/featured.svg?post_id=753599&theme=light" alt="DeepFace - A Lightweight Deep Face Recognition Library for Python | Product Hunt" style="width: 250px; height: 54px;" width="250" height="54" />
  </a>
</div>
-->

## 引用

如果 deepface 对您的研究有所帮助，请在您的出版物中引用它。

<details open>
  <summary>S. Serengil and A. Ozpinar, <b>"A Benchmark of Facial Recognition Pipelines and Co-Usability Performances of Modules"</b>, <i>Journal of Information Technologies</i>, vol. 17, no. 2, pp. 95-107, 2024.</summary>

  ```BibTeX
  @article{serengil2024lightface,
    title     = {A Benchmark of Facial Recognition Pipelines and Co-Usability Performances of Modules},
    author    = {Serengil, Sefik and Ozpinar, Alper},
    journal   = {Journal of Information Technologies},
    volume    = {17},
    number    = {2},
    pages     = {95-107},
    year      = {2024},
    doi       = {10.17671/gazibtd.1399077},
    url       = {https://dergipark.org.tr/en/pub/gazibtd/issue/84331/1399077},
    publisher = {Gazi University}
  }
  ```
</details>

<details>
  <summary>S. I. Serengil and A. Ozpinar, <b>"LightFace: A Hybrid Deep Face Recognition Framework"</b>, <i>2020 Innovations in Intelligent Systems and Applications Conference (ASYU)</i>, 2020, pp. 23-27.</summary>

  ```BibTeX
  @inproceedings{serengil2020lightface,
    title        = {LightFace: A Hybrid Deep Face Recognition Framework},
    author       = {Serengil, Sefik Ilkin and Ozpinar, Alper},
    booktitle    = {2020 Innovations in Intelligent Systems and Applications Conference (ASYU)},
    pages        = {23-27},
    year         = {2020},
    doi          = {10.1109/ASYU50717.2020.9259802},
    url          = {https://ieeexplore.ieee.org/document/9259802},
    organization = {IEEE}
  }
  ```
</details>

<details>
  <summary>S. I. Serengil and A. Ozpinar, <b>"HyperExtended LightFace: A Facial Attribute Analysis Framework"</b>, <i>2021 International Conference on Engineering and Emerging Technologies (ICEET)</i>, 2021, pp. 1-4.</summary>

  ```BibTeX
  @inproceedings{serengil2021lightface,
    title        = {HyperExtended LightFace: A Facial Attribute Analysis Framework},
    author       = {Serengil, Sefik Ilkin and Ozpinar, Alper},
    booktitle    = {2021 International Conference on Engineering and Emerging Technologies (ICEET)},
    pages        = {1-4},
    year         = {2021},
    doi          = {10.1109/ICEET53442.2021.9659697},
    url          = {https://ieeexplore.ieee.org/document/9659697},
    organization = {IEEE}
  }
  ```
</details>

<details>
  <summary>S. Serengil and A. Ozpinar, <b>"Encrypted Vector Similarity Computations Using Partially Homomorphic Encryption: Applications and Performance Analysis"</b>, <i>arXiv preprint arXiv:2503.05850</i>, 2025.</summary>

  ```BibTeX
  @article{serengil2025vectorsimilarity,
    title={Encrypted Vector Similarity Computations Using Partially Homomorphic Encryption: Applications and Performance Analysis},
    author={Serengil, Sefik and Ozpinar, Alper},
    journal={arXiv preprint arXiv:2503.05850},
    note={doi: 10.48550/arXiv.2503.05850. [Online]. Available: \url{https://arxiv.org/abs/2503.05850}},
    year={2025}
  }
  ```
</details>

此外，如果您在 GitHub 项目中使用 deepface，请将 `deepface` 添加到 `requirements.txt` 中。

## 许可证

DeepFace 根据 MIT 许可证授权 - 更多详情请参见 [`LICENSE`](https://github.com/serengil/deepface/blob/master/LICENSE)。

DeepFace 封装了一些外部人脸识别模型：[VGG-Face](http://www.robots.ox.ac.uk/~vgg/software/vgg_face/)、[Facenet](https://github.com/davidsandberg/facenet/blob/master/LICENSE.md)（包括 128d 和 512d）、[OpenFace](https://github.com/iwantooxxoox/Keras-OpenFace/blob/master/LICENSE)、[DeepFace](https://github.com/swghosh/DeepFace)、[DeepID](https://github.com/Ruoyiran/DeepID/blob/master/LICENSE.md)、[ArcFace](https://github.com/leondgarse/Keras_insightface/blob/master/LICENSE)、[Dlib](https://github.com/davisking/dlib/blob/master/dlib/LICENSE.txt)、[SFace](https://github.com/opencv/opencv_zoo/blob/master/models/face_recognition_sface/LICENSE)、[GhostFaceNet](https://github.com/HamadYA/GhostFaceNets/blob/main/LICENSE) 和 [Buffalo_L](https://github.com/deepinsight/insightface/blob/master/README.md)。此外，年龄、性别和种族/民族模型是在 VGG-Face 的骨干网络上通过迁移学习训练的。类似地，DeepFace 封装了许多人脸检测器：[OpenCV](https://github.com/opencv/opencv/blob/4.x/LICENSE)、[Ssd](https://github.com/opencv/opencv/blob/master/LICENSE)、[Dlib](https://github.com/davisking/dlib/blob/master/LICENSE.txt)、[MtCnn](https://github.com/ipazc/mtcnn/blob/master/LICENSE)、[Fast MtCnn](https://github.com/timesler/facenet-pytorch/blob/master/LICENSE.md)、[RetinaFace](https://github.com/serengil/retinaface/blob/master/LICENSE)、[MediaPipe](https://github.com/google/mediapipe/blob/master/LICENSE)、[YuNet](https://github.com/ShiqiYu/libfacedetection/blob/master/LICENSE)、[Yolo](https://github.com/derronqi/yolov8-face/blob/main/LICENSE) 和 [CenterFace](https://github.com/Star-Clouds/CenterFace/blob/master/LICENSE)。最后，DeepFace 可选地使用[人脸防伪](https://github.com/minivision-ai/Silent-Face-Anti-Spoofing/blob/master/LICENSE)来确定给定图像是真实的还是伪造的。当您打算使用这些模型时，许可证类型将被继承。请检查这些模型用于生产目的的许可证类型。

DeepFace [徽标](https://thenounproject.com/term/face-recognition/2965879/) 由 [Adrien Coquet](https://thenounproject.com/coquet_adrien/) 创建，并根据 [Creative Commons: By Attribution 3.0 License](https://creativecommons.org/licenses/by/3.0/) 授权。
