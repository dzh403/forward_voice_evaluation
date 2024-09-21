## 语音评测转发

此接口为语音评测的转发与保存接口，主要功能有：  
（1）将用户上传的音频文件转发到有道云语音评测接口并返回评测结果  
（2）将音频文件保存至oss


**请求方式：**  
- POST

**参数：**

| 参数名       | 必选 | 类型      | 说明                                          |
|:----------|:---|:--------|---------------------------------------------|
| file      | 是	 | file	   | 仅支持wav文件上传                                  |
| user_id   | 是	 | int	    | 用户id                                        |
| word      | 是	 | string	 | 读取的单词，如：ruler ，注意如上传句子时，建议此处还是上传关键单词，不要全句内容 |
| text      | 是	 | string	 | 要评测的音频文件对应的文本                               |
| lang_type | 是	 | string	 | 源语言,wav文件中的语言，仅支持 en \ zh-CHS               |

注：此接口为转发接口，语音评测接口说明：https://ai.youdao.com/DOCSIRMA/html/tts/api/yypc/index.html#section-9

**Response返回结果**

**1、成功返回示例**

```
{
    "evaluation_result": {
        "emotion": 0,
        "end": 0.99,
        "errorCode": "0",
        "fluency": 92.741432,
        "integrity": 100,
        "intonation": "",
        "overall": 88.386292,
        "pronunciation": 85.482864,
        "refText": "ruler",
        "requestId": "0581c818-a74c-4e23-8b7e-ff31cf1bbb9f",
        "service": "capt",
        "speed": 86.956505,
        "start": 0.3,
        "version": "capt-onetime-en:online-V2.0.8",
        "words": [
            {
                "IPA": "ˈruːlər",
                "end": 0.99,
                "phonemes": [
                    {
                        "calibration": "r",
                        "calibration-diphone": "",
                        "end": 0.54,
                        "judge": true,
                        "phoneme": "r",
                        "prominence": 0,
                        "pronunciation": 76.945892,
                        "start": 0.3,
                        "stress_detect": false,
                        "stress_ref": false
                    },
                    {
                        "calibration": "uː",
                        "calibration-diphone": "",
                        "end": 0.69,
                        "judge": true,
                        "phoneme": "uː",
                        "prominence": 0,
                        "pronunciation": 100,
                        "start": 0.54,
                        "stress_detect": false,
                        "stress_ref": false
                    },
                    {
                        "calibration": "l",
                        "calibration-diphone": "",
                        "end": 0.78,
                        "judge": true,
                        "phoneme": "l",
                        "prominence": 0,
                        "pronunciation": 100,
                        "start": 0.69,
                        "stress_detect": false,
                        "stress_ref": false
                    },
                    {
                        "calibration": "ər",
                        "calibration-diphone": "",
                        "end": 0.99,
                        "judge": true,
                        "phoneme": "ər",
                        "prominence": 0,
                        "pronunciation": 100,
                        "start": 0.78,
                        "stress_detect": false,
                        "stress_ref": false
                    }
                ],
                "phonics": [
                    {
                        "overall": 76,
                        "phonme": [
                            "r"
                        ],
                        "spell": "r"
                    },
                    {
                        "overall": 100,
                        "phonme": [
                            "uː"
                        ],
                        "spell": "u"
                    },
                    {
                        "overall": 100,
                        "phonme": [
                            "l"
                        ],
                        "spell": "l"
                    },
                    {
                        "overall": 100,
                        "phonme": [
                            "ə",
                            "r"
                        ],
                        "spell": "er"
                    }
                ],
                "pronunciation": 85.482864,
                "start": 0.3,
                "word": "ruler"
            }
        ]
    },
    "filename": "1_ruler_1726796727.wav",
    "oss_url": "https://oss.abc.com.cn/wav/ruler/1/1_ruler_1726796727.wav",
    "status": "true"
}
