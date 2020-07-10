# API_ML_AI
## 价值主张设计
### 1.产品背景
-  随着我国经济的高速发展以及人们生活水平不断提高,人们外出旅游的需求日益增加。但旅游景区厕所作为游客进行旅行活动时的必备设施，长期普遍存在较严重的排队现象，是影响旅客游玩体验的一大重要因素。
### 2.加值宣言
-  使用地图API定位用户周围的厕所，调用人流量检测API得到厕所所在处的人流量，用户通过人流量与厕所的距离来综合判断选择厕所；最终使用路径规划为用户提供路线。这些技术的综合运用能有效地缓解排队现象，且景区管理通过分析客流量分配厕所管理员，减少了人工成本，提升旅客游玩体验。
### 3.核心价值(最小可行性产品)
- 提供定位、人流量统计服务功能，缓解用户旅行在外上厕所的排队现象。
### 4.用户痛点
- 在旅游景区中，不熟悉景区的环境，解决生理需求找厕所时，多次询问工作人员。
- 来到厕所后发现人流量非常大，排队现象严重。
- 用户集中在一个区域的厕所位置，但距离偏远一点的厕所人流量较少。
### 5.用户分析（主要用户和用户画像、使用场景）
### 6.AI概率性考量
### 7.需求列表与人工智能API加值
| 序号 | 用户需求 | API加值 |重要程度|
|:------:| :------: | :------: | :------: |
| 1 | 不清楚周围哪里有厕所 | 高德开发平台的输入提示API |重要|
| 2 | 不知道哪里厕所的人流量相对较小 | 百度开发平台的人流量统计识别API |重要|
| 3 | 不知道厕所的具体位置  | 高德开发平台的路线规划API |次重要|
## 三、API 产品使用及输出展示
### 1.API展示说明及输出
#### （1）[输入提示API---高德开放平台](https://lbs.amap.com/api/webservice/guide/api/inputtips)
- 接口描述：输入提示是一类简单的HTTP接口，提供根据用户输入的关键词查询返回建议列表。
- 接口地址：[https://restapi.amap.com/v3/assistant/inputtips?parameters](https://restapi.amap.com/v3/assistant/inputtips?parameters)
- 请求方式：GET
- 输入源代码
```
import requests
key='334190ffbcbd51cfe6c7f81594a9b9de'
def hint(keywords=None,type='分类代码',location=None,city='citycode',sig=None,citylimit='false',datatype='all',homeorcorp=None)->dict:
    url = 'https://restapi.amap.com/v3/assistant/inputtips?parameters'
    params={
        'key': key,
        'location':location,
        'keywords':keywords,
        'type':type,
        'city':city,
        'citylimit':citylimit,
        'datatype':datatype,
        'homeorcorp':homeorcorp,
        'homeorcorp':homeorcorp,
        'sig':sig,
        'output':'json'
    }
    response = requests.get(url,params=params)
    data = response.json()
    return data
hint_厕所 = hint(keywords='九寨沟-公共厕所')
hint_厕所
```
- 由于输出源代码过长，详细代码示例:[调用高德开放平台-----输入提示API](https://www.jianshu.com/p/eaf69d91c30f)

***

#### （2）[人流量统计---百度AI开放平台](https://ai.baidu.com/ai-doc/BODY/7k3cpyy1t)
- 接口描述：对于输入的一张图片（可正常解码，且长宽比适宜），识别和统计图像当中的人体个数（静态统计，不支持追踪和去重）。适用于3米以上的中远距离俯拍，以头部为主要识别目标统计人数，无需正脸、全身照，适应各类人流密集场景（如：机场、车展、景区、广场等）；默认识别整图中的人数，支持指定不规则区域的人数统计，同时可输出渲染图片。摄像头硬件选型无特殊要求，分辨率建议720p以上，更低分辨率的图片也能识别，只是效果可能有差异。暂不适用夜间红外监控图片，后续会考虑扩展。
- 接口地址：[https://aip.baidubce.com/rest/2.0/image-classify/v1/body_num](https://aip.baidubce.com/rest/2.0/image-classify/v1/body_num)
- 请求方式：POST
- 输入源代码
```
import requests
import base64
request_url = "https://aip.baidubce.com/rest/2.0/image-classify/v1/body_num"
# 二进制方式打开图片文件
f = open('Desktop/picture.jpg', 'rb')
img = base64.b64encode(f.read())
params = {"image":img}
access_token = '24.0c0289a210b48d32b4c1318f86a1a889.2592000.1596955912.282335-21236519'
request_url = request_url + "?access_token=" + access_token
headers = {'content-type': 'application/x-www-form-urlencoded'}
response = requests.post(request_url, data=params, headers=headers)
if response:
    print (response.json())
```

- 输出源代码
```
{'person_num': 26, 'log_id': 6154891608034342474}
```
- 详细代码示例：[调用百度AI开放平台-----人流量统计API](https://www.jianshu.com/p/e2e66eeaf687)
