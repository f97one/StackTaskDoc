===========================
Realtime Database JSON 構造
===========================

Firebase Realtime Database に保存される、全体の JSON 構造を示す。

.. code-block:: json
   :linenos:

   {
       "StackTask": {
           "userId": ユーザーID,
           "taskItems": [
               "taskItem": {
                   "taskId": タスクID,
                   "userId": ユーザーID,
                   "taskName": タスク名,
                   "dueDate": 期日,
                   "priority": 優先度,
                   "finished": 完了チェック,
                   "createdAt": レコード作成日,
                   "updatedAt": レコード更新日
               }
           ]
       }
   }