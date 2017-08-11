集まれる時に集まってもくもくとKotlinのコントリビュートを行う会です。

[Slack](https://mokmok-kontribute.slack.com)

## トラブルシューティング
* [Unresolved ReferenceなどでビルドできないときはKotlinプラグインを最新のバージョンにする](https://github.com/JetBrains/kotlin#-installing-the-latest-kotlin-plugin)
* 同じくUnresolved ReferenceなどでビルドできないときはIntelliJ IDEAでUpdate-Dist-Runを行う![](https://user-images.githubusercontent.com/1386930/29066189-6ec53ab8-7c69-11e7-93f1-834c4f64df55.png)
* Kotlinのプロジェクトが読み込めない時はAndroid Supportプラグインを無効にするとなぜか読み込める
  * エラー内容：Cannot Load Project:com.intellij.ide.plugins.PluginManager$StartupAbortedException:Fatal error initializing plugin org.jetbrains.kotlin
* [Generate Testがうまく動かないときはJDKのearly access版かpatched jdkを使う](https://youtrack.jetbrains.com/issue/IDEA-170117#comment=27-2065491)
  * File > Project Structure > SDKsに追加したJDKを追加して、Edit Configurationsを開き、JREを先ほどのJDKにしてビルドすればエラーでなくなる。
* [Antのメモリを大きくしないとビルドできないことがあるらしい](http://shiraji.github.io/blog/2016/07/14/how-to-kontribute/)


## 便利なリンク集
* [JetBrains/kotlinの開発環境の作り方](https://github.com/JetBrains/kotlin#build-environment-requirements)
* [Up For Grabsで絞り込んだIssueリスト](https://youtrack.jetbrains.com/oauth?state=%2Fissues%2FKT%3Fq%3Dtag:%2520%257BUp%2520For%2520Grabs%257D%2520%2523Unresolved%2520sort%2520by:%2520created%2520desc%2520)
   * ここにあるIssueは解決したプルリクエストを送ることで、コントリビュートすることができます。
* [Kotlin公式Slackのkontributorsチャンネル](https://kotlinlang.slack.com/messages/C0BUHC9HD/)
* [Shiraji's Blog/How to Kontribute](http://shiraji.github.io/blog/2016/07/14/how-to-kontribute/)  
   * 日本のKontributeされている方のブログ記事です。最高です。

## 新機能追加

Kotlinで頻出の新機能作成はIntention/Inspection/Quickfixに関するものです。Intention/Inspection/Quickfixの違いは実装前に確認しておくと良いです。どれを実装すれば良いのかわからない場合、SlackやそのIssueで聞いてしまうのも手です。

それぞれの機能追加の場合、以下のファイルの追加・変更が必要になります。(Xxxはそれぞれの機能の名前です。xxxはlowerCamelCaseということです。)

### Intention

* idea/src/org/jetbrains/kotlin/idea/intentions/XxxIntention.ktを追加
* idea/src/META-INF/plugin.xmlにintentionActionタグを追加
* idea/resources/intentionDescriptions/XxxIntention/description.htmlにIntentionの説明を追加
* idea/resources/intentionDescriptions/XxxIntention/before.kt.templateとidea/resources/intentionDescriptions/XxxIntention/after.kt.templateを追加
* idea/testData/intentions/xxxにテストデータを作成

### Inspection

* idea/src/org/jetbrains/kotlin/idea/inspections/にXxxInspection.ktを追加
* idea/src/META-INF/plugin.xmlにlocalInspectionのタグを追加
* idea/resources/inspectionDescriptions/Xxx.htmlのInspectionの説明を追加
* idea/testData/inspectionsLocal/xxxにテストデータを作成(inspectionsLocalが2017年8月現在最新のテスト方法です。)

### Quickfix

* idea/src/org/jetbrains/kotlin/idea/quickfix/XxxFix.ktを作成する
* idea/src/org/jetbrains/kotlin/idea/quickfix/QuickFixRegistrar.ktの対象のエラーにregisterする
* idea/testData/quickfix/xxxにテストデータを作成