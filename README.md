Tencent AI SDK
==================

腾讯AI开放平台php开发包,细化各项接口操作,支持链式调用,欢迎Fork此项目  
php sdk for tencent AI open platform.
项目地址：**https://github.com/uctoo/tencent-ai-php-sdk**  

## 知识准备
使用前请先查看腾讯AI开放平台官方文档：  https://ai.qq.com/doc/ 

## 目录 
> **[Ai.php 官方API类库](#user-content-1-aiphp-官方api类库)**  

## Requirement 运行要求

1. PHP >= 7.0
2. **[Composer](https://getcomposer.org/)**
3. openssl 拓展

## Installation 安装

```shell
$ composer require uctoo/tencent-ai:dev-master
```

## Usage

基本使用:

----------

## 1. Ai.php 官方API类库
调用官方API； 

### 主要功能 
#### 基础文本分析
- 分词	对文本进行智能分词识别，支持基础词与混排词粒度  
- 词性	对文本进行分词，同时为每个分词标注正确的词性  
- 专有名词	对文本进行专有名词的分词识别，找出文本中的专有名词  
- 同义词	识别文本中存在同义词的分词，并返回相应的同义词  
#### 语义解析
- 意图成分	对文本进行意图识别，快速找出意图及上下文成分  
- 情感分析识别	对文本进行情感分析，快速判断情感倾向（正面或负面）  
#### 智能闲聊
- 基础闲聊  
#### 机器翻译
- 文本翻译（AI Lab）	对文本进行翻译，支持多种语言之间互译  
- 文本翻译（翻译君）	对文本进行翻译，支持多种语言之间互译  
#### OCR
- 身份证OCR	识别身份证图像上面的详细身份信息  
- 行驶证驾驶证OCR	识别行驶证或驾驶证图像上面的字段信息  
- 通用OCR	识别上传图像上面的字段信息   
- 营业执照OCR	识别营业执照上面的字段信息  
- 银行卡OCR	识别银行卡上面的字段信息  
- 手写体OCR	检测和识别图像上面手写体的字段信息  
- 车牌OCR	识别车牌上面的字段信息  
- 名片OCR	识别名片图像上面的字段信息  
#### 图片特效
- 图片滤镜（天天P图）	对原图进行滤镜特效处理，更适合人物图片  
- 图片滤镜（AI Lab）	对原图进行滤镜特效处理，更适合风景图片  

更详细内容请参考官方文档

### 初始化动作 
```php
   $options = array(
			'appid'=>'110......', //填写你的应用标识
			'app_key'=>'app_key......' //填写你的应用密钥
		);
      $aiObj = new Ai($options);
      $res = $aiObj->nlp_textchat('hello world', 10000);         //调用基础闲聊接口
      $resultcontent = json_encode($res,JSON_UNESCAPED_UNICODE); //结果进行一下json编码
```

### 预定义常量列表：
```php
const API_URL_PREFIX = 'https://api.ai.qq.com/fcgi-bin';
//基本文本分析
const NLP_WORDSEG = '/nlp/nlp_wordseg?';
const NLP_WORDPOS = '/nlp/nlp_wordpos?';
const NLP_WORDNER = '/nlp/nlp_wordner?';
const NLP_WORDSYN = '/nlp/nlp_wordsyn?';
//语义解析
const NLP_WORDCOM = '/nlp/nlp_wordcom?';
//情感分析
const NLP_TEXTPOLAR = '/nlp/nlp_textpolar?';
//机器翻译
const NLP_TEXTTRANS = '/nlp/nlp_texttrans?';
//智能闲聊
const NLP_TEXTCHAT = '/nlp/nlp_textchat?';
//图片识别
const VISION_SCENER = '/vision/vision_scener?';
const VISION_OBJECTR = '/vision/vision_objectr?';
//智能鉴黄
const VISION_PORN = '/vision/vision_porn?';
//身份证OCR识别
const OCR_IDCARDOCR = '/ocr/ocr_idcardocr?';
//名片OCR识别
const OCR_BCOCR = '/ocr/ocr_bcocr?';
//行驶证驾驶证OCR识别
const OCR_DRIVERLICENSEOCR = '/ocr/ocr_driverlicenseocr?';
//营业执照OCR识别
const OCR_BIZLICENSEOCR = '/ocr/ocr_bizlicenseocr?';
//银行卡OCR识别
const OCR_CREDITCARDOCR = '/ocr/ocr_creditcardocr?';
//通用OCR识别
const OCR_GENERALOCR = '/ocr/ocr_generalocr?';
//人脸美妆
const PTU_FACECOSMETIC = '/ptu/ptu_facecosmetic?';
//人脸变妆
const PTU_FACEDECORATION = '/ptu/ptu_facedecoration?';
//图片滤镜
const PTU_IMGFILTER = '/ptu/ptu_imgfilter?';
//人脸融合
const PTU_FACEMERGE = '/ptu/ptu_facemerge?';
//大头贴
const PTU_FACESTICKER = '/ptu/ptu_facesticker?';
//颜龄检测
const PTU_FACEAGE = '/ptu/ptu_faceage?';
//模糊图片检测
const IMAGE_FUZZY = '/image/image_fuzzy?';
//美食图片识别
const IMAGE_FOOD = '/image/image_food?';
//图像标签识别
const IMAGE_TAG = '/image/image_tag?';
//人脸检测
const FACE_DETECTFACE = '/face/face_detectface?';
//人脸对比
const FACE_FACECOMPARE = '/face/face_facecompare?';
```