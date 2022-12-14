## 升级Android jpush 版本
+ ：升级 Android JPush 4.7.0
# 为了和厂商sdk版本保持一致，此处fork后在项目中处理厂商sdk
```
    // 接入华为厂商
    implementation 'com.huawei.hms:push:6.3.0.304'
    implementation 'cn.jiguang.sdk.plugin:huawei:4.7.0'
    // 接入魅族厂商
    implementation 'cn.jiguang.sdk.plugin:meizu:4.7.0'
    // 接入 VIVO 厂商
    implementation 'cn.jiguang.sdk.plugin:vivo:4.7.0'
    // 接入小米厂商
    implementation 'cn.jiguang.sdk.plugin:xiaomi:4.7.0'
    // 接入 OPPO 厂商
    implementation 'cn.jiguang.sdk.plugin:oppo:4.7.0'

```

[![QQ Group](https://img.shields.io/badge/QQ%20Group-862401307-red.svg)]()
# JPush Flutter Plugin
> flutter 2.0 请切换至 dev-2.x 分支。
### 安装

在工程 pubspec.yaml 中加入 dependencies

```
  
//github  集成
dependencies:
  jpush_flutter:
    git:
      url: git://github.com/jpush/jpush-flutter-plugin.git
      ref: master
      
// pub 集成
dependencies:
  jpush_flutter: 2.3.2
```

### 配置

##### Android:

在 `/android/app/build.gradle` 中添加下列代码：

```groovy
android: {
  ....
  defaultConfig {
    applicationId "替换成自己应用 ID"
    ...
    ndk {
	//选择要添加的对应 cpu 类型的 .so 库。
	abiFilters 'armeabi', 'armeabi-v7a', 'x86', 'x86_64', 'mips', 'mips64', 'arm64-v8a',        
    }

    manifestPlaceholders = [
        JPUSH_PKGNAME : applicationId,
        JPUSH_APPKEY : "appkey", // NOTE: JPush 上注册的包名对应的 Appkey.
        JPUSH_CHANNEL : "developer-default", //暂时填写默认值即可.
    ]
  }    

##### iOS:

- 在 xcode8 之后需要点开推送选项： TARGETS -> Capabilities -> Push Notification 设为 on 状态

### 使用

```dart
import 'package:jpush_flutter/jpush_flutter.dart';
```

### APIs

**注意** : 需要先调用 JPush.setup 来初始化插件，才能保证其他功能正常工作。

 [参考](./documents/APIs.md)

