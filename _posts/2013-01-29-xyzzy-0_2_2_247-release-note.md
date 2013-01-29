---
layout: post
title: xyzzy 0.2.2.247 リリースノート
category: xyzzy
tags: []
---
{% include JB/setup %}

  * バージョン: 0.2.2.247
  * リリース日: 2013-01-29
  * ホームページ: <http://xyzzy-022.github.com>
  * ダウンロード: [xyzzy-0.2.2.247.zip](http://xyzzy-022.github.com/downloads/xyzzy-0.2.2.247.zip)
    ([ソース](http://xyzzy-022.github.com/downloads/xyzzy-src-0.2.2.247.zip))
  * SHA1 チェックサム: `8897b5d01c04532eaf25a771508ba051cfa89fda`


インストール
------------

インストーラはありませんので zip を展開するだけです。
インストールから初期設定までは以下を参照してください。

  * [QuickTour - XyzzyWiki]


アップデート
------------

以下の手順で 0.2.2.235 からアップデートしてください。

  1. 0.2.2.235 のバックアップ取得
  2. 0.2.2.247 を上書き
  3. $XYZZY/html を削除 ($XYZZY/docs/old に移動しています)
  4. xyzzy.wxp を削除
  5. xyzzy.exe 起動

lisp/ 配下や etc/ 配下をカスタマイズしている場合は
上書き後に再度カスタマイズをお願いします。


機能追加
--------

  * 管理者ユーザかどうかをタイトルバーに表示するようにしました (x022235, [#333])

    コマンドプロンプトのように管理者ユーザで xyzzy を起動した場合、
    タイトルバーに `管理者: ` を表示するようにしまし。

    また、`title-bar-format` と `mode-line-format` に以下のフォーマットを追加しました。

        %!    管理者          (管理者権限の場合のみ、一般ユーザの場合は空文字列)
        %#!   管理者:         (# をつけるとコロンも付ける)

  * Avast! で xyzzycli がウイルスと誤認される問題を修正しました (x022235, [#373])

    最適化をオフにしてビルドしなおしただけなので、またいつか誤認されるかもしれません。


バグ修正
--------

  * `run-admin-console` が現在のバッファのディレクトリで起動するようにしました (x022235, [#374])


xyzzy Lisp 開発者向け機能追加
-----------------------------

  * `ed:user-admin-p` を追加しました (x022235, [#333])

    管理者ユーザで xyzzy を実行している場合は t を返します


xyzzy Lisp 開発者向けバグ修正
-----------------------------

  * なし


既知の問題
----------

  * <https://github.com/xyzzy-022/xyzzy/issues?labels=bug&state=open>


`(provide "xyzzy-0.2.2.247")`

  [QuickTour - XyzzyWiki]: http://xyzzy.s53.xrea.com/wiki/index.php?QuickTour
  [#333]: https://github.com/xyzzy-022/xyzzy/issues/333
  [#373]: https://github.com/xyzzy-022/xyzzy/issues/373
  [#374]: https://github.com/xyzzy-022/xyzzy/issues/374
