---
layout: post
title: xyzzy 0.2.2.237 リリースノート
category: xyzzy
tags: []
---
{% include JB/setup %}

  * バージョン: 0.2.2.237
  * リリース日: 2012-03-31
  * ホームページ: <http://xyzzy-022.github.com>
  * ダウンロード: [xyzzy-0.2.2.237.zip](http://xyzzy-022.github.com/downloads/xyzzy-0.2.2.237.zip)
    ([ソース](http://xyzzy-022.github.com/downloads/xyzzy-src-0.2.2.237.zip))
  * SHA1 チェックサム: `30a0222c44d00e1ba38de9e8516736c07ef5c852`


はじめに
--------

0.2.2.236 で Windows XP 環境で設定ファイルのパスが `$XYZZY/usr/<UserName>/wxp` から `$XYZZY/usr/<UserName>/wnt`
に変わってしまっていた問題を修正した hotfix リリースです。

ついでに calc-mode も少し修正しています。

0.2.2.236 のリリースノートは以下を参照してください。

  * <http://xyzzy-022.github.com/xyzzy/2012/03/29/xyzzy-0_2_2_236-release-note/>


インストール
------------

インストーラはありませんので zip を展開するだけです。
インストールから初期設定までは以下を参照してください。

  * [QuickTour - XyzzyWiki](http://xyzzy.s53.xrea.com/wiki/index.php?QuickTour)


アップデート
------------

  * Windows XP で利用している方は以下の手順で 0.2.2.236 からアップデートしてください。

    1. 0.2.2.235 の設定ファイル (`$XYZZY/usr/<UserName>/wxp`) をバックアップ
    2. 0.2.2.237 を上書き。
    3. もし設定が上手く復元出来なかったら、xyzzy.exe を終了後にバックアップした設定ファイルを
       `$XYZZY/usr/<UserName>/wxp` に上書きしてください。

  * 0.2.2.237 で更新・追加したファイルは以下のとおりです。

    * xyzzy.exe
    * lisp/calc.l
    * lisp/calc.lc
    * docs/release-note-0.2.2.237.md

----

  * 0.2.2.235 からアップデートする場合は以下の手順で実施してください。
    1. 0.2.2.235 のバックアップ取得
    2. 0.2.2.237 を上書き
    3. $XYZZY/html を削除 ($XYZZY/docs/old に移動しています)
    4. xyzzy.wxp を削除
    5. xyzzy.exe 起動
  * lisp/ 配下や etc/ 配下をカスタマイズしている場合は
    上書き後に再度カスタマイズをお願いします。


機能追加
--------

  * calc-mode で日本語の変数名が利用できるようになりました。([#183], x022235)

        $ Φ=(1+sqrt(5.0))/2
        1.618033988749895
        $ Φ*8
        12.94427190999916

    ※半角カナは利用できません


バグ修正
--------

  * calc-mode で「人生、宇宙、すべての答え * 2」を計算できるようになりました。([#181], x022235)

        $ 人生、宇宙、すべての答え * 2
        84
        $ sqrt(人生、宇宙、すべての答え)
        6.480741f0

  * Windows XP, 2000 で設定ファイルのパスが変わっていた問題を修正しました。([#185], m-takagi)


注意事項
--------

  * NetInstaller で入手可能な以下のパッケージは 0.2.2.236 では
    本体に同梱しています。インストールすると古いファイルで上書きされるので
    インストールしないようにしてください。

        keyword file                       2007.12.25     2007/12/25 01:27  | 2007.12.25     2007/12/25 01:27
        reference.xml                      2007.12.25     2007/12/25 01:23  | 2007.12.25     2007/12/25 01:23


既知の問題
----------

  * format の `~n@A` 書式がバグっている

    このバグの修正は影響範囲が大きいので修正されません。

        (format nil "~10@A" "hoge")
        "hoge      "                   ; 0.2.2.235, 0.2.2.236
        "      hoge"                   ; 本来の仕様

  * software-type, software-version が CL と異なる ([#169])
  * NULL 文字をインクリメンタル検索しようとすると落ちる ([#152])
  * :typeがlistかvectorで:namedじゃない構造体でtypepがおかしい ([#138])
  * ローカル関数で (setf READER) ([#137])
  * dualウィンドウモードでfilerのディレクトリ指定が動かない ([#130])
  * c-modeでマクロの継続行のインデントがおかしい ([#127])
  * クリップボードにコピーするとxyzzyが固まる場合がある ([#113])
  * C-u 999 C-g 後にメニュー操作でエラー ([#111])
  * Vista 以降で再変換 (C-c C-c) が動作しない ([#101])
  * ファイル保存時にパーミッションを保存 ([#96])
  * ole で responseBody, responseStream を取得できない ([#68])
  * ole-for-each で ie.Document.all の IEnum を取得できない ([#67])
  * ole-create-event-sink に TypeLib のファイル名を明示的に指定しないとエラーになる ([#66])
  * 巨大な文字列に対する正規表現マッチがすごい遅い ([#65])
  * load 時の *readtable* がファイルローカルではない ([#64])
  * setf の最適化に bug ([#63])
  * handler-case で :no-error を指定してコンパイルするとエラー ([#62])
  * labels の lambda-list 内の init-form で同じ labels 式で定義したローカル関数を呼び出してると、コンパイルで挙動が変わる ([#61])
  * si:binhex-decode で落ちる ([#45])
  * multiframe: 画面端の折り返しがウィンドウ単位でちゃんと動くようにする変更を取り込む ([#25])
  * siteinit.l が sjis 以外で書かれていた場合に対応 ([#11])
  * multiframe: cpp-syntax の修正を取り込む ([#10])


`(provide "xyzzy-0.2.2.237")`

  [#10]: https://github.com/xyzzy-022/xyzzy/issues/10
  [#11]: https://github.com/xyzzy-022/xyzzy/issues/11
  [#25]: https://github.com/xyzzy-022/xyzzy/issues/25
  [#45]: https://github.com/xyzzy-022/xyzzy/issues/45
  [#61]: https://github.com/xyzzy-022/xyzzy/issues/61
  [#62]: https://github.com/xyzzy-022/xyzzy/issues/62
  [#63]: https://github.com/xyzzy-022/xyzzy/issues/63
  [#64]: https://github.com/xyzzy-022/xyzzy/issues/64
  [#65]: https://github.com/xyzzy-022/xyzzy/issues/65
  [#66]: https://github.com/xyzzy-022/xyzzy/issues/66
  [#67]: https://github.com/xyzzy-022/xyzzy/issues/67
  [#68]: https://github.com/xyzzy-022/xyzzy/issues/68
  [#96]: https://github.com/xyzzy-022/xyzzy/issues/96
  [#101]: https://github.com/xyzzy-022/xyzzy/issues/101
  [#111]: https://github.com/xyzzy-022/xyzzy/issues/111
  [#113]: https://github.com/xyzzy-022/xyzzy/issues/113
  [#127]: https://github.com/xyzzy-022/xyzzy/issues/127
  [#130]: https://github.com/xyzzy-022/xyzzy/issues/130
  [#137]: https://github.com/xyzzy-022/xyzzy/issues/137
  [#138]: https://github.com/xyzzy-022/xyzzy/issues/138
  [#152]: https://github.com/xyzzy-022/xyzzy/issues/152
  [#169]: https://github.com/xyzzy-022/xyzzy/issues/169
  [#181]: https://github.com/xyzzy-022/xyzzy/issues/181
  [#183]: https://github.com/xyzzy-022/xyzzy/issues/183
  [#185]: https://github.com/xyzzy-022/xyzzy/issues/185
