# :memo: 正規表現

## 1. 基本

- **デリミタ** 
・・・正規表現をはさむ。正規表現の先頭と末尾につける。デフォルト「/」。

- **修飾子**  
・・・「/正規表現/*修飾子*」の形式。
  - **g修飾子**  
  ・・・可能な限り多く検出する。

  - **s修飾子**  
  ・・・改行をワイルドカードの対象に含める。

  - **i修飾子**  
  ・・・大文字と小文字の区別をなくす

  - **m修飾子**  
  ・・・複数行を対象にする。

- **メタ文字**  
  - **「.」 - ワイルドカード**  
  ・・・一文字分を何でもカバーする。  
  　※正規表現はスペースも対象にする。

  - **「[]」 - 角括弧**  
  ・・・一文字分の選択肢を設定する。

  - **「-」 - ハイフン**  
  ・・・角括弧の中で文字数の範囲を指定する。

  - **「^」 - キャレット**  
  ・・・角括弧の中で、直後の対象範囲を逆転させる。  
  　※角括弧の先頭で使用する必要がある。  
　角括弧の外では、行頭であることを指定する。

  - **「$」 - ドルマーク**  
  ・・・行末であることを指定する。

  - **「\」 - バックスラッシュ**  
  ・・・メタ文字の「*エスケープ処理*」。
    - 「**\n**」・・・改行
    - 「**\t**」・・・タブ
    - 「**\d**」・・・[0-9]と同じ。0から9までの数字を表す。
    - 「**\D**」・・・[^0-9]と同じ。数字以外すべてを表す。
    - 「**\w**」・・・[a-zA-Z0-9]と同じ。アルファベットと数字すべてを表す。
    - 「**\W**」・・・[^a-zA-Z0-9]と同じ。上記以外すべて。
    - 「**\s**」・・・[ \f\n\r\t]と同じ。スペース、改ページ、改行、タブを表す。
    - 「**\S**」・・・[^ \f\n\r\t]と同じ。上記以外すべてを表す。
    - 「**\b**」・・・スペースや改行などの区切りを表す。
    - 「**\B**」・・・上記以外すべての区切りを表す。

## 2. 数量詞

・・・パターンの直後に記述する。

- **「*」 - アスタリスク**  
・・・0回以上の繰り返し

- **「+」 - プラス**  
・・・1回以上の繰り返し

- **「?」 - クエスチョンマーク**  
・・・0回または1回の繰り返し

- **{n}**  
・・・n回の繰り返し

- **{n,}**  
・・・n回以上の繰り返し

- **{n,m}**  
・・・n回以上m回以下の繰り返し

- **最短一致**  
・・・数量詞の直後に「?」を記述する。  
　※デフォルトでは最長一致。

## 3. グループ化

- **「()」 - 丸括弧**  
・・・正規表現パターンをグループ化する。
　※ネスト可能。

- **「|」 - パイプ**  
・・・選択肢の設定（or条件）。

- **キャプチャ**  
・・・「\」+0~9の数字で、既出の丸括弧を参照する。  
　※丸括弧の中の先頭で「**?:**」と記述するとキャプチャを無効化する。  
　※置換で使用する時は「**$**」をつけて使用する。

## 4. アサーション

- **後読み**  
・・・直前またはすぐ左を調べる  
　例）/(?<=山田)太郎/

- **先読み**  
・・・直後またはすぐ右を調べる  
　例）/太郎(?=さん)/、/太郎(?=\d+)/

※否定する場合は「=」を「**!**」に変える。

## 5. 具体例

- 名前  
・・・「*/^(?!.*\s\s)(?!.*\\.\\.)[A-Z][A-Za-z .]{2,25}$/*」

- メールアドレス  
・・・<https://www.udemy.com/course/cfmenzkv/learn/lecture/21899778#overview>

- URL  
・・・<https://www.udemy.com/course/cfmenzkv/learn/lecture/21899892#overview>

- IPアドレス  
・・・<https://www.udemy.com/course/cfmenzkv/learn/lecture/21899932#overview>

- 日付  
・・・<https://www.udemy.com/course/cfmenzkv/learn/lecture/21899938#overview>

- パスワード  
・・・<https://www.udemy.com/course/cfmenzkv/learn/lecture/21899952#overview>
