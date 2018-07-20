!>  **当前版本**：[UWS 账户服务 V1.0.0][account_document_url]  
 **发布时间**：2018-07-19  


## 简介

> 账号服务旨在提供涵盖物联全流程的访问控制服务，为开发者搭建统一的用户登录系统。  

开发者通过集成U+IOT平台账号服务，不仅提供用户账号的注册、登录、找回密码等账户管理服务，同时帮助开发者构建包括物联设备的统一控制、设备与用户权限管理等在内的一致性的IOT系统化管控模式。

![账户图片][account_type]

### 名词解释

-  **海尔OAuth授权**
>  指海尔集团用户中心对外提供的统一账户授权，可使用该种用户授权登录海尔优家IOT平台获取用户设备相关权限，同时具备登录海尔集团旗下相关其他业务服务权限，如海尔商城、海尔社区等；


- **海尔优家 账号**
>  指海尔集团旗下海尔优家平台对外提供的自有物联网账户体系，该账户体系具备绑定/控制等操作海尔物联网家电权限；

若使用海尔OAuth授权登录，按照海尔OAuth接入要求，可同时自动获得海尔优家账号信息；即使用海尔账号的同时获得海尔优家账号；

- **海尔优家 OAuth**
> 指海尔优家对外提供的OAuth服务，需要使用海尔优家账号进行登录授权；

由于海尔账号同时具备海尔优家账号权限，顾也可在该种授权服务下使用 海尔账号尽心登录；  
海尔账号与海尔优家账号单向互通，具备海尔优家 OAuth权限不代表具有海尔集团旗下业务权限；

- **海尔优家 第三方登录**
> 指使用第三方平台账号登录海尔优家平台，如微信、京东、淘宝等；

第三方社交账号支持QQ、微信、微博、豆瓣、人人网账号登录,若有其他第三方平台账号登录需求，可在线反馈;

- **海尔优家 开发者自有账号登录**
> 指开发者已有账户体系，且希望使用自有账户体系登录海尔优家平台；  

海尔优家提供平台间账户对接方案，具有标准OAuth方案、应用前方方案等，该种对接方式需要走线下申请流程，如有需求，可在开发者社区反馈，或通过海尔优家商务BD反馈；

### 功能介绍
**账号基础能力**  
1、	IOT平台账号注册：使用此接口用户可以使用手机或邮箱注册IOT账号，并调用验证码接口获取验证码，进行注册激活  
2、	IOT平台账号登录与退出，进行登录验证获取系统创建的安全令牌（accessToken），系统校验accessToken进行用户退出登录。  
3、	IOT账号验证码申请与验证，使用此接口可以申请和验证手机或邮箱的验证码保证注册、登录的安全性。  

**账号信息相关能力**  
1、	查询IOT平台账号信息，请求获取用户信息（包括id、loginName、email、mobile等用户属性）。
2、	修改IOT平台账号信息，用户主动修改其应用属性信息、用户基础属性等，需要进行权限认证。  

**账号体系关联能力**  
1、	第三方社交账号登录，支持QQ、微信、微博、豆瓣、人人网账号登录。
2、	开发者的自有账号登录，在U+IOT平台生成对应的暗账号并以U+账号身份进行用户授权登录到U+平台，开发者可建立其独立的开发者账号体系。


## 接口清单
### 海尔优家 账号  
> API接口总览

| API名称        | 作用          | 是否开放  | 特别说明|
| ------------- |:-------------:|:-----:|:-------------:|
| 账号注册     | 使用手机号或邮箱注册海尔优家平台账号 | 是| 无|

#### 账号注册
> 使用手机号或邮箱注册海尔优家平台账号

##### 1、接口定义

?> **接入地 址：**  `/uam/v1/   `  
 **HTTP Method：** POST

**输入参数**  

| 参数名        | 类型          | 位置  | 必填|说明|
| ------------- |:-------------:|:-----:|:-------------:|
| name     | String | Body| 必填|用户名称|

**输出参数**  

|   名称      |     类型      | 位置  |必填 |说明|
| ------------- |:----------:|:-----:|:--------:|:---------:|
|    |    |     |     |     |

##### 2、请求样例  

**用户请求**
```java  
Header：
appId: MB-FRIDGEGENE1-0000
appVersion: 99.99.99.99990
clientId: 123
sequenceId: 2014022801010
accessToken: TGT1ANW5WCQ2SXRD2DGIYRRAVLOMS0
sign: e5bd9aefd68c16a9d441a636081f11ceaed51ff58ec608e5d90048f975927e7f
timestamp: 1491014447260 
language: zh-cn
timezone: +8
appKey: 6cdd4658b8e7dcedf287823b94eb6ff9
Content-Encoding: utf-8
Content-type: application/json
Body
{
    "aliasName": "s"
}

```  

**请求应答**

```java
{
    "retCode": "00000",
    "retInfo": "成功!"
}

```

##### 3、错误码  
> A00001、B00001、G20202、A00004、B00001、D00006

### 海尔优家 OAuth

### 海尔优家 第三方登录

### 海尔优家 开发者自有账号登录

## 使用方式

### 开通流程  
![开通流程][account_liucheng]

### 应用场景
**账号管理**  
开发者没有账户系统，可集成U+账号的相关服务。  

**第三方登录**  
通过主流的第三方平台，一键进行登录。  

**开发者账号**  
开发者有自己的账户系统，通过云云对接互联方式接入U+账户服务。  


## 文档资料
[UWS 账户服务][account_document_url]

## 常见问题

[^-^]:文本连接注释
[account_document_url]:#

[^-^]:常用图片注释
[account_type]:_media/_account/account_type.png
[account_liucheng]:_media/_account/account_liucheng.png


