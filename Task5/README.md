## 进程通信

### 需求

1. 实现一个计时器：

   - 进行计时时间自定义设定（倒计时）
   - 在service中实现后台计时
   - 计时完成时显示通知，更新UI
   - 进阶：app中实现一个动画

2. 实现一个对讲机：

   - 两个App，互相发送消息，并能显示收到的消息

     (例如：App1发送一条消息后，会在App2中打印，并且存储消息和发送时间在App2中的List集合里)



提示：以下三种方式均可

1. ContentProvider
2. Messenger
3. AIDL（可参照例子  https://github.com/Yunlong626/AidlConnnection/tree/master）

UI不做限制和要求

进阶 (选做)：将以上记录能够持久化存储，如果能用多种方式实现更佳