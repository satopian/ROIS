# ROIS

ROISは全く新しいお絵かき掲示板スクリプトです。  
Rapid Oekaki Image System で「ROIS」です。

[PaintBBS NEO](https://github.com/funige/neo/)

## 概要

POTI-board改で使用しているテンプレートエンジン「htmltemplate.inc」は老朽化して今後が危ない…  
ということでなんか新しいテンプレートエンジンはないか探したところ、

[Skinny](http://skinny.sx68.net/) → [POTI-board EVO](https://github.com/satopian/POTI-board_EVO)  
↓  
[smarty](https://www.smarty.net/) → [noe](https://github.com/sakots/noe-board)  
↓  
重いからTwigにしたい…（今後）  
↓  
BladeのほうがTwigより速いらしい！？

という経緯です。

## 設置方法

- パスワードその他を設定  
- アップロード
- OK！ index.phpにアクセスしてください。

## 注意

- まだいわゆるアルファ版です。テーマ等仕様がころころ変わる可能性があります。
- noeとデータベースの互換性はありますが、テーマの互換性はありません。

## サンプルとサポート

[このお絵かき掲示板はSQLiteとさらにBladeを（以下略](https://dev.oekakibbs.net/bbs/rois/)

## 同梱のパレットについて

`p_PCCS.txt`(PCCS:日本色研配色体系パレット)は、[色彩とイメージの情報サイト IROUE](https://tee-room.info/color/database.html) を参考に、`p_munsellHVC.txt`(マンセルHV/Cパレット)は、[マンセル表色系とRGB値](http://k-ichikawa.blog.enjoy.jp/etc/HP/js/Munsell/MSL2RGB0.html) を参照して作成いたしました。

再配布等自由にしていただいて構いません。ただの文字列なので著作権の主張はしませんが、書くのにそれなりの苦労はしましたので、再配布の際はどこかに私の名前を書いていただければと思います。

## 履歴

### [2021/08/12] v0.99.1

- phpスクリプト内の、Bladeに渡す配列の書式変更(by さとぴあ)
- しぃペインターで動画から続きを書けないバグ修正

### [2021/08/11] v0.99.0

- 続きから描くの画像差し替えが機能していなかったの修正
- パレット選択機能実装
- そのついでにパレットデータ`p_PCCS.txt`,`p_munsellHVC.txt`を作ったので同梱
- configに設定はあったトラブルシューティングを実装
- 各テーマ更新
- あとなんかたくさん更新した気がするけど忘れた

### [2021/08/10] v0.4.2b1

- いったんコミット
- 続きから描くときとアニメ再生時におかしかったの修正

### [2021/08/09] v0.4.1

- 各テーマ
  - 追加お知らせの表示がおかしいの修正
  - chickenpaintで描画時間が記録されないバグ修正
  - シェアボタンのリンクがうまく作成されないの修正

### [2021/08/09] v0.4.0

- [chickenpaint](https://github.com/thenickdude/chickenpaint)でのお絵描きに対応
- `config.php`
  - `$addinfo`を配列とし、htmlタグ`<li> </li>`で囲まれるように変更
  - 管理パスが初期値のままではスクリプトが動かないように念のため変更
  - 再設定をお願いします。
- 07/30の「データベースのサイズをあとから変えるのが困難」が解決できそうなのでこのまま行くことにした。
- 各テーマもかなり更新しております

### [2021/08/02] v0.3.0

- セキュリティ対策の改善
  - タグや特殊文字は表示するときに無効化する。
  - さとぴあさんありがとうございます。
- 改行はコードのまま保存し、表示のときにHTMLタグにするように変更
- コンフィグファイルの互換性がなくなったときは起動できないようにした
- csrfトークンを使って不正な投稿を拒絶する設定追加

### [2021/07/30] 今後

~~ - やはり「データベースのサイズをあとから変えるのが困難」ということで、ログの保存形式をjsonかなにかにしようと思った。 ~~

### [2021/07/13] v0.2.4

- v0.2.3がちょっと間違ってたので修正。

### [2021/07/12] v0.2.3

- URL欄にURLじゃないものが入っていた場合表示しないように修正。

### [2021/07/06] v0.2.2

- theme(MONORED)
  - css切り替え機能の脆弱性その他修正
  - そしたらjqueryが不要になったので削除
  - Paint画面に無意味にカラーピッカーを搭載

### [2021/06/23] themes

- NEOでアプレットフィットONのときにキャンバスサイズを拡大して、そのままOFFにすると表示が崩れるの修正。
- シェアボタンあたりとアイコン周り修正。

### [2021/06/14] v0.2.1

- テキストエリアからCtrl+Enterで送信できるようにした。
- 送信ボタンの位置修正。
- アプレットフィットの著作権を表示。

### [2021/06/13] v0.2.0

- パレットファイル(`palette.txt`)の外部化
- アプレットフィット機能実装

### [2021/06/13] theme

- ついったでシェアできないの修正。

### [2021/06/13] v0.1.2

- 動画アニメーションモードに入れないバグ修正。
- 管理モードに入れないバグ修正。

### [2021/06/05] v0.1.1

- 変数のtypo修正。

### [2021/06/05] themes

- `$addinfo`でタグが使えないの修正。

### [2021/06/05] v0.1.0

- 公開。
