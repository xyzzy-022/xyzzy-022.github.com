---
layout: post
title: xyzzy 0.2.2.251 リリースノート
category: xyzzy
tags: []
---
{% include JB/setup %}

  * バージョン: 0.2.2.251
  * リリース日: 2013-08-29
  * ホームページ: <http://xyzzy-022.github.com>
  * ダウンロード: [xyzzy-0.2.2.251.zip](/downloads/xyzzy-0.2.2.251.zip)
    ([ソース](/downloads/xyzzy-src-0.2.2.251.zip))
  * SHA1 チェックサム: `07b834db58adc8438bdbc478d705542f7f328418`


インストール
------------

インストーラはありませんので zip を展開するだけです。
インストールから初期設定までは以下を参照してください。

  * [QuickTour - XyzzyWiki]


アップデート
------------

以下の手順で 0.2.2.235 からアップデートしてください。

  1. 0.2.2.235 のバックアップ取得
  2. 0.2.2.251 を上書き
  3. $XYZZY/html を削除 ($XYZZY/docs/old に移動しています)
  4. xyzzy.wxp を削除
  5. xyzzy.exe 起動

lisp/ 配下や etc/ 配下をカスタマイズしている場合は
上書き後に再度カスタマイズをお願いします。


機能追加
--------

  * [共通設定]-[ファイラ]に[ゴミ箱を使って削除]の設定を追加しました ([#401], x022235)

  * ファイラでファイル操作をエクスプローラに任せる事ができるようになりました ([#376], [#298], x022235)

    ファイル操作をエクスプローラに任せることで以下のメリットがあります。

    * ファイル操作の進捗状況がダイアログで確認できる
    * 大量のファイル削除の高速化
    * ゴミ箱を使ってフォルダを削除した場合に、フォルダがそのままゴミ箱に入る
      （従来はフォルダの中のファイルが 1 つづつバラバラにゴミ箱に入るためもとに戻すのが大変）

    共通設定または `*filer-use-shell-file-operation*` で設定できます。

    ![filer-setting]

    ![filer-copy]

バグ修正
--------

  * 「最初からやり直し」を使った時にファイル先頭に書かれたエンコーディング指定を
    常に見るようにしました ([#397], molety, x022235)

  * ファイルを開くダイアログでのエンコーディング指定をファイル先頭に書かれたエンコーディング指定より
    優先するようにしました ([#396], molety, x022235)

  * Windows8 で [共通設定]-[さまざま]-[完全に同期] が表示が切れている問題を修正しました ([#403], x022235)


既知の問題
----------

  * <https://github.com/xyzzy-022/xyzzy/issues?labels=bug&state=open>


`(provide "xyzzy-0.2.2.251")`

  [QuickTour - XyzzyWiki]: http://xyzzy.s53.xrea.com/wiki/index.php?QuickTour
  [filer-setting]: https://f.cloud.github.com/assets/1522408/1049773/9c160cb6-10ae-11e3-82dd-013ddb86e93c.png
  [filer-copy]: https://f.cloud.github.com/assets/1522408/1049774/a2908170-10ae-11e3-8383-361a6acbfeb7.png
  [#298]: https://github.com/xyzzy-022/xyzzy/issues/298
  [#376]: https://github.com/xyzzy-022/xyzzy/issues/376
  [#396]: https://github.com/xyzzy-022/xyzzy/issues/396
  [#397]: https://github.com/xyzzy-022/xyzzy/issues/397
  [#401]: https://github.com/xyzzy-022/xyzzy/issues/401
  [#403]: https://github.com/xyzzy-022/xyzzy/issues/403
