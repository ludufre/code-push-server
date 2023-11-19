# ARCHIVED

## Better solution: https://github.com/Cap-go/capgo/




# CodePush Server [source](https://github.com/lisong/code-push-server)

[![NPM](https://nodei.co/npm/code-push-server.svg?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/code-push-server/)

[![NPM Version](https://img.shields.io/npm/v/code-push-server.svg)](https://npmjs.org/package/code-push-server)
[![Node.js Version](https://img.shields.io/node/v/code-push-server.svg)](https://nodejs.org/en/download/)
[![Linux Status](https://img.shields.io/travis/lisong/code-push-server/master.svg?label=linux)](https://travis-ci.org/lisong/code-push-server)
[![Windows Status](https://img.shields.io/appveyor/ci/lisong/code-push-server/master.svg?label=windows)](https://ci.appveyor.com/project/lisong/code-push-server)
[![Coverage Status](https://img.shields.io/coveralls/lisong/code-push-server/master.svg)](https://coveralls.io/github/lisong/code-push-server)
[![Dependency Status](https://img.shields.io/david/lisong/code-push-server.svg)](https://david-dm.org/lisong/code-push-server)
[![Known Vulnerabilities](https://snyk.io/test/npm/code-push-server/badge.svg)](https://snyk.io/test/npm/code-push-server)
[![Licenses](https://img.shields.io/npm/l/code-push-server.svg)](https://spdx.org/licenses/MIT)

CodePush Server is a CodePush progam server! microsoft CodePush cloud is slow in China, we can use this to build our's. I use [qiniu](http://www.qiniu.com/) to store the files, because it's simple and quick! Or you can use [local/s3/oss/tencentcloud] storage, just modify config.js file, it's simple configure.

## Support Storage mode

-   local _storage bundle file in local machine_
-   qiniu _storage bundle file in [qiniu](http://www.qiniu.com/)_
-   s3 _storage bundle file in [aws](https://aws.amazon.com/)_
-   oss _storage bundle file in [aliyun](https://www.aliyun.com/product/oss)_
-   tencentcloud _storage bundle file in [tencentcloud](https://cloud.tencent.com/product/cos)_

## qq 交流群

-   QQ 群: 628921445
-   QQ 群: 535491067

## 正确使用 code-push 热更新

-   苹果 App 允许使用热更新[Apple's developer agreement](https://developer.apple.com/programs/ios/information/iOS_Program_Information_4_3_15.pdf), 为了不影响用户体验，规定必须使用静默更新。 Google Play 不能使用静默更新，必须弹框告知用户 App 有更新。中国的 android 市场必须采用静默更新（如果弹框提示，App 会被“请上传最新版本的二进制应用包”原因驳回）。
-   react-native 不同平台 bundle 包不一样，在使用 code-push-server 的时候必须创建不同的应用来区分(eg. CodePushDemo-ios 和 CodePushDemo-android)
-   react-native-code-push 只更新资源文件,不会更新 java 和 Objective C，所以 npm 升级依赖包版本的时候，如果依赖包使用的本地化实现, 这时候必须更改应用版本号(ios 修改 Info.plist 中的 CFBundleShortVersionString, android 修改 build.gradle 中的 versionName), 然后重新编译 app 发布到应用商店。
-   推荐使用 code-push release-react 命令发布应用，该命令合并了打包和发布命令(eg. code-push release-react CodePushDemo-ios ios -d Production)
-   每次向 App Store 提交新的版本时，也应该基于该提交版本同时向 code-push-server 发布一个初始版本。(因为后面每次向 code-push-server 发布版本时，code-puse-server 都会和初始版本比较，生成补丁版本)

### shell login

```shell
$ code-push login http://api.code-push.com #登录
```

### [web](http://www.code-push.com)

访问：http://www.code-push.com

### client eg.

[ReactNative CodePushDemo](https://github.com/lisong/code-push-demo-app)

[Cordova CodePushDemo](https://github.com/lisong/code-push-cordova-demo-app)

## HOW TO INSTALL code-push-server

-   [docker](https://github.com/lisong/code-push-server/blob/master/docker/README.md) (recommend)
-   [manual operation](https://github.com/lisong/code-push-server/blob/master/docs/README.md)

## DEFAULT ACCOUNT AND PASSWORD

-   account: `admin`
-   password: `123456`

## HOW TO USE

-   [normal](https://github.com/lisong/code-push-server/blob/master/docs/react-native-code-push.md)
-   [react-native-code-push](https://github.com/Microsoft/react-native-code-push)
-   [code-push](https://github.com/Microsoft/code-push)

## ISSUES

[code-push-server normal solution](https://github.com/lisong/code-push-server/issues/135)

[An unknown error occurred](https://github.com/lisong/code-push-server/issues?utf8=%E2%9C%93&q=unknown)

[modify password](https://github.com/lisong/code-push-server/issues/43)

# UPDATE TIME LINE

-   targetBinaryVersion support
    -   `*`
    -   `1.2.3`
    -   `1.2`/`1.2.*`
    -   `1.2.3 - 1.2.7`
    -   `>=1.2.3 <1.2.7`
    -   `~1.2.3`
    -   `^1.2.3`

## Advance Feature

> use google diff-match-patch calculate text file diff patch

-   support iOS and Android
-   use `"react-native-code-push": "git+https://git@github.com/lisong/react-native-code-push.git"` instead `"react-native-code-push": "x.x.x"` in `package.json`
-   change `apps`.`is_use_diff_text` to `1` in mysql codepush database

## License

MIT License [read](https://github.com/lisong/code-push-server/blob/master/LICENSE)
