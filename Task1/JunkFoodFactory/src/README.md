# 垃圾食品工厂



## 题目背景

Android 组的某位同学非常地喜欢吃垃圾食品，尤其是坐落于~~三本武汉城建学院~~ CBD 的 Burger King 与位于 985 华中理工大学的 McDonald's。

但是由于近期疫情反复，学校采取了一刀切的防疫政策，校内店铺的营业受到很大影响，甚至被迫停摆，正在出熬测题的这位同学十分伤心，希望你能使用面向对象的程序设计知识，为他使用 Java 编写一个可以生成汉堡套餐的程序。



## 题目要求

你需要编写可以实现以下逻辑的代码：

- `JunkFood` 抽象类：记录垃圾食品的名字与卡路里，输出方法 `printInformation()` 输出该垃圾食品的信息。
- `Burger`、`Fries`、`Cola` 类：继承自 `JunkFood` 类，**但各自拥有自己独特的属性**。
- `BurgerMeal` 类：拥有以上三个类的对象，组成一个汉堡套餐，输出方法 `printInformation()` 输出该套餐的名字，3 个组分各自的信息以及 **总热量**。
- `JunkFoodMenu` 类：内部 **至少实现两种静态工厂方法**  `orderBurgerMeal() `，返回一个汉堡套餐 `BurgerMeal` 对象。
- 你的 `Main.main()` 方法应该调用 `orderBurgerMeal()` 获得两个不同的 `BurgerMeal` 对象，然后使用其输出方法来输出套餐的信息来表示你完成了该任务。



## 代码示例

使用示例：

```java
public class Main {
    public static void main(String[] args) {
        BurgerMeal whopperMeal = JunkFoodMenu.orderWhopperMeal();
        BurgerMeal chickenBurgerMeal= JunkFoodMenu.orderChickenBurgerMeal();
        whopperMeal.printMessage();
        chickenBurgerMeal.printMessage();
    }
}
```



输出示例：

```
皇堡套餐
皇堡
Calories: 400.0 kcal
Net Weight: 300g
薯霸王
Calories: 200.0 kcal
Size: 小
可口可乐
Calories: 200.0 kcal
Net Weight: 330 mL
Total Calories: 800.0 kcal

板烧鸡腿堡套餐
板烧鸡腿堡
Calories: 250.0 kcal
Net Weight: 250g
薯条
Calories: 300.0 kcal
Size: 中
零度可口可乐
Calories: 0.0 kcal
Net Weight: 350 mL
Total Calories: 550.0 kcal

```


## 思考题

请你将以下思考题的答案写于你的代码注释或直接添加到本文件中。

- Java 中静态方法与普通方法的区别有哪些？
- `JunkFood` 为何被设计为抽象类？尝试给出这样做的理由。
- 静态工厂方法相较直接使用构造器方法创建 `BurgerMeal` 对象，有何优点？

