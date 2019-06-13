Tencent AI SDK
==================

��ѶAI����ƽ̨php������,ϸ������ӿڲ���,֧����ʽ����,��ӭFork����Ŀ  
php sdk for tencent AI open platform.
��Ŀ��ַ��**https://github.com/uctoo/tencent-ai-php-sdk**  

## ֪ʶ׼��
ʹ��ǰ���Ȳ鿴��ѶAI����ƽ̨�ٷ��ĵ���  https://ai.qq.com/doc/ 

## Ŀ¼ 
> **[Ai.php �ٷ�API���](#user-content-1-aiphp-�ٷ�api���)**  

## Requirement ����Ҫ��

1. PHP >= 7.0
2. **[Composer](https://getcomposer.org/)**
3. openssl ��չ

## Installation ��װ

```shell
$ composer require uctoo/tencent-ai:dev-master
```

## Usage

����ʹ��:

----------

## 1. Ai.php �ٷ�API���
���ùٷ�API�� 

### ��Ҫ���� 
#### �����ı�����
- �ִ�	���ı��������ִܷ�ʶ��֧�ֻ���������Ŵ�����  
- ����	���ı����зִʣ�ͬʱΪÿ���ִʱ�ע��ȷ�Ĵ���  
- ר������	���ı�����ר�����ʵķִ�ʶ���ҳ��ı��е�ר������  
- ͬ���	ʶ���ı��д���ͬ��ʵķִʣ���������Ӧ��ͬ���  
#### �������
- ��ͼ�ɷ�	���ı�������ͼʶ�𣬿����ҳ���ͼ�������ĳɷ�  
- ��з���ʶ��	���ı�������з����������ж��������������棩  
#### ��������
- ��������  
#### ��������
- �ı����루AI Lab��	���ı����з��룬֧�ֶ�������֮�以��  
- �ı����루�������	���ı����з��룬֧�ֶ�������֮�以��  
#### OCR
- ���֤OCR	ʶ�����֤ͼ���������ϸ�����Ϣ  
- ��ʻ֤��ʻ֤OCR	ʶ����ʻ֤���ʻ֤ͼ��������ֶ���Ϣ  
- ͨ��OCR	ʶ���ϴ�ͼ��������ֶ���Ϣ   
- Ӫҵִ��OCR	ʶ��Ӫҵִ��������ֶ���Ϣ  
- ���п�OCR	ʶ�����п�������ֶ���Ϣ  
- ��д��OCR	����ʶ��ͼ��������д����ֶ���Ϣ  
- ����OCR	ʶ����������ֶ���Ϣ  
- ��ƬOCR	ʶ����Ƭͼ��������ֶ���Ϣ  
#### ͼƬ��Ч
- ͼƬ�˾�������Pͼ��	��ԭͼ�����˾���Ч�������ʺ�����ͼƬ  
- ͼƬ�˾���AI Lab��	��ԭͼ�����˾���Ч�������ʺϷ羰ͼƬ  

����ϸ������ο��ٷ��ĵ�

### ��ʼ������ 
```php
   $options = array(
			'appid'=>'110......', //��д���Ӧ�ñ�ʶ
			'app_key'=>'app_key......' //��д���Ӧ����Կ
		);
      $aiObj = new Ai($options);
      $res = $aiObj->nlp_textchat('hello world', 10000);         //���û������Ľӿ�
      $resultcontent = json_encode($res,JSON_UNESCAPED_UNICODE); //�������һ��json����
```

### Ԥ���峣���б�
```php
const API_URL_PREFIX = 'https://api.ai.qq.com/fcgi-bin';
//�����ı�����
const NLP_WORDSEG = '/nlp/nlp_wordseg?';
const NLP_WORDPOS = '/nlp/nlp_wordpos?';
const NLP_WORDNER = '/nlp/nlp_wordner?';
const NLP_WORDSYN = '/nlp/nlp_wordsyn?';
//�������
const NLP_WORDCOM = '/nlp/nlp_wordcom?';
//��з���
const NLP_TEXTPOLAR = '/nlp/nlp_textpolar?';
//��������
const NLP_TEXTTRANS = '/nlp/nlp_texttrans?';
//��������
const NLP_TEXTCHAT = '/nlp/nlp_textchat?';
//ͼƬʶ��
const VISION_SCENER = '/vision/vision_scener?';
const VISION_OBJECTR = '/vision/vision_objectr?';
//���ܼ���
const VISION_PORN = '/vision/vision_porn?';
//���֤OCRʶ��
const OCR_IDCARDOCR = '/ocr/ocr_idcardocr?';
//��ƬOCRʶ��
const OCR_BCOCR = '/ocr/ocr_bcocr?';
//��ʻ֤��ʻ֤OCRʶ��
const OCR_DRIVERLICENSEOCR = '/ocr/ocr_driverlicenseocr?';
//Ӫҵִ��OCRʶ��
const OCR_BIZLICENSEOCR = '/ocr/ocr_bizlicenseocr?';
//���п�OCRʶ��
const OCR_CREDITCARDOCR = '/ocr/ocr_creditcardocr?';
//ͨ��OCRʶ��
const OCR_GENERALOCR = '/ocr/ocr_generalocr?';
//������ױ
const PTU_FACECOSMETIC = '/ptu/ptu_facecosmetic?';
//������ױ
const PTU_FACEDECORATION = '/ptu/ptu_facedecoration?';
//ͼƬ�˾�
const PTU_IMGFILTER = '/ptu/ptu_imgfilter?';
//�����ں�
const PTU_FACEMERGE = '/ptu/ptu_facemerge?';
//��ͷ��
const PTU_FACESTICKER = '/ptu/ptu_facesticker?';
//������
const PTU_FACEAGE = '/ptu/ptu_faceage?';
//ģ��ͼƬ���
const IMAGE_FUZZY = '/image/image_fuzzy?';
//��ʳͼƬʶ��
const IMAGE_FOOD = '/image/image_food?';
//ͼ���ǩʶ��
const IMAGE_TAG = '/image/image_tag?';
//�������
const FACE_DETECTFACE = '/face/face_detectface?';
//�����Ա�
const FACE_FACECOMPARE = '/face/face_facecompare?';
```

## ����Ⱥ
QQȺ��102324323��ʹ�����ʣ����������״������Ⱥ��

## ��л
��л��ѶAI����ƽ̨2017��8�����뱾��˾������ԣ���л��ѶAI��������֧�֡�

## ����
������ô���Ŀ�����а�������ӭ������һ������

![����wechat](https://gitee.com/uctoo/uctoo/raw/master/Public/images/donate.png)

License
-------
MIT 