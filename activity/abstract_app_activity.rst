==================
Activity基底クラス
==================

物理名、宣言
============

``abstract class AbstractAppActivity : AppCompatActivity()``

画面部品
========

基底クラスのためUIは持たない。

イベント処理
============

初期化
------

#. :ref:`initialize_navigation_drawer` にある ``NavigationDrawer`` 初期化処理を行う。

.. _get_realtime_database:

Realtime Database 取得
----------------------

#. ``FirebaseDatabase.getInstance()`` を実行し、 ``FirebaseDatabase`` を取得する。
#. ``setPersistenceEnabled(true)`` を実行し、永続化を有効にする。
#. ``getReference()`` を実行し、 ``DatabaseReference`` を取得する。