============
ログイン画面
============

物理名、宣言
============

``class LoginActivity : AppCompatActivity()``

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

#. ``onCreate(Bundle)`` では、 ``GoogleSignInOption`` と ``GoogleSignInClient`` を `Android で Google ログインを使用して認証する - Firebase で認証する <https://firebase.google.com/docs/auth/android/google-signin?hl=ja#authenticate_with_firebase>`_ の記述に従い初期化する。
#. ``onStart()`` で、 Firebase のログイン中ユーザーを取得する。
#. ログイン中ユーザーが取得できた場合、ログイン中なのでタスクリスト画面へ遷移する。
#. ログイン中ユーザーが取得できなかった場合は、以下の処理を行う。

   #. 画面部品.初期化表示を非表示( ``View.GONE`` )にする。
   #. 画面部品.ログインボタンを表示( ``View.VISIBLE`` )する。

ログインボタン押下時
--------------------

#. ``GoogleSignInClient`` から SignInIntent を取得し、 ``startActivityForResult(Intent, Int)`` を実行する。
#. ``onActivityResult(Int, Int, Intent)`` で、 Google サインインの結果を取得する。
#. サインイン結果が取得できた場合、 :ref:`firebase_auth_with_google` を実行する。
#. サインイン結果の取得に失敗した場合、 ``Toast`` にて「Google Sign In failed. Please retry.」を表示する。


.. _firebase_auth_with_google:

Google アカウントによる Firebase 認証
-------------------------------------

#. 「Authenticating...」表示のプログレスダイアログを表示する。
#. Googleアカウントの ``IdToken`` から、Google認証プロバイダのクレデンシャルを取得する。
#. 2で取得したクレデンシャルを使い、 ``FirebaseAuth#signInWithCredential`` を実行する。
#. 終了後、サインインの成功いかんにかかわらず1で表示したプログレスダイアログを消す。
#. サインインに成功した場合、タスクリスト画面へ遷移する。
#. サインインに失敗した場合、 ``Toast`` にて「Authentication In failed. Please retry.」を表示する。
