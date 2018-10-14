===========================
Realtime Database JSON 構造
===========================

Firebase Realtime Database に保存される、全体の JSON 構造を示す。

.. code-block:: json
   :linenos:

   {
       "StackTask": [
            "キー": {
                "taskId": "タスクID",
                "userId": "ユーザーID",
                "taskName": "タスク名",
                "dueDate": "期日",
                "priority": "優先度",
                "taskDetail": "タスク詳細",
                "finished": "完了チェック",
                "createdAt": "作成日",
                "updatedAt": "更新日"
            }
        ]
   }

Firebase Realtime Database の特性により、上記「キー」部分は一意のIDが割り当てられる。
