==============
タスクアイテム
==============

物理名
======

+----------+-----------+
| クラス名 | TaskItem  |
+----------+-----------+
| JSON     | task_item |
+----------+-----------+

フィールド
==========

.. list-table::
   :header-rows: 1

   * - 物理名
     - 論理名
     - 型
     - 主キー順序
     - NOT NULL制約
     - デフォルト
     - DDLオプション
     - コメント
   * - taskId
     - タスクID
     - String(UUID)
     - 1
     - あり
     - -
     - -
     - タスクを一意に判別するID
   * - userId
     - ユーザーID
     - String
     - -
     - あり
     - ``FirebaseUser#uid``
     - -
     - タスクを所有するユーザー
   * - taskName
     - タスク名
     - String(length = 32)
     - -
     - あり
     - -
     - -
     - タスクの表示名
   * - dueDate
     - 期日
     - String(DateTime)
     - -
     - あり
     - -
     - -
     - タスクの期日
   * - priority
     - 優先度
     - Int
     - -
     - あり
     - 1
     - 
     - タスクの優先度、1～3で表現
   * - taskDetail
     - タスク詳細
     - String(length = 200)
     - -
     - なし
     - -
     - -
     - タスクの詳細
   * - finished
     - 完了チェック
     - Boolean
     - -
     - なし
     - false
     - -
     - タスクを完了したかどうかを表すフラグ
   * - createdAt
     - 作成日
     - String(DateTime)
     - -
     - なし
     - 現在日時
     - -
     - このレコードを作成した日時
   * - updatedAt
     - 更新日
     - String(DateTime)
     - -
     - なし
     - -
     - 
     - このレコードを更新した日時
