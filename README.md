# CAT TIME ATTACK Web版 v2

## v2の変更

- URLを開いた利用者はSupabase匿名認証を使用
- メールアドレス、電話番号、パスワード登録なし
- 公開参加者番号を登録順に発行
  - 1人目 = No.1
  - 2人目 = No.2
  - 30人目 = No.30
- 同じニックネームを複数人が使用可能
- 同じ利用者はランキングに1件だけ
- 再挑戦で自己ベストだけ更新
- 公開ランキングには以下だけ表示
  - ニックネーム
  - No.○
  - 自己ベスト
- Supabase内部の匿名 user_id はランキングへ返さない

## 大事なプライバシー仕様

公開する No.○ は、ゲーム専用DBのカウンターで作る番号です。
Apple ID、iPhoneのシリアル番号、IMEI、電話番号などから作りません。

一方、同じブラウザからの再挑戦を判定するため、
Supabase Authの匿名セッションを内部的に使用します。

ブラウザデータを削除したり、別端末へ移ると、
同じ匿名ユーザーとして認識できなくなり、
新しいNo.が発行される場合があります。

## Supabase側で最初にすること

1. Authentication を開く
2. Anonymous Sign-Ins（匿名サインイン）を有効にする
3. SQL Editorを開く
4. supabase_v2.sql を全部貼る
5. Run

## config.js

Project URL と Publishable key のみ入れてください。

Secret key / service_role key は絶対にGitHubへ入れないでください。

## GitHub

このZIPを解凍し、リポジトリ直下にすべてアップロードします。

cats/ フォルダには猫画像88枚がすでに入っています。


## 軽量版について

猫画像88枚は、スマホ/Web表示用にWebPへ軽量化済みです。
元の高解像度PNGをGitHubへアップロードする必要はありません。

GitHubにはZIPそのものではなく、ZIPを解凍した「中身」をアップロードしてください。
