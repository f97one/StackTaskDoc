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
     - タスクアイテム.完了チェック
     - -
   * - タスク名
     - TextView
     - O
     - -
     - -
     - -
     - タスクアイテム.タスク名
     - elipsise = end
   * - 期日
     - TextView
     - O
     - -
     - -
     - -
     - タスクアイテム.期日
     - nullの場合「-」を表示
   * - 優先度
     - RatingBar
     - O
     - -
     - -
     - 1
     - タスクアイテム.優先度
     - -
   * - タスク追加ボタン
     - FloatingActionButton
     - I/O
     - -
     - -
     - -
     - -
     - 「＋」を画像表示

