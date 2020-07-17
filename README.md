# API_ML_AI
| 文档名称 | 找厕所---产品需求文档 |
|:------: | :------: |
| 产品名 | 找厕所  |
| 产品描述 | 一款利用人流量统计和距离综合判断，为旅行中的女性用户提供最便捷厕所路线的APP|
| 产品版本 | 1.0 |
| 文件现状| 进行中|
| 文件作者| 李姗姗|
## 一、价值主张设计
### 1.加值宣言
-  我认为目前的旅游景区，长期存在着严重的排队现象，特别是女厕所。找厕所APP是使用地图API定位用户周围的厕所，调用人流量统计API，根据人流量与厕所的距离来综合判断选择厕所；然后调用路径规划API为用户提供路线。这些技术的综合运用能有效地缓解排队现象，且景区管理通过分析客流量分配厕所管理员，减少了人工成本，提升旅客游玩体验。
### 2.产品背景
-  随着我国经济的高速发展以及人们生活水平不断提高,人们外出旅游的需求日益增加。但旅游景区厕所作为游客进行旅行活动时的必备设施，长期普遍存在较严重的排队现象，是影响旅客游玩体验的一大重要因素。
### 3.核心价值(最小可行性产品)
- 提供定位、人流量统计服务功能，缓解用户旅行在外上厕所的排队现象。
### 4.用户痛点
- 在旅游景区中，不熟悉景区的环境，解决生理需求找厕所时，多次询问工作人员。
- 来到厕所后发现人流量非常大，排队现象严重。
- 用户集中在一个区域的厕所位置，但距离偏远一点的厕所人流量较少。
### 5.目标
- 前期目标：帮助女性搜索到周围的厕所位置，根据距离和人流量统计为用户推荐最佳目的地与规划最佳路线，节省用户时间，提高用户体验
- 后期目标：原有的基础上，在APP中添加页面为用户推荐旅行攻略，可多方面满足用户出门旅行的需求。
### 6.用户分析（主要用户和用户画像、使用场景）
- 主要用户：热爱旅行的18-30岁女性
- 用户画像：![用户画像](https://i.loli.net/2020/07/16/whS5rXJmx4i3MF6.png)
- 使用场景：

| 序号 | 使用场景 | 
|------| ------| 
|使用场景一| 小李在九寨沟景区中，有生理需求想上厕所时，周围没有景区工作人员，引路排指向的是一个大概的方向；小李打开“找厕所”APP，搜索附近的厕所，根据APP中推荐的厕所目的地与路线前往。 | 
|使用场景二| 小郑在大理古城中，向附近店铺人员询问厕所的位置，店铺人员指着一个方向说到往前面走，小郑对店铺人员说的位置感到茫然，这时她打开“找厕所”APP，搜索附近的厕所，发现另一个方向距离差不多的厕所位置人流量相对较少，于是根据最佳路线前往。| 
|使用场景三|小彭在故宫博物中，根据景区人员指引前往厕所后发现人流量极大，需要等待较长时间，这时她打开“找厕所”APP，搜索附近的厕所，发现距离远一点的厕所人流量少，于是她决定不再等待，根据“找厕所”APP推荐的路线前往距离远一点的厕所。| 

### 7.AI概率性考量
- 百度AI人流量识别功能使用高精度头肩检测算法，准确率90%以上，统计人数无上限，适应各种人群密集场所，且服务稳定，拥有精确的大流量服务，可靠性保障高达99%；环境中的遮挡物会干扰识别结果，且对摄像头架设的角度有一定要求，但这些都可以通过设定区域来排除干扰，提升识别效果，不会对用户产生较大的负面影响。
- 高德地图的精准度高，具有一定权威性，且在竞品中占有突出地位，精细程度对比百度地图与腾讯地图都是更加突出的。
- 参考链接：[竞品分析报告 | 高德地图 vs 百度地图 vs 腾讯地图](http://www.woshipm.com/evaluating/3867852.html)

### 8.需求列表与人工智能API加值
| 序号 | 用户需求 | 智能加值| API类型 |重要程度|
|:------:| :------: | :------: | :------: |:------: |
| 1 | 当前在什么位置 | 否 |手机地理定位|次重要|
| 2| 不清楚周围哪里有厕所| 是 | 高德开发平台的输入提示API |重要|
| 3 | 不知道哪里厕所的人流量相对较小 | 是| 百度开发平台的人流量统计识别API |重要|
| 4 | 不知道厕所的具体位置  | 是| 高德开发平台的路线规划API |次重要|

## 二、产品设计原型
- 1. 产品原型交互链接：[点击此处](https://modao.cc/app/19ce68e4cb745482e210f41c99a189f7768d9274?simulator_type=device) （开启全屏模式可以看得更清楚哦~）

- 2. 主要交互应用流程图：
![主要交互应用流程图](https://i.loli.net/2020/07/17/7RiGTxbdzOQnJCP.png)

- 3. 信息设计：
![信息设计](https://i.loli.net/2020/07/17/IZz5iwS3abYdgKk.png)

- 4. 产品架构图：
![产品架构图](https://i.loli.net/2020/07/17/4JswTcDMZyEq8Ka.png)

- 5. 产品流程图：
![产品流程图](https://i.loli.net/2020/07/17/KbWGevthX78VwJQ.png)

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

***

！[图片示例1](https://i.loli.net/2020/07/16/BQGsp76dJq3SfeN.png)
！[图片示例2](https://i.loli.net/2020/07/16/kPn1pfe7Jcg5a62.png)

#### （3）[路径规划API---高德开放平台](https://lbs.amap.com/api/webservice/guide/api/direction#walk)
- 接口描述：步行路径规划 API 可以规划100KM以内的步行通勤方案，并且返回通勤方案的数据。
- 接口地址：[https://restapi.amap.com/v3/direction/walking?parameters](https://restapi.amap.com/v3/direction/walking?parameters)
- 请求方式：GET
- 输入源代码
```
def walking(origin,destination,sig=None)->dict:
    url = 'https://restapi.amap.com/v3/direction/walking?parameters'
    params={
        'key':key,
        'origin':origin,
        'destination':destination,
        'output':'json'
    }
    response = requests.get(url,params=params)
    data = response.json()
    return data
九寨沟_location = 九寨沟['geocodes'][0]['location']
九寨沟公共厕所_location = '104.246078,33.242995'
九寨沟_九寨沟公共厕所 = walking(九寨沟_location,九寨沟公共厕所_location)
九寨沟_九寨沟公共厕所
```
- 由于输出源代码过长，详细代码示例:[调用高德开放平台-----路径规划API](https://www.jianshu.com/p/9b90f04c1878)

*** 

### 2.使用比较分析
