---
layout: default
---

<a id="List" name="List"></a>
# 項目一覧

<!-- TOC -->
- Choreonoid インストール手順（for Windows10）
    - [事前準備](cnoid4win.html#advancePreparation "事前準備")
        - [必要なツールのインストール](cnoid4win.html#toolInstallation "必要なツールのインストール")
            - [Visual C++](cnoid4win.html#visualc++ "Visual C++")
            - [CMake](cnoid4win.html#installCmake "CMake")
        - [必要なライブラリのインストール](cnoid4win.html#libInstallation "必要なライブラリのインストール")
            - [Boost](cnoid4win.html#installBoost "Boost")
            - [Qt](cnoid4win.html#installQt "Qt")
    - [Visual StudioによるChoreonoidのソース取得](cnoid4win.html#getSource4Vs "Choreonoidソース取得")
    - [CMakeによるビルド設定](cnoid4win.html#setBuild "CMakeによるビルド設定")
    - [Visual Studioによるソリューションの読み込み](cnoid4win.html#readSolution "Visual Studioによるソリューションの読み込み")
    - [動作確認](cnoid4win.html#operatioCheck "動作確認")
<!-- /TOC -->

<a id="advancePreparation" name="advancePreparation"></a>
## 事前準備
<a id="toolInstallation" name="toolInstallation"></a>
### 必要なツールのインストール
<a id="visualc++" name="visualc++"></a>
#### Visual C++
<details>
<summary>Visual C++インストール手順</summary><div>

1. Visual C++の対応バージョンは、2015, 2017, 2019となっており、無料版のVisual Studio Communityを以下URLよりダウンロードします。<br>
<a href="https://visualstudio.microsoft.com/ja/free-developer-offers/">https://visualstudio.microsoft.com/ja/free-developer-offers/</a><br><br>

2. ウェブブラウザにて上記URLにアクセスし、Visual Studio Communityの「無料ダウンロード」ボタンを押下します。<br>
<img src="img/cnoid/vscommunity.png" alt="Visual Studio Community無料ダウンロード" title="Visual Studio Community無料ダウンロード"><br><br>

3. 自動で"vs_community_….exe"がダウンロードします。<br>
※以下に表示されている「開始するためのヒントとリソース」は何も入力せずに「×」で閉じてください。<br>
<img src="img/cnoid/downloadVsCommunity.png" alt="Visual Studioの自動ダウンロード" title="Visual Studioの自動ダウンロード"><br>
<img src="img/cnoid/vsStartDialog.png" alt="開始するためのヒントとリソース" title="開始するためのヒントとリソース"><br><br>

4. ダウンロードフォルダより"vs_community_….exe"ファイルをダブルクリックします。<br>
<img src="img/cnoid/vsDownloadFolder.png" alt="Visual Studioダウンロードフォルダ" title="Visual Studioダウンロードフォルダ"><br><br>

5. 「続行」ボタンを押下します。<br>
<img src="img/cnoid/vsInstaller.png" alt="Visual Studioのインストール" title="Visual Studioのインストール"><br><br>

6. 次の画面に遷移するまで待機します。<br>
<img src="img/cnoid/checkVsInstall.png" alt="インストールを構成するための設定" title="インストールを構成するための設定"><br><br>

7. 「C++によるデスクトップ環境」にチェックを入れ、「インストール」ボタン押下します。<br>
<img src="img/cnoid/selectC++.png" alt="C++によるデスクトップ環境の選択" title="C++によるデスクトップ環境の選択"><br><br>

8. インストールが完了するまで待機します。<br>
<img src="img/cnoid/installVs.png" alt="Visual Studioをインストール中" title="Visual Studioをインストール中"><br><br>

9. 再起動を求められるので、「再起動」ボタンを押下します。<br>
<img src="img/cnoid/rebootVs.png" alt="再起動" title="再起動"><br><br>
</div>
</details>

<a id="installCmake" name="installCmake"></a>
#### CMake
<details>
<summary>CMakeのインストール手順</summary><div>

1. CMakeの最新バージョンは、3.18.0となっており、以下URLよりWindows版のインストーラをダウンロードします。<br>
<a href="https://cmake.org/download/">https://cmake.org/download/</a><br><br>

2. ウェブブラウザにて上記URLにアクセスし、Windows win64-x64 Installerの「cmake-3.18.0-rc4-win64-x64.msi」リンクを押下します。<br>
<img src="img/cnoid/cmakeDownloadSite.png" alt="Cmakeサイト" title="Cmakeサイト"><br><br>

3. 自動で”cmake-3.18.0-rc4-win64-x64.msi”がダウンロードされます。<br>
<img src="img/cnoid/cmakeAutoDownload.png" alt="Cmake自動ダウンロード" title="Cmake自動ダウンロード"><br><br>

4. ダウンロードフォルダより” cmake-3.18.0-rc4-win64-x64.msi”ファイルをダブルクリックします。<br>
<img src="img/cnoid/cmakeDownloadFolder.png" alt="Cmakeダウンロードフォルダ" title="Cmakeダウンロードフォルダ"><br><br>

5. 「Next」ボタンを押下します。<br>
<img src="img/cnoid/cmakeSetupWizard.png" alt="Cmakeセットアップウィザード" title="Cmakeセットアップウィザード"><br><br>

6. 「I accept the terms in the License Agreement」にチェックを入れます。<br>
<img src="img/cnoid/beforeCakeAccept.png" alt="Cmakeライセンスの承諾（チェック前）" title="Cmakeライセンスの承諾（チェック前）"><br><br>

7. 「Next」ボタンを押下します。<br>
<img src="img/cnoid/afterCakeAccept.png" alt="Cmakeライセンスの承諾（チェック後）" title="Cmakeライセンスの承諾（チェック後）"><br><br>

8. 「Add CMake to the system PATH for all users」を選択します。<br>
<img src="img/cnoid/beforeCmakePathAll.png" alt="Cmakeパス設定（選択前）" title="Cmakeパス設定（選択前）"><br><br>

9. 「Next」ボタンを押下します。<br>
<img src="img/cnoid/afterCmakePathAll.png" alt="Cmakeパス設定（選択後）" title="Cmakeパス設定（選択後）"><br><br>

10. フォルダパスを変更せずに、「Next」ボタンを押下します。<br>
<img src="img/cnoid/cmakeFolderPath.png" alt="Cmakeフォルダパス設定" title="Cmakeフォルダパス設定"><br><br>

11. 「Install」ボタンを押下します。<br>
<img src="img/cnoid/startInstallingCmake.png" alt="Cmakeのインストール開始" title="Cmakeのインストール開始"><br><br>

12. インストールが完了するまで待機します。<br>
<img src="img/cnoid/installingCmake.png" alt="Cmakeのインストール中" title="Cmakeのインストール中"><br><br>

13. インストールが完了したら、「Finish」ボタンを押下します。<br>
<img src="img/cnoid/finishInstallCmake.png" alt="Cmakeのインストール完了" title="Cmakeのインストール完了"><br><br>
</div>
</details>

<a id="libInstallation" name="libInstallation"></a>
### 必要なライブラリのインストール
<a id="installBoost" name="installBoost"></a>
#### Boost
<details>
<summary>Boostのインストール手順</summary><div>

1. Boostライブラリの最新版は、1.73.0となっており、を以下URLよりインストーラをダウンロードします。<br>
<a href="https://www.boost.org/users/download/">https://www.boost.org/users/download/</a><br><br>

2. ウェブブラウザにて上記URLにアクセスし、OTHER DOWNLOADSの「Prebuilt windows binaries.」リンクを押下します。<br>
<img src="img/cnoid/boostDownloadSite.png" alt="Boostサイト" title="Boostサイト"><br><br>

3. 「Download Latest Version」ボタンは押下しないでください。<br>
<img src="img/cnoid/notClickLatestVer.png" alt="Download Latest Version" title="Download Latest Version"><br><br>

4. 最新版の「1.73.0」フォルダを押下します。<br>
<img src="img/cnoid/clickFolder1-73-0.png" alt="最新版のフォルダ" title="最新版のフォルダ"><br><br>

5. 「boost_1_73_0-msvc-14.2-64.exe」リンクを押下します。<br>
<img src="img/cnoid/clickBoost1-73-0.png" alt="最新版のBoostダウンロード" title="最新版のBoostダウンロード"><br><br>

6. 自動で” boost_1_73_0-msvc-14.2-64.exe”がダウンロードされます。<br>
<img src="img/cnoid/boostAutoDownload.png" alt="Boost自動ダウンロード" title="Boost自動ダウンロード"><br><br>

7. ダウンロードフォルダにて” boost_1_73_0-msvc-14.2-64.exe”をダブルクリックします。<br>
<img src="img/cnoid/boostDownloadFolder.png" alt="Boostのダウンロードフォルダ" title="Boostのダウンロードフォルダ"><br><br>

8. 「詳細情報」を押下すると「実行」ボタンが表示されます。<br>
<img src="img/cnoid/installBoost.png" alt="Boostのインストーラの起動を許可" title="Boostのインストーラの起動を許可"><br><br>

9. 「実行」ボタンを押下します。<br>
<img src="img/cnoid/boostInstallationPermmition.png" alt="Boostのインストーラ起動" title="Boostのインストーラ起動"><br><br>

10. フォルダパスは変更せずに「Next」ボタンを押下します。<br>
<img src="img/cnoid/boostFolderPath.png" alt="Boostのフォルダパス" title="Boostのフォルダパス"><br><br>

11. インストールが完了するまで待機します。<br>
<img src="img/cnoid/installingBoost.png" alt="Boostのインストール中" title="Boostのインストール中"><br><br>

12. インストールが完了したら「Finish」ボタンを押下します。<br>
<img src="img/cnoid/finishBoostInstallation.png" alt="Boostのインストール完了" title="Boostのインストール完了"><br><br>
</div>
</details>

<a id="installQt" name="installQt"></a>
#### Qt
<details>
<summary>Qtのインストール手順</summary><div>

1. Qtの最新版は、5.13.0となっており、以下URLよりWindows版のQtのインストーラをダウンロードします。<br>
※最小要件：5.10以上<br>
<a href="https://www.qt.io/download">https://www.qt.io/download</a><br><br>

2. ウェブブラウザにて上記URLにアクセスします。<br>
<img src="img/cnoid/qtDownloadSite.png" alt="Qtサイト" title="Qtサイト"><br><br>

3. Downloads for open source usersの「Go open source」ボタンを押下します。<br>
<img src="img/cnoid/clickGoOss.png" alt="Go open sourceをクリック" title="Go open sourceをクリック"><br><br>

4. 「Download the Qt Online Installer」ボタンを押下します。<br>
<img src="img/cnoid/downloadQt.png" alt="Qtのダウンロード" title="Qtのダウンロード"><br><br>

5. 対象OSのインストーラが表示されます。<br>
※以下ではWindows OSのインストーラが表示されています。<br>
<img src="img/cnoid/displayQtInstaller.png" alt="対象OSのインストーラ" title="対象OSのインストーラ"><br><br>

6. 「Download」ボタンを押下します。<br>
<img src="img/cnoid/clickDownloadQt.png" alt="ダウンロードのクリック" title="ダウンロードのクリック"><br><br>

7. 自動で” qt-unified-windows-x86-3.2.3-online.exe”がダウンロードします。<br>
<img src="img/cnoid/qtAutoDownload.png" alt="Qt自動ダウンロード" title="Qt自動ダウンロード"><br><br>

8. ダウンロードフォルダにて” qt-unified-windows-x86-3.2.3-online.exe”をダブルクリックします。<br>
<img src="img/cnoid/qtDownlloadFolder.png" alt="Qtダウンロードフォルダ" title="Qtダウンロードフォルダ"><br><br>

9. 「Next」ボタンを押下します。<br>
<img src="img/cnoid/qtInstaller.png" alt="Qtのインストーラ" title="Qtのインストーラ"><br><br>

10. 必須項目を入力します。（アカウント登録が必須）<br>
<img src="img/cnoid/enterQtAccount.png" alt="Qtアカウントの入力" title="Qtアカウントの入力"><br><br>

11. 必須項目を入力後「Next」ボタンを押下します。<br>
【Qtアカウントを既に持っている方】<br>
LoginにEmail, Passwodを入力後、「I accept the service terms.」にチェックを入れ、「Next」ボタンを押下します。<br>
<br>
【Qtアカウントを持っていない方】<br>
Sign-upにEmail, Password※, Confirm Passwordを入力後、「I accept the service terms.」にチェックを入れ、「Next」ボタンを押下します。<br>
入力したメールアドレスにアカウント登録メールが届くので、リンクよりアカウントの登録を完了させます。<br>
アカウント登録完了後、再度「Next」ボタンを押下します。<br>
※パスワードは、7桁以上、大文字、小文字、数字、記号の4パターンの内最低3パターンを使用する必要があります。<br>
<img src="img/cnoid/enterQtAccountInfo.png" alt="Qtアカウント情報の入力" title="Qtアカウント情報の入力"><br><br>

12. 「I have read and approve the obligations of using Open Source Qt」にチェックを入れます。
<img src="img/cnoid/beforeCheckAcceptQtOss.png" alt="Open Source Qtの同意（チェック前）" title="Open Source Qtの同意（チェック前）"><br><br>

13. 「次へ」ボタンを押下します。<br>
<img src="img/cnoid/afterCheckAcceptQtOss.png" alt="Open Source Qtの同意（チェック後）" title="Open Source Qtの同意（チェック後）"><br><br>

14. 「次へ」ボタンを押下します。<br>
<img src="img/cnoid/setupQt.png" alt="Qt設定" title="Qt設定"><br><br>

15. 「Disable sending pseudonymous usage statistics in Qt Creator」を選択し、「次へ」ボタンを押下します。<br>
<img src="img/cnoid/disableSending.png" alt="送信の無効化" title="送信の無効化"><br><br>

16. インストールフォルダは変更せずに「次へ」ボタンを押下します。<br>
<img src="img/cnoid/qtFolerPath.png" alt="Qtフォルダパス" title="Qtフォルダパス"><br><br>

17. "Qt 5.15.0”の”MSVC 2019 64-bit"にチェックを入れ、「次へ」ボタンを押下します。<br>
<img src="img/cnoid/selectQtComponent.png" alt="コンポーネントの選択" title="コンポーネントの選択"><br><br>

18. 「I have read and agree to the terms contained in the license agreements」を選択します。<br>
<img src="img/cnoid/beforeSelectAcceptQt.png" alt="Qtライセンスの承諾（選択前）" title="Qtライセンスの承諾（選択前）"><br><br>

19. 「次へ」ボタンを押下します。<br>
<img src="img/cnoid/afterSelectAcceptQt.png" alt="Qtライセンスの承諾（選択後）" title="Qtライセンスの承諾（選択後）"><br><br>

20. "Qt"という名称の新しいフォルダを指定し「次へ」ボタンを押下します。<br>
<img src="img/cnoid/selectQtFolder.png" alt="Qtフォルダを選択" title="Qtフォルダを選択"><br><br>

21. 「インストール」ボタンを押下します。<br>
<img src="img/cnoid/startQtInstallation.png" alt="Qtのインストール開始" title="Qtのインストール開始"><br><br>

22. インストールが完了するまで待機します。<br>
<img src="img/cnoid/installingQt.png" alt="Qtのインストール中" title="Qtのインストール中"><br><br>

23. 「Launch Qt Creator」のチェックを外します。<br>
<img src="img/cnoid/uncheckLaunchQt.png" alt="Qtを起動しない" title="Qtを起動しない"><br><br>

24. 「完了」ボタンを押下します。<br>
<img src="img/cnoid/finishQtInstallation.png" alt="Qtのインストール完了" title="Qtのインストール完了"><br><br>
</div>
</details>

<a id="getSource4Vs" name="getSource4Vs"></a>
## Visual StudioによるChoreonoidのソース取得
<details>
<summary>Choreonoidのソース取得方法</summary><div>

1. Visual Studio 2019を起動後、「後で行う。」を押下します。<br>
<img src="img/cnoid/.png" alt="Visual Studio 2019の起動" title="Visual Studio 2019の起動"><br><br>

2. 開発設定を”Visual C++”に変更します。<br>
※配色のテーマの選択は任意で変更を行ってください。<br>
<img src="img/cnoid/.png" alt="開発設定" title="開発設定"><br><br>

3. 「Visual Studioの開始」ボタンを押下します。<br>
<img src="img/cnoid/.png" alt="Visual Studioの開始" title="Visual Studioの開始"><br><br>

4. 30日間の試用期間が終了している場合、「サインイン」ボタンを押下しMicrosoftアカウントでサインインします。<br>
※アカウントがない場合、「作成してください。」のリンクより作成を行ってください。<br>
<img src="img/cnoid/.png" alt="Visual Studio Communityのサインイン" title="Visual Studio Communityのサインイン"><br><br>

5. 「閉じる」ボタンを押下します。<br>
<img src="img/cnoid/.png" alt="サインイン後閉じる" title="サインイン後閉じる"><br><br>

6. 「コードなしで続行→」を押下します。<br>
<img src="img/cnoid/.png" alt="コードなしで続行" title="コードなしで続行"><br><br>

7. 「ソリューションエクスプローラー」が表示されているので、「チームエクスプローラー」を表示します。<br>
<img src="img/cnoid/.png" alt="ソリューションエクスプローラーの表示" title="ソリューションエクスプローラーの表示"><br><br>

8. 「メニュー」→「表示」→「チームエクスプローラー」を選択します。<br>
<img src="img/cnoid/.png" alt="チームエクスプローラーの表示" title="チームエクスプローラーの表示"><br><br>

9. 「コンセント」ボタンを押下します。<br>
<img src="img/cnoid/.png" alt="リポジトリの接続" title="リポジトリの接続"><br><br>

10. ローカルGitリポジトリの「クローン」を押下します。<br>
<img src="img/cnoid/.png" alt="Gitリポジトリのクローン" title="Gitリポジトリのクローン"><br><br>

11. Gitリポジトリを指定します。<br>
※Choreonoidリポジトリ：<a href="https://github.com/choreonoid/choreonoid.git">https://github.com/choreonoid/choreonoid.git</a><br>
<img src="img/cnoid/.png" alt="Gitリポジトリの指定" title="Gitリポジトリの指定"><br><br>

12. Choreonoidリポジトリをダウンロードするフォルダを指定し、「クローン」ボタンを押下します。<br>
※フォルダパス： C:\Users\ユーザ名\choreonoid<br>
<img src="img/cnoid/.png" alt="フォルダパスの指定" title="フォルダパスの指定"><br><br>

13. リポジトリを複製が完了するまで待機します。<br>
<img src="img/cnoid/.png" alt="リポジトリの複製中" title="リポジトリの複製中"><br><br>

14. リポジトリの複製が完了すると画像のメッセージが表示されます。<br>
<img src="img/cnoid/.png" alt="リポジトリの完了" title="リポジトリの完了"><br><br>

15. 「同期」ボタンを押下します。<br>
<img src="img/cnoid/.png" alt="リポジトリの同期" title="リポジトリの同期"><br><br>

16. 「プル」を押下します。<br>
<img src="img/cnoid/.png" alt="リポジトリのプル" title="リポジトリのプル"><br><br>

17. リポジトリが最新状態の場合、画像のメッセージが表示されます。<br>
<img src="img/cnoid/.png" alt="リポジトリの最新状態" title="リポジトリの最新状態"><br><br>
</div>
</details>

<a id="setBuild" name="setBuild"></a>
## CMakeによるビルド設定
<details>
<summary>ビルド設定手順</summary><div>

1. スタートメニューから「CMake」→「CMake (cmake-gui)」を押下します。<br>
<img src="img/cnoid/.png" alt="CMakeの起動" title="CMakeの起動"><br><br>

2. 「Where is the source code:」にChoreonoidのダウンロードフォルダを指定します。<br>
「Where to build the binaries:」にChoreonoidのダウンロードフォルダ直下のbuildフォルダを指定します。<br>
※Where is the source code：C:\Users\ユーザ名\choreonoid<br>
  Where to build the binaries：C:\Users\ユーザ名\choreonoid\build<br>
<img src="img/cnoid/.png" alt="Choreonoidフォルダパスの指定" title="Choreonoidフォルダパスの指定"><br><br>

3. 「Configure」ボタンを押下します。<br>
<img src="img/cnoid/.png" alt="Configureの実行" title="Configureの実行"><br><br>

4. 「Yes」ボタンを押下します。<br>
<img src="img/cnoid/.png" alt="フォルダ作成ダイアログ" title="フォルダ作成ダイアログ"><br><br>

5. 「Specify the generator for this project」に”Visual Studio 16 2019”を選択し、「Finish」ボタンを押下します。<br>
<img src="img/cnoid/.png" alt="Visual Studioのバージョン選択" title="Visual Studioのバージョン選択"><br><br>

6. "Configuring done"のメッセージが表示されれば正常終了です。<br>
<img src="img/cnoid/.png" alt="Configureの正常終了" title="Configureの正常終了"><br><br>

7. "CMAKE_INSTALL_PREFIX"を変更します。<br>
※CMAKE_INSTALL_PREFIX：C:\Users\ユーザ名\choreonoid\program<br>
<img src="img/cnoid/.png" alt="CMAKE_INSTALL_PREFIXの変更" title="CMAKE_INSTALL_PREFIXの変更"><br><br>

8. 「Configure」ボタンを押下します。<br>
<img src="img/cnoid/.png" alt="再度Configureの実行" title="再度Configureの実行"><br><br>

9. 「Generate」ボタンを押下します。<br>
<img src="img/cnoid/.png" alt="Generateの実行" title="Generateの実行"><br><br>

10. "Generating done"のメッセージが表示されれば正常終了です。<br>
<img src="img/cnoid/.png" alt="Generateの正常終了" title="Generateの正常終了"><br><br>
</div>
</details>

<a id="readSolution" name="readSolution"></a>
## Visual Studioによるソリューションの読み込み
<details>
<summary>ソリューションの読み込み方法</summary><div>

【既にVisual Studioを起動している場合】<br>
1. 「メニュー」→「ファイル」→「開く」→「プロジェクト/ソリューション」を押下します。<br>
<img src="img/cnoid/.png" alt="プロジェクト/ソリューションの選択" title="プロジェクト/ソリューションの選択"><br><br>

2. ビルドフォルダ内の"Choreonoid.sln"ファイルを選択し「開く」ボタンを押下します。<br>
<img src="img/cnoid/.png" alt="Choreonoid.slnを開く" title="Choreonoid.slnを開く"><br><br>

【Visual Studioを起動していない場合】<br>
3. ビルドフォルダに移動し、"Choreonoid.sln"ファイルをダブルクリックします。<br>
<img src="img/cnoid/.png" alt="Choreonoid.slnの実行" title="Choreonoid.slnの実行"><br><br>

4. "Choreonoid.sln"を起動すると、ソリューションエクスプローラーにプロジェクト一覧が表示されます。<br>
<img src="img/cnoid/.png" alt="Choreonoid.slnの表示" title="Choreonoid.slnの表示"><br><br>

5. ソリューション構成：Release、ソリューションプラットフォーム：x64に変更します。<br>
<img src="img/cnoid/.png" alt="ビルド設定" title="ビルド設定"><br><br>

6. 「メニュー」→「ビルド」→「ソリューションのビルド」を押下します。<br>
<img src="img/cnoid/.png" alt="ビルドの実行" title="ビルドの実行"><br><br>

7. 出力ビューに表示されているビルド結果の”失敗”が0なら正常終了です。<br>
<img src="img/cnoid/.png" alt="ビルドの正常終了" title="ビルドのの正常終了"><br><br>

8. ソリューションエクスプローラーの"INSTALL"を選択します。<br>
<img src="img/cnoid/.png" alt="Choreonoidのインストール" title="Choreonoidのインストール"><br><br>

9. 右クリックし「ビルド」を選択します。<br>
<img src="img/cnoid/.png" alt="INSTALLのビルド" title="INSTALLのビルド"><br><br>

10. 出力ビューに表示されているビルド結果の”失敗”が0なら正常終了です。<br>
<img src="img/cnoid/.png" alt="INSTALLの正常終了" title="INSTALLの正常終了"><br><br>
</div>
</details>

<a id="operatioCheck" name="operatioCheck"></a>
## 動作確認
<details>
<summary>ビルド設定(for CMake)</summary><div>

1. インストールフォルダの"bin"フォルダにある"choreonoid.exe"ファイルをダブルクリックします。<br>
※インストールフォルダ：C:\Users\ユーザ名\choreonoid\program\<br>
<img src="img/cnoid/.png" alt="Choreonoidインストールフォルダ" title="Choreonoidインストールフォルダ"><br><br>

2. 画像のようなChoreonoid画面が起動します。<br>
<img src="img/cnoid/.png" alt="Choreonoid起動画面" title="Choreonoid起動画面"><br><br>

3. 「メニュー」→「プロジェクトの読み込み」を押下します。<br>
<img src="img/cnoid/.png" alt="プロジェクトの読み込み" title="プロジェクトの読み込み"><br><br>

4. "Tank.cnoid"を選択し「読み込み」ボタンを押下します。<br>
<img src="img/cnoid/.png" alt="Tank.cnoidの読み込み" title="Tank.cnoidの読み込み"><br><br>

5. 「シミュレーション開始」ボタンを押下します。<br>
<img src="img/cnoid/.png" alt="シミュレーションの開始" title="シミュレーションの開始"><br><br>

6. 仮想ジョイスティックビューをクリックしアクティブにした後、キーボードのE(前進), S(左旋回), F(右旋回), D(後退)等を押してTankが動作することを確認してください。<br>
※キーを押している間のみ動作し続けます。<br>
<img src="img/cnoid/.png" alt="仮想ジョイスティック操作" title="仮想ジョイスティック操作"><br><br>
</div>
</details>

