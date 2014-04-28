---
layout: post
title: xyzzy 0.2.2.253 リリースノート
category: xyzzy
tags: []
---
{% include JB/setup %}

  * バージョン: 0.2.2.253
  * リリース日: 2014-04-29
  * ホームページ: <http://xyzzy-022.github.com>
  * ダウンロード: [xyzzy-0.2.2.253.zip](/downloads/xyzzy-0.2.2.253.zip)
    ([ソース](/downloads/xyzzy-src-0.2.2.253.zip))
  * SHA1 チェックサム: `6a926be393745de811a5f69fb481bbf71590dcae`


インストール
------------

インストーラはありませんので zip を展開するだけです。
インストールから初期設定までは以下を参照してください。

  * [QuickTour - XyzzyWiki]


アップデート
------------

以下の手順で 0.2.2.235 からアップデートしてください。

  1. 0.2.2.235 のバックアップ取得
  2. 0.2.2.253 を上書き
  3. $XYZZY/html を削除 ($XYZZY/docs/old に移動しています)
  4. xyzzy.wxp を削除
  5. xyzzy.exe 起動

lisp/ 配下や etc/ 配下をカスタマイズしている場合は
上書き後に再度カスタマイズをお願いします。


機能追加
--------

  * バッファ選択ダイアログのソート順を改善 (rapidexp, x022235, [#414])

    [共通設定]-[いろいろ]に以下の設定を追加。

    ![select-buffer-options](https://cloud.githubusercontent.com/assets/1522408/2777403/d50f9e6a-cae4-11e3-8df8-157b08c14c3f.png)

    * ソート方法を保存をチェックした場合は前回バッファ選択ダイアログで指定したソート順でソート
    * 前回のソート順が保存されていない場合や、保存しないように設定している場合はデフォルトのソート順でソート
    * また、選択ダイアログのカラム名をクリックでの降順ソートにも対応


バグ修正
--------

  * Google 日本語入力の「カーソル周辺に入力モード表示」の位置がずれる問題を修正 (coexe, [#398], [#410])

  * ファイラにおけるフォルダ名の変更に対応 (x022235, [#408], [xyzzy:09314])

    正規表現を使った複数のフォルダを指定しての名前変更が動作していなかったのを修正。


その他
------

  * zlib 1.2.8 へ更新 (x022235, [#412])

  * VisualStudio 2013 に移行 (x022235, [#411])


既知の問題
----------

  * <https://github.com/xyzzy-022/xyzzy/issues?labels=bug&state=open>


`(provide "xyzzy-0.2.2.253")`

  [QuickTour - XyzzyWiki]: http://xyzzy.s53.xrea.com/wiki/index.php?QuickTour
  [#398]: https://github.com/xyzzy-022/xyzzy/issues/398
  [#408]: https://github.com/xyzzy-022/xyzzy/issues/408
  [#410]: https://github.com/xyzzy-022/xyzzy/issues/410
  [#411]: https://github.com/xyzzy-022/xyzzy/issues/411
  [#412]: https://github.com/xyzzy-022/xyzzy/issues/412
  [#414]: https://github.com/xyzzy-022/xyzzy/issues/414
