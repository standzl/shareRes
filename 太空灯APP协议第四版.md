# 太空灯APP协议
<br/>

## 设备端通用响应

| 属性名 | 值类型 | value |
|:----:|:----:|:----:|
| cmd  | String | APP端发送的cmd指令 |
| result  | Integer | 0:成功 1:错误 |

成功响应数据示例:

    {
		"cmd":"timeClock",
		"result":0
	}

失败响应数据示例:

    {
		"cmd":"timeClock",
		"result":1
	}


<br/>

## APP端指令

## **1. 开关灯指令(控制所有灯：白灯，彩色光灯，激光灯)**

| 属性名 | 值类型 | value |
|:----:|:----:|:----:|
| cmd  | String | lightOpen |
| state | Integer|0:关 1:开  |
| light | Integer| 1:白灯 2:彩光灯 3:激光灯 |

数据示例：

    {
		"cmd":"lightOpen",
        "state": 1,
        "light": 3
	}

设备端响应参见“通用设备响应”

<br/>

## **2.时钟指令**


| 属性名 | 值类型 | value |
|:----:|:----:|:----:|
| cmd  | String | timeClock |
| dayTime | String | eg: 2024/05/27 14:11:35 |

数据示例：

    {
		"cmd":"timeClock",
        "dayTime":"2024/05/27 14:11:35"
	}


设备端响应参见“通用设备响应”
<br/>

## **3.设置白灯亮度**

| 属性名 | 值类型 | value | 属性说明 |
|:----:|:----:|:----:|:----:|
| cmd  | String | setWLightBness ||
| level | Integer| (0-100)  | 白灯亮度 |

数据示例:

    {
		"cmd":"setWLightBness",
        "level": 80
	}

设备端响应参见“通用设备响应”


<br/>


## **4.设置彩灯颜色**

| 属性名 | 值类型 | value |属性说明|
|:----:|:----:|:----:|:----:|
| cmd  | String | setRGBLightColor | |
| color | String |(（000000-FFFFFF）（RGB）)  | 彩灯色值 |
| whiteOn | Integer| 1:开启白光 0:关闭白光 | 是否开启白光 |


数据示例:

    {
		"cmd":"setRGBLightColor",
        "color": "2af6cc",
		"whiteOn": 1
	}

设备端响应参见“通用设备响应”

<br/>

## **5.设置彩灯亮度**

| 属性名 | 值类型 | value |属性说明|
|:----:|:----:|:----:|:----:|
| cmd  | String | setRGBBness ||
| level | Integer | (0~100)  |彩灯亮度值|


数据示例:

    {
		"cmd":"setRGBBness",
        "level": 100
	}

设备端响应参见“通用设备响应”

<br/>



## **6.设置转盘速度**

| 属性名 | 值类型 | value |属性说明|
|:----:|:----:|:----:|:----:|
| cmd  | String | spinSpeed ||
| speed | Integer | 0:停止 1:慢速 2:中速 3:快速  |转盘速度，取值[0-3]|

数据示例:

    {
		"cmd":"spinSpeed",
        "speed": 2
	}

设备端响应参见“通用设备响应”

<br/>

## **7.灯光呼吸开关**

| 属性名 | 值类型 | value |属性说明|
|:----:|:----:|:----:|:----:|
| cmd  | String | breathConfig ||
| light | Integer | 0 |0:白灯 1:彩光灯 2:激光|
| breathEnable|Integer|1|是否启用呼吸效果 0:关闭 1:开启|

数据示例:

    {
		"cmd":"breathConfig",
        "light": 0,
		"breathEnable":1
	}

设备端响应参见“通用设备响应”

<br/>

## **8.设置音乐播放/暂停 上一首 下一首**

| 属性名 | 值类型 | value |属性说明|
|:----:|:----:|:----:|:----:|
| cmd  | String | playControl ||
| state | Integer | 0:暂停 1:播放 2：上一首 3:下一首  |音乐操作|

数据示例:

    {
		"cmd":"playControl",
		"state": 2
	}

设备端响应参见“通用设备响应”

<br/>

## **9.设置音乐灵敏度**

| 属性名 | 值类型 | value |属性说明|
|:----:|:----:|:----:|:----:|
| cmd  | String | setMusicSens ||
| level | Integer | 80  |音乐灵敏度,取值[0-100]|

数据示例:

    {
		"cmd":"setMusicSens",
		"level": 60
	}

设备端响应参见“通用设备响应”

<br/>

## **10.设置音乐模式开关**

| 属性名 | 值类型 | value |属性说明|
|:----:|:----:|:----:|:----:|
| cmd  | String | setMusicModeSwitch ||
| modeOn | Integer | 0:关闭 1:打开  |音乐模式开关|

数据示例:

    {
		"cmd":"setMusicModeSwitch",
		"modeOn": 1
	}

设备端响应参见“通用设备响应”

<br/>

## **11.设置音乐模式律动场景**

| 属性名 | 值类型 | value |属性说明|
|:----:|:----:|:----:|:----:|
| cmd  | String | setMusicScene ||
| scene | Integer | 0：摇滚 1：爵士 2：经典 3：球赛 4：游戏  |音乐模式开关|


数据示例:

    {
		"cmd":"setMusicScene",
		"scene": 0
	}

设备端响应参见“通用设备响应”

<br/>

## **12.设置设备音量**

| 属性名 | 值类型 | value |属性说明|
|:----:|:----:|:----:|:----:|
| cmd  | String | deviceVolume ||
| volume | Integer | 80  |设备音量,取值[0-100]|


数据示例:

    {
		"cmd":"deviceVolume",
		"scene": 70
	}

设备端响应参见“通用设备响应”

<br/>

## **13.设置总开关延时**

| 属性名 | 值类型 | value |属性说明|
|:----:|:----:|:----:|:----:|
| cmd  | String | switchDelay ||
| state | Integer | 0:总开关关闭 1：总开关开启  |总开关延时操作|
| hour|Integer|15|时,取值[0-24]|
|minutes|Integer|32|分,取值[0-59]|

数据示例:

    {
		"cmd":"switchDelay",
		"state": 1,
		"hour": 0,
		"minutes":1
	}

设备端响应参见“通用设备响应”

<br/>


## **14.设置音乐播放源**

| 属性名 | 值类型 | value |属性说明|
|:----:|:----:|:----:|:----:|
| cmd  | String | musicSrc ||
| source | Integer | 0:APP音源 1：本地音乐  |播放源|

数据示例:

    {
		"cmd":"musicSrc",
		"source": 1
	}

设备端响应参见“通用设备响应”

<br/>


## **15.设置机器运行状态**

| 属性名 | 值类型 | value |属性说明|
|:----:|:----:|:----:|:----:|
| cmd  | String | setDevSwitchState ||
| state | Integer |  65 |机器开关状态 0:关闭(所有的停止运行)，1:开启（恢复停止之前的动作）|

数据示例:

    {
		"cmd":"setDevSwitchState",
		"state":1
	}

设备端响应参见“通用设备响应”

<br/>

## **16.推荐场景选择**

| 属性名 | 值类型 | value |属性说明|
|:----:|:----:|:----:|:----:|
| cmd  | String | suggestedScene ||
| sceneCategory | Integer | 3  |推荐场景 1:单双色动态2:单色静态3:动态场景4:假日陪伴5:主题成语 自定义场景:[6~10] 0:关闭场景显示|


数据示例:

    {
		"cmd":"suggestedScene",
		"sceneCategory": 3
	}


设备端响应参见“通用设备响应”

<br/>


## **17.自定义场景设置**

| 属性名 | 值类型 | value |属性说明|
|:----:|:----:|:----:|:----:|
| cmd  | String | customeScene ||
| name | String | myScene01  |自定义场景名称|
|schedule|Object| 参见说明 |包含灯光属性设置的调度信息|

数据示例:


    {
		"cmd":"customeScene",
		"name":"cmt1",
		"schedule":{
			"enable":true,
			"Interval":3000,
			"seqInterval":false,
			"loop":true,
			"isConcurrent":false
			"lightSpeed":55,
			"noise":[0,12,33]
			"sequence":[{
				"name":"white",
				"colorNum":2,
				"colorValue": ["cccccc", "d5d4d4"],
				"duration":2000,
				"lightChangeMode":1,
				"lightBness":65,
				"lightChangeSpeed":55,
				"open":true
			},{
				"name":"rgb",
				"colorNum":2,
				"colorValue":["cccccc", "d5d4d4"],
				"lightChangeMode":1,
				"duration":5000,
				"lightBness":78,
				"lightChangeSpeed":45,
				"open":true
			},{
				"name":"laser",
				"laserSat":80,
				"duration":1000,
				"laserBreathAnim":1,
				"open":false
			}]
		}
	}


schedule字段说明

| 属性名 | 值类型 | value |属性说明|
|:----:|:----:|:----:|:----:|
| enable  | boolean | true:开启 false:关闭 | 是否开启灯光调度,如果为true,则循环sequence数组 |
| Interval | Long |   |调度间隔,单位毫秒。表示每隔多少毫秒切换到sequence数组中的下一个|
| seqInterval | boolean | false  |是否启用每个灯光的自定义间隔,如果启用,则忽略Interval属性,改为每个灯的duration|
| loop | boolean |  true:循环 false:一次性  |是否循环,如果为true,则会无限循环sequence数组中的灯设置|
| isConcurrent | boolean  | true:并行 false:时序循环 |是否并行,表示所有灯同时打开。如果是并行,则loop属性必须为false|
| noise | Int[] |  [0,3,1,2,9]  |白噪音编号数组,表示需要播放的音乐,白噪音序号为0~7|
|sequence|OjbectArray| 参见说明 |灯光循环时序,其中数组中的每个元素包含了各个灯光的属性设置,比如白光灯,彩灯,激光灯,不同灯光排列定义了不同的循环时序|


sequence字段说明

| 属性名 | 值类型 | value |属性说明|
|:----:|:----:|:----:|:----:|
| name  | String | white | 灯光名称 white:白灯 rgb:彩灯 laser:激光灯 |
| colorNum | Integer | 2  |颜色数量,必须和colorValue数组的长度保持一致|
| colorValue | String[] |    |具体的颜色数组|
| lightChangeMode | Integer |  1  |灯光切换模式 0:静态 1:跳变 2:呼吸 |
|lightBness|Integer| 55 |灯光亮度(0~100)|
|duration|Long|  |灯光显示的持续时间,单位毫秒.受open和seqInterval的约束,如果seqInterval为true,则此字段忽略|
|lightChangeSpeed|Integer| 25 |灯光变换速度(0~100)|
|open|boolean| true |灯光是否打开 true:打开 false:关闭|
|laserSat|Integer|  |激光灯饱和度|
|laserBreathAnim|Integer| 1 |激光灯呼吸动画 0:关闭 1:开启|
|lightSpeed|Integer|0|彩灯/白灯 转盘速度,0:停止 1:慢速 2:中速 3:快速|


设备端响应参见“通用设备响应”

<br/>


## **18.发送非场景模式下数据(水纹、激光、音乐)**

| 属性名 | 值类型 | value |属性说明|
|:----:|:----:|:----:|:----:|
| cmd  | String | setCustomModeData ||
| deviceState | Integer |  1 |机器开关状态 0:关闭(所有的停止运行) 1开启（恢复停止之前的动作）|
| lightUIState | Integer |  1 |白灯/彩灯界面开关状态 0:关闭（白灯/彩灯 关闭 转盘停止转动）1:开启 （恢复停止之前的动作）|
|light|Integer|0|控制的灯0:白灯,1：彩光灯,2激光灯|
| lightState | Integer |  1 |0:关闭 1:开启|
| WLightBness | Integer |  90 |白灯亮度(0~100)|
| rgbBness| Integer |  55 |彩灯亮度(0~100)|
| laserBness | Integer |  55 |激光灯亮度(0~100)|
| rgbLightColor | String |  cccccc |彩灯颜色 （000000-FFFFFF）（RGB）|
| rgbSat | Integer |  55 |彩灯饱和度 (0~100)|
| breathAnimaOn | Integer |  1 |彩灯和白灯呼吸开关 0:关闭 1:开启|
| rotationSpeed | Integer |  1 |彩灯和白灯转盘速度 （0～3）0:停止 1:慢速 2:中速 3:快速|
| musicModeOn | Integer |  1 |音乐模式开关 0:关闭 1:开启|
| musicPlayState | Integer |  1 |音乐当前状态 0:暂停 1:播放 2:上一首 3:下一首|
| musicSens | Integer |  66 |音乐灵敏度(0~100)|
| musicStyle | Integer |  1 |音乐模式律动场景 0:摇滚 1:爵士 2:经典 3:球赛 4:游戏|
| deviceVolume | Integer |  1 |设备音量 0:关闭 1:开启|
| musicSource | Integer |  1 |音乐模式 0:第三方音乐 1:本地音乐|
| noiseNumber | Integer |  5 |白噪音编号(0~7)|

数据示例:

    {
		"cmd":"setCustomModeData",
		"deviceState":1,
		"lightUIState":1,
		"light":1,
		"lightState":1,
		"WLightBness":55,
		"rgbBness":55,
		"laserBness":66,
		"rgbLightColor":"cccccc",
		"rgbSat":55,
		"breathAnimaOn":1,
		"rotationSpeed":1,
		"musicModeOn":1,
		"musicPlayState":1,
		"musicSens":34,
		"musicStyle":1,
		"deviceVolume":1,
		"musicSource":1,
		"noiseNumber":7
	}

设备端响应参见“通用设备响应”

<br/>

## **19.获取非场景模式下数据(水纹、激光、音乐)**

| 属性名 | 值类型 | value |属性说明|
|:----:|:----:|:----:|:----:|
| cmd  | String | getCustomModeData ||

数据示例:

    {
		"cmd":"getCustomModeData"
	}


设备端响应

| 属性名 | 值类型 | value |属性说明|
|:----:|:----:|:----:|:----:|
| cmd  | String | getCustomModeData ||
| state  | String | 0 |状态 0:正常 1:定时编号(增替)|
| delayHour  | Integer | 0 |延时时间 时(0~24)|
| delayMins  | Integer | 1 |延时时间 分(0~59) |
| deviceState | Integer |  1 |机器开关状态 0:关闭(所有的停止运行) 1开启（恢复停止之前的动作）|
| lightUIState | Integer |  1 |白灯/彩灯界面开关状态 0:关闭（白灯/彩灯 关闭 转盘停止转动）1:开启 （恢复停止之前的动作）|
|light|Integer|0|控制的灯0:白灯,1：彩光灯,2激光灯|
| lightState | Integer |  1 |0:关闭 1:开启|
| WLightBness | Integer |  90 |白灯亮度(0~100)|
| rgbBness| Integer |  55 |彩灯亮度(0~100)|
| laserBness | Integer |  55 |激光灯亮度(0~100)|
| rgbLightColor | String |  cccccc |彩灯颜色 （000000-FFFFFF）（RGB）|
| rgbSat | Integer |  55 |彩灯饱和度 (0~100)|
| breathAnimaOn | Integer |  1 |彩灯和白灯呼吸开关 0:关闭 1:开启|
| rotationSpeed | Integer |  1 |彩灯和白灯转盘速度 （0～3）0:停止 1:慢速 2:中速 3:快速|
| musicModeOn | Integer |  1 |音乐模式开关 0:关闭 1:开启|
| musicPlayState | Integer |  1 |音乐当前状态 0:暂停 1:播放 2:上一首 3:下一首|
| musicSens | Integer |  66 |音乐灵敏度(0~100)|
| musicStyle | Integer |  1 |音乐模式律动场景 0:摇滚 1:爵士 2:经典 3:球赛 4:游戏|
| deviceVolume | Integer |  1 |设备音量 0:关闭 1:开启|
| musicSource | Integer |  1 |音乐模式 0:第三方音乐 1:本地音乐|
| noiseNumber | Integer |  5 |白噪音编号(0~7)|


数据示例:

    {
		"cmd":"getCustomModeData",
		"state":0,
		"delayHour":0,
		"delayMins":1,
		"deviceState":1,
		"lightUIState":1,
		"light":1,
		"lightState":1,
		"WLightBness":55,
		"rgbBness":55,
		"laserBness":66,
		"rgbLightColor":"cccccc",
		"rgbSat":55,
		"breathAnimaOn":1,
		"rotationSpeed":1,
		"musicModeOn":1,
		"musicPlayState":1,
		"musicSens":34,
		"musicStyle":1,
		"deviceVolume":1,
		"musicSource":1,
		"noiseNumber":7
	}

<br/>