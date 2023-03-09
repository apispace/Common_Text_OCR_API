# APISpace 介绍
**本 API 服务由 [APISpace（apispace.com）](https://www.apispace.com/?utm_source=github&utm_term=tongyongwenziocr) 提供。**

APISpace 是 Eolink 旗下专业的 API 开放与交易平台，为广大企业以及个人开发者提供多维度、全方位的API接口，覆盖短信验证、天气查询、快递物流、OCR文字识别等海量 API 服务，帮助用户快速获取数据，降低获取数据的成本和难度，提升开发效率。

APISpace 提供15种开发语言的代码示例，分别是：
- Java(OK HTTP)
- HTTP
- cURL
- 微信小程序
- PHP(pecl_http)、PHP(cURL)
- Python(http.client)、Python(Requests)
- JavaScript(Jquery AJAX)、JavaScript(XHR)
- NodeJS(Native)、NodeJS(Request)
- Ruby(Net:Http)
- Shell(Httpie)、Shell(cUrl)

# 通用文字识别OCR
多场景、多语种、高精度的整图文字检测和识别服务，多项指标行业领先，可识别中、英、日、韩、法、德多种语言。

**使用该产品前，您需要通过 [https://www.apispace.com/eolink/api/ocrbase/introduction](https://www.apispace.com/eolink/api/ocrbase/introduction?utm_source=github&utm_term=tongyongwenziocr) 申请API服务**

本文档末尾提供了 Python(Requests) 的调用代码示例，可以前往文档末尾查看。

更多代码示例：[https://www.apispace.com/eolink/api/ocrbase/guidence/](https://www.apispace.com/eolink/api/ocrbase/guidence/?utm_source=github&utm_term=tongyongwenziocr)

### 应用场景

1.  #### **拍照/截图识别**

使用通用文字识别技术，实现拍照文字识别、相册图片文字识别和截图文字识别，可应用于搜索、书摘、笔记、翻译等移动应用中，方便用户进行文本的提取或录入，有效提升产品易用性和用户使用体验。

2.  #### **内容审核与监管**

自动提取图像中的文字内容，结合文本审核技术识别违规内容，提示相应风险，协助进行违规处理，可应用于电商广告审核、舆情监管等场景，帮助企业有效规避业务风险。

3.  #### **视频内容分析**

检测识别视频中的字幕、标题、弹幕等文字内容，并根据文字位置判断文字类型，可应用于视频分类和标签提取、视频内容审核、营销分析等场景，有效提升内容分类、检索的效率。

4.  #### **纸质文档电子化**

识别提取各类医疗单据、金融财税票据、法律卷宗等纸质文档中的文字信息，并可基于位置信息进行比对、结构化处理，提高信息录入、存档、检索的效率。

### 识别效果

```
{
    "words_result": [{
        "word": " APispace",
        "location": [
            [57, 54],
            [395, 54],
            [395, 108],
            [57, 108]
        ]
    }, {
        "word": "通用文字识别OCR",
        "location": [
            [55, 223],
            [711, 223],
            [711, 285],
            [55, 285]
        ]
    }, {
        "word": "多场景：多场景、高精度的整图文字检测和识别服务",
        "location": [
            [83, 437],
            [836, 437],
            [836, 468],
            [83, 468]
        ]
    }, {
        "word": "多语种：可识别中、英、日、韩、法、德多种语言",
        "location": [
            [95, 481],
            [806, 483],
            [806, 514],
            [95, 512]
        ]
    }, {
        "word": "高精度：多项指标行业领先",
        "location": [
            [90, 529],
            [486, 529],
            [486, 560],
            [90, 560]
        ]
    }],
    "words_count": 5,
    "log_id": "b73e85a2-bd99-11ed-bc35-000000015f2c"
}
```

### 服务保障
![image](https://user-images.githubusercontent.com/36323798/223977455-9c5d0575-2eb5-471a-ac5f-f918ffa9f463.png)

### Python(Requests) 调用代码示例

```
import requests

url = "https://eolink.o.apispace.com/ocrbase/ocr/v1/base"

payload = {"image":"","url":"https://data-apibee.apispace.com/license/1678270527930990ebabe-a570-44ca-9966-b892d2bb6df8","language":"CHN_ENG"}

headers = {
    "X-APISpace-Token":"",
    "Authorization-Type":"apikey",
    "Content-Type":"application/json"
}

response=requests.request("POST", url, data=json.dumps(payload), headers=headers)

print(response.text)

```

