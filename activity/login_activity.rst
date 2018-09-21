============
ログイン画面
============

物理名、宣言
============

``class LoginActivity : AbstractAppActivity()``

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
   * - ログインボタン
     - Button
     - I/O
     - -
     - -
     - Login with Google
     - -
     - 初期化時は非表示( ``View.GONE`` )
   * - 初期化表示
     - TextView
     - O
     - -
     - -
     - initializing ...
     - -
     - 初期化時はログインボタンの上に表示( ``View.VISIBLE`` )

イベント処理
============

初期化
------

#. ``onCreate(Bundle)`` では、 ``GoogleSignInOption`` と ``GoogleApiClient`` を `Android で Google ログインを使用して認証する - Firebase で認証する <https://firebase.google.com/docs/auth/android/google-signin?hl=ja#authenticate_with_firebase>`_ の記述に従い初期化する。
#. ``onStart()`` で、 Firebase のログイン中ユーザーを取得する。
#. ログイン中ユーザーが取得できた場合、ログイン中なのでタスクリスト画面へ遷移する。
#. ログイン中ユーザーが取得できなかった場合は、以下の処理を行う。

   #. 画面部品.初期化表示を非表示( ``View.GONE`` )にする。
   #. 画面部品.ログインボタンを表示( ``View.VISIBLE`` )する。

ログインボタン押下時
--------------------

#. 