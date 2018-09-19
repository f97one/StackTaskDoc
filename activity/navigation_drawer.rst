================
NavigationDrawer
================

画面部品
========

.. list-table::
   :header-rows: 1

   * - 論理名
     - 種別
     - I/O
     - 最大桁数
     - 入力規則
     - 初期値
     - 導入元
     - 備考
   * - ユーザー名
     - TextView
     - O
     - 32
     - -
     - -
     - FirebaseUser.providerData.UserInfo.displayName
     - 端末のGoogleアカウントにひもづくユーザー情報から取得
   * - タスクリスト
     - ListItem
     - I/O
     - -
     - -
     - Task List
     - -
     - クリックイベントあり
   * - 設定
     - ListItem
     - I/O
     - -
     - -
     - Settings
     - -
     - クリックイベントあり
   * - ログアウト
     - ListItem
     - I/O
     - -
     - -
     - Logout
     - -
     - クリックイベントあり

イベント処理
============

初期化
------

Activity の規定処理として実装する。

