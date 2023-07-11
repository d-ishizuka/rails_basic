# rails_basic

## 目的
- FrontendとBackendが分離されたアプリケーションしか触ってこなかった結果、RailsのView周りを含めた設定が怪しい...
- Ursmさんに聞いたところ、何にも見なくても普通に全部設定できるという話だったので修行する

## 概要
- 一旦、Railsガイドの「[Railsをはじめよう](https://railsguides.jp/getting_started.html)」を何も見ずに書けるようにしておく

## 詳細な内容
- Railsで「Hello」と表示する
  - 一旦、article/indexとrootで表示してみる
- Articleモデルを生成する
  - title:string, body:text
  - migration
- 一旦、コンソールから２件くらいデータを作成しておく
- Articleのタイトル一覧を表示する
  - index
- Articleをtitleとbodyを１件表示する
  - show
- resourcesを使ったルーティングに変更
  - path一覧を表示して確認する
- Articleのタイトル一覧から、個別のshowリンクに飛べるように修正する
  - この時はヘルパーを使わず、aタグで実装すること
  - その後、link_toヘルパーメソッドを使って遷移できるようにする
- Createできるようにする
  - 成功したら、article/#{@article.id}に遷移できるように、redirect_toヘルパーメソッドを使って実装する
  - 失敗したら、unprocessable_entityでエラーを返す
  - viewはform_withヘルパーメソッドを使って実装する
    - HTMLにどのように変換されるかも確認する
  - strong paramsを設定する
- Articleモデルにバリデーションを入れる
  - 条件は、titleもbodyも必ず存在すること、またbodyは１０文字以上とすること
  - バリデーションに引っかかった場合、viewファイルでエラーが表示されるようにする(full_messages_for ヘルパーメソッドを使用する)
  - 
