==========
 Java小用
==========
:tags: java, oop
:category: java

.. contents::

----------------------------------------

下面就是一些有关Java体验的提示：

1. 在一个文件中给出类的完整层次。

2. 对于每个命名不以上标D、V、I、M结尾的类，\
   添加 `toString` 方法，并遵守以下规则：

   a) 如果一个类没有属性

      .. code-block:: java

         public String toString() {
             return "new " + getClass().getName() + "()";
         }

   b) 如果一个类只有一个属性，比如叫 `x`

      .. code-block:: java

         public String toString() {
             return "new " + getClass().getName() + "(" + x + ")";
         }

   c) 如果一个类有两个属性，比如叫 `x` 和 `y`

      .. code-block:: java

         public String toString() {
             return "new " + getClass().getName() + "(" + x + ", " + y + ")";
         }

3. 在文件的底部添加如下类：

   .. code-block:: java

      class Main {
          public static void main(String args[]) {
              DataType_or_Interface y = new ______;
              System.out.println( ... ... );
          }
      }

`DataType_or_Interface y = new ______;` 是用来创建你想尝试的对象。

`System.out.println( ... ... );` 是用来填写你想尝试的表达式。

比如，你想尝试第2章定义的 `ManhattanPt` 的 `distanceTo0` 方法，\
你就可以添加如下代码到你文件的最后：

.. code-block:: java

   class Main{
       public static void main(String args[]) {
           PointD y = new ManhattanPt(2, 8);
           System.out.println(y.distanceTo0());
       }
   }

如果你想尝试多条表达式，就修改 `y` ，就像第10章里，
::

   y._ _ _ _ _ _;
   y._ _ _ _ _ _;
   y._ _ _ _ _ _

替换成
::

   y._ _ _ _ _ _ + "\n" +
   y._ _ _ _ _ _ + "\n" +
   y._ _ _ _ _ _

如果你想尝试第10章中定义的 `PiemanM` 的多个方法，\
那么你就将以下代码写在文件的最后面：

.. code-block:: java

   class Main {
       public static void main(String args[]) {
           PiemanI y = new PiemanM();
           System.out.println(
               y.addTop(new Anchovy()) + "\n" +
               y.addTop(new Anchovy()) + "\n" +
               y.substTop(new Tuna(), new Anchovy())
           );
       }
   }

4. 最后，编译文件并且执行 `Main` 类。

   .. tip::
      `Main`类不能声明为public，因为声明为public的是你自己的类，`Main`是在你自己的类中新增的类。运行时要指定运行的是`Main`，
      否则会执行你自己的类的main方法。
