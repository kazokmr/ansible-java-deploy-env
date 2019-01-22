# JavaのWebアプリ動作環境とCI/CDを実行するJenkinsサーバーを構築するAnsible-Playbookです。

以下の3つの環境を作るためのPlaybookが作成できます。

### Jenkins

`ansible-playbook -i /ansible/jenkins /ansible/jenkins-site.yml`

- Jenkinsの最新版をインストールします。  
- Jenkins実行用JREにOpenJDK 8 JREをインストールしています。  
- ソースコードのビルド用にはOpenJDK 11をインストールしています。(/usr/local/jdk-xx.x.x)

### JVM(OpenJDK)
`ansible-playbook -i /ansible/jvm /ansible/jvm-site.yml`

- jarファイル実行用の環境です。(主にSpring-bootで生成したArtifactsを実行することを想定しています。)
- OpenJDK 11をインストールします。
- javaコマンドが実行できるようにパスを通しています。


### Tomcat
`ansible-playbook -i /ansible/tomcat /ansible/tomcat-site.yml`

- Tomcatをインストールして、サービスを実行します。
- Tomcat実行用のJDKは、OpenJDK 11を使います。
