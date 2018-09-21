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

.. _initialize_navigation_drawer:

初期化
------

#. Activity の規定処理として、 `ナビゲーションドロワーの作成 <https://developer.android.com/training/implementing-navigation/nav-drawer?hl=ja>`_ に従い 実装する。
#. 現在の FirebaseUser を取得する。
#. ユーザーが取得できた場合は、以下の手順で現在のユーザーを再認証する。

   #. Googleアカウントの認証情報を取得する。
   #. ``FirebaseUser.reauthenticate`` で再認証する。
   #. 再認証終了後、取得できたユーザー情報のユーザー名を、 NavigationDrawer.ユーザー名にセットする。
   #. 各画面の処理に戻る

#. ユーザーが取得できなかった場合、かつ現在の画面がログイン画面以外の場合、ログイン画面へ遷移する。

タスクリスト クリック時
-----------------------

#. タスクリスト画面へ遷移する。（引数なし）

設定 クリック時
---------------

#. アプリ設定画面へ遷移する。（引数なし）

ログアウト クリック時
---------------------

#. ``FirebaseAuth.signout()`` を実行する。
#. 成功の場合、バックスタックをクリアしてログイン画面へ遷移する。
