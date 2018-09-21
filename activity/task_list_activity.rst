================
タスクリスト画面
================

物理名、宣言

``class TaskListActivity : AbstractAppActivity()``


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
   * - タスクリスト
     - RecyclerView
     - I/O
     - -
     - -
     - -
     - -
     - 
   * - タスクカード
     - CardView
     - I/O
     - -
     - -
     - -
     - -
     - タスクリスト内に表示
   * - 完了チェック
     - CheckBox
     - I/O
     - -
     - -
     - checked = false
     - 導入元
     - 備考
