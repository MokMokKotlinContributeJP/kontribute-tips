集まれる時に集まってもくもくとKotlinのコントリビュートを行う会です。

[Slack](https://mokmok-kontribute.slack.com)

## トラブルシューティング
* [kotlinプラグインを最新のバージョンにした？](https://github.com/JetBrains/kotlin#-installing-the-latest-kotlin-plugin)
* Kotlinのプロジェクトが読み込めない時はAndroid Supportプラグインを無効にするとなぜか読み込める
* IntelliJ IDEAでUpdate-Dist-Runを行う![](https://user-images.githubusercontent.com/1386930/29066189-6ec53ab8-7c69-11e7-93f1-834c4f64df55.png)
* [Generate Testがうまく動かないときはJDKのearly access版かpatched jdkを使う](https://youtrack.jetbrains.com/issue/IDEA-170117#comment=27-2065491)
* [Antのメモリを大きくしないとビルドできないことがあるらしい](http://shiraji.github.io/blog/2016/07/14/how-to-kontribute/)
* kotlinのプラグインをインストールして再起動した後にプロジェクトを開こうとすると以下のエラーが出ることがある
 ```
Cannot Load Project:
com.intellij.ide.plugins.PluginManager$StartupAbortedException:
Fatal error initializing plugin org.jetbrains.kotlin
 ```
Android Supportプラグインを外すとうまくいく。なぜか。

## 便利なリンク集
* [JetBrains/kotlinの開発環境の作り方](https://github.com/JetBrains/kotlin#build-environment-requirements)
* [Up For Grabsで絞り込んだIssueリスト](https://youtrack.jetbrains.com/oauth?state=%2Fissues%2FKT%3Fq%3Dtag:%2520%257BUp%2520For%2520Grabs%257D%2520%2523Unresolved%2520sort%2520by:%2520created%2520desc%2520)
   * ここにあるIssueは解決したプルリクエストを送ることで、コントリビュートすることができます。
* [Kotlin公式Slackのkontributorsチャンネル](https://kotlinlang.slack.com/messages/C0BUHC9HD/)
* [Shiraji's Blog/How to Kontribute](http://shiraji.github.io/blog/2016/07/14/how-to-kontribute/)  
   * 日本のKontributeされている方のブログ記事です。自分はこれを見て始めました。最高です。

