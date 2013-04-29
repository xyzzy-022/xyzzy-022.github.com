---
layout: post
title: xyzzy 0.2.2.249 リリースノート
category: xyzzy
tags: []
---
{% include JB/setup %}

  * バージョン: 0.2.2.249
  * リリース日: 2013-04-29
  * ホームページ: <http://xyzzy-022.github.com>
  * ダウンロード: [xyzzy-0.2.2.249.zip](downloads/xyzzy-0.2.2.249.zip)
    ([ソース](downloads/xyzzy-src-0.2.2.249.zip))
  * SHA1 チェックサム: `3e93c64dd7b4e04a0f5475472999689c58c12e72`


インストール
------------

インストーラはありませんので zip を展開するだけです。
インストールから初期設定までは以下を参照してください。

  * [QuickTour - XyzzyWiki]


アップデート
------------

以下の手順で 0.2.2.235 からアップデートしてください。

  1. 0.2.2.235 のバックアップ取得
  2. 0.2.2.249 を上書き
  3. $XYZZY/html を削除 ($XYZZY/docs/old に移動しています)
  4. xyzzy.wxp を削除
  5. xyzzy.exe 起動

lisp/ 配下や etc/ 配下をカスタマイズしている場合は
上書き後に再度カスタマイズをお願いします。


機能追加
--------

  * Wineでの日本語フォント設定改善 (rapidexp, x022235, [#386])

    Wine 上で xyzzy を実行した場合に同じフォント名が複数表示される問題を修正しました。
    また、日本語フォントを選んでも再起動すると同名の英語フォントが設定され、
    文字化けする問題を修正しました。

  * フレームの並びの保存 (x022235, [#381])

    `*next-pseudo-frame-in-tab-order*` スペシャル変数を追加しました。
    `non-nil` に設定すると `next-pseudo-frame` 等でフレームバーでの
    順番でフレームを切り替えます。

    また、ssn セッションにもフレームバーでの順番で保存されます。


バグ修正
--------

  * HTML5 キーワードから空要素の終了タグを削除しました (furugomu, [#387])


既知の問題
----------

  * <https://github.com/xyzzy-022/xyzzy/issues?labels=bug&state=open>


`(provide "xyzzy-0.2.2.249")`

  [QuickTour - XyzzyWiki]: http://xyzzy.s53.xrea.com/wiki/index.php?QuickTour
  [#381]: https://github.com/xyzzy-022/xyzzy/issues/381
  [#386]: https://github.com/xyzzy-022/xyzzy/issues/386
  [#387]: https://github.com/xyzzy-022/xyzzy/issues/387
