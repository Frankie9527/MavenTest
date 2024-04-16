# 发布android projet（kotlin 版本）作为库
## java lib 添加 如下
id("org.jetbrains.kotlin.android")  ，因为当前android 基本都是kotlin，最好添加此语句到 build.gradle.kts 配置文件中。否则你的架包如果含有kotlin 则会有引用失败提示

- Unresolved reference: TestKt

## 添加kotlin 包
-  implementation("androidx.core:core-ktx:1.10.1")
-   kotlinOptions {
        jvmTarget = "1.8"
    }

如果你的jar 里面有kotlin 代码，则一定要添加这个包。否则报如下错误

Inconsistent JVM-target compatibility detected for tasks 'compileDebugJavaWithJavac' (1.8) and 'compileDebugKotlin' (17).

### doc
https://developer.android.com/build/publish-library

## 添加 jitpack.yml
jdk:
  - openjdk17

开始添加到是 jdk11 ，然后报错 ，log 如下
https://jitpack.io/com/github/Frankie9527/MavenTest/0.7/build.log

## 发布版本
- 在自己项目中点击relsease，填写内容并发布
此项目发布版本链接为：https://github.com/frankie9527/MavenTest/releases/new

- 在 https://www.jitpack.io/ 中填入自己的项目链接则可以查到自己是否发布成功
