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