# 进程通信



## 计时器

请你实现一个可以进行倒计时的计时器 App。

基本要求：

- 在 Activity 中进行计时时间自定义设定
- 在 Service 中实现后台计时
- 计时完成时在通知栏推送通知，并在前台更新 UI

进阶要求：

- App 中实现一个动画效果，具体动画效果不做要求

  

## 对讲机

请你实现一个由 **两个独立的 App** 组成的对讲机系统。

基本要求：

- 发送端可以发送消息给接收端，并在接收端显示
- 将消息及其发送时间储存在接收端的 List 集合中

进阶要求：

- 将以上记录用数据库进行持久化储存

  

提示：你可以使用以下 IPC 方法完成本题

1. ContentProvider
2. Messenger
3. AIDL（可参照例子 https://github.com/Yunlong626/AidlConnnection/tree/master ）

本题 UI 不做限制和要求
