
C# 是面向对象的、面向组件的编程语言。 垃圾回收会自动回收无法访问的未使用对象所占用的内存。 可以为 null 的类型可防范不引用已分配对象的变量。 
异常处理提供了一种结构化且可扩展的方法来进行错误检测和恢复。 Lambda 表达式支持函数编程技术。 
语言集成查询 (LINQ) 语法创建一个公共模式，用于处理来自任何源的数据。 异步操作语言支持提供用于构建分布式系统的语法。
C# 采用统一的类型系统。 所有 C# 类型（包括 int 和 double 等基元类型）均继承自一个根 object 类型。 所有类型共用一组通用运算。 
任何类型的值都可以一致地进行存储、传输和处理。 此外，C# 还支持用户定义的引用类型和值类型。
C# 允许动态分配轻型结构的对象和内嵌存储。 C# 支持泛型方法和类型，因此增强了类型安全性和性能。
C# 可提供迭代器，使集合类的实现者可以定义客户端代码的自定义行为。

#### .NET 体系结构
C# 程序在 .NET 上运行，而 .NET 是名为公共语言运行时 (CLR) 的虚执行系统和一组类库。
CLR 是 Microsoft 对公共语言基础结构 (CLI) 国际标准的实现。 CLI 是创建执行和开发环境的基础，语言和库可以在其中无缝地协同工作。
 C# 编写的源代码被编译成符合 CLI 规范的中间语言 (IL)。 IL 代码和资源（如位图和字符串）存储在程序集中，扩展名通常为 .dll。
 执行 C# 程序时，程序集将加载到 CLR。 CLR 会直接执行实时 (JIT) 编译，将 IL 代码转换成本机指令。 CLR 可提供其他与自动垃圾回收、异常处理和资源管理相关的服务。 
 
C# 有两种类型：__值类型__ 和 __引用类型__ 。 值类型的变量直接包含它们的数据。 引用类型的变量存储对数据（称为“对象”）的引用。 
对于引用类型，两个变量可以引用同一个对象；对一个变量执行的运算可能会影响另一个变量引用的对象。 借助值类型，每个变量都有自己的数据副本；
因此，对一个变量执行的运算不会影响另一个变量（ref 和 out 参数变量除外）。
C# 的类型系统。

- 值类型
  - 简单类型
    - 有符号整型：sbyte、short、int、long
    - 无符号整型：byte、ushort、uint、ulong
    - Unicode 字符：char，表示 UTF-16 代码单元
    - IEEE 二进制浮点：float、double
    - 高精度十进制浮点数：decimal
    - 布尔值：bool，表示布尔值（true 或 false）
  - 枚举类型
    - enum E {...} 格式的用户定义类型。 enum 类型是一种包含已命名常量的独特类型。 每个 enum 类型都有一个基础类型（必须是八种整型类型之一）。 enum 类型的值集与基础类型的值集相同。
  - 结构类型
    - 格式为 struct S {...} 的用户定义类型
  - 可以为 null 的值类型
    - 值为 null 的其他所有值类型的扩展
  - 元组值类型
    - 格式为 (T1, T2, ...) 的用户定义类型
- 引用类型
  - 类类型
    - 其他所有类型的最终基类：object
    - Unicode 字符串：string，表示 UTF-16 代码单元序列
    - 格式为 class C {...} 的用户定义类型
  - 接口类型
    - 格式为 interface I {...} 的用户定义类型
  - 数组类型
    - 一维、多维和交错。 例如：int[]、int[,] 和 int[][]
  - 委托类型
    - 格式为 delegate int D(...) 的用户定义类型

class、struct、interface 和 delegate 类型全部都支持泛型，因此可以使用其他类型对它们进行参数化。

* 数组
  * C# 支持任意类型的一维和多维数组。 与上述类型不同，数组类型无需先声明即可使用。 相反，数组类型是通过在类型名称后面添加方括号构造而成。 例如，int[] 是 int 类型的一维数组，
  int[,] 是 int 类型的二维数组，int[][] 是由 int 类型的一维数组或“交错”数组构成的一维数组。

C# 采用统一的类型系统，因此任意类型的值都可视为 object。 每种 C# 类型都直接或间接地派生自 object 类类型，而 object 是所有类型的最终基类。
只需将值视为类型 object，即可将引用类型的值视为对象。 通过执行 装箱 和 取消装箱操作，可以将值类型的值视为对象。

C# 程序可以存储在多个源文件中。 在编译 C# 程序时，将同时处理所有源文件，并且源文件可以自由地相互引用。 从概念上讲，就好像所有源文件在被处理之前都连接到一个大文件。 在 C# 中永远都不需要使用前向声明，因为声明顺序无关紧要（极少数例外情况除外）。 C# 并不限制源文件只能声明一种公共类型，也不要求源文件的文件名必须与其中声明的类型相匹配。

https://docs.microsoft.com/zh-cn/dotnet/csharp/tour-of-csharp/

C# 支持封装、继承和多态性这些概念。
若要用方法重写父类中的虚方法，必须使用 __override 关键字__ ，以免发生意外重定义。
