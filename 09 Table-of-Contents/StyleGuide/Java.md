## Java 编码规范

### 一、Java源文件基础规范

#### 1.1 文件名

源文件名称由它包含主类的名称(区分大小写)加 **.java** 扩展名构成。

#### 1.2 文件编码

源文件都以 **UTF-8** 编码。

#### 1.3 特殊字符

##### 1.3.1 空白字符

除了行结束符序列，ASCII水平空格字符(0x20)是唯一一个可以出现在源文件任意位置的空白字符，这意味着：

 1. 所有其他空白字符都不能出现在字符串或者代码段中。
 2. **制表符** 不能在代码缩进中使用。

##### 1.3.2 特殊字符转义序列

对于具有特殊的转义序列的字符，如：`\b, \t, \n, \f, \r, \", \' 和 \\`,在源码必须使用该转义序列，而不是其相应的 **八进制编码**（例：`\012`）或 **Unicode** (例：`\u000a`) 编码。

##### 1.3.3 非 **ASCII** 字符 （不必须）

对于其余的非 **ASCII** 字符，无论是使用实际的Unicode字符（如：`∞`），还是与其等效的Unicode转义符（如：`\u221e`）时，取决于那种方式可以使得代码更易于阅读和理解。

### 二、Java源文件代码结构

源文件由以下部分顺序构成：

 1. 许可证或版权信息（如果存在）
 2. 包声明语句
 3. 导入其他依赖类语句
 4. 源文件主类

#### 2.1 许可证或版权信息
 
如果软件具有许可证或版权信息，在源文件中首先以注释的形式写入此信息。

#### 2.2 包声明语句

一条包声明语句占一行。

#### 2.3 导入语句

##### 2.3.1 不能使用通配符进行导入

##### 2.3.2 一条导入语句占一行

##### 2.3.3 排序与间隔

导入语句按如下方式进行分组区分并排序，每组导入语句使用空行分开。

 1. 所有的静态导入属于同一组（静态导入：`import static ...`）
 2. `java` 类导入
 3. `javax` 类导入
 4. 第三方类导入，每一个主包属于一个分组并按ASCII进行排序
   - 例如：`android, com, junit, org, sun`
 5. `org.gbros`或 `com.perpetual`
 
#### 2.4 类定义

##### 2.4.1 一个Java源文件中只能有一个主类

##### 2.4.2 类成员排序

一个java类中如果有多个构造方法或者多个同名方法，把他们放到一起

### 三、源码格式

#### 3.1 大括号

##### 3.1.1 在 `if`,`else`,`for`,`do` 和 `while`等选择语句中，大括号必须使用，不管这些语句为空还是不为空。

##### 3.1.2 大括号内部若不为空，则使用 `K & R` 风格

1. `{` 之前不进行换行
2. `{` 之后进行换行
3. `}` 之后，若逻辑已终止（比如：类结束，构造方法结束。），则进行回车，否则不进行回车

`K & R`风格代码例子如下：

    return new MyClass() {
	  @Override public void method() {
        if (condition()) {
          try {
            something();
          } catch (ProblemException e) {
            recover();
          }
        } else {
          something();
        }
      }
	};

##### 3.1.3 大括号内代码块为空，则大括号 `{` 和 `}`写在一起

如：

     void doNothing(){}

#### 3.2 不同的代码块使用 *四个空格* 进行缩进，如 `K & R` 风格例子所示。

#### 3.3 一句源码占一行

每一句源码后，使用换行符

#### 3.4 列限制：80字符

每行源码字符限制为 **80 ** 字符，超过后自动换行 ,以下情况例外。

 0. 不可能满足列限制的行(例如，Javadoc中的一个长URL，或是一个长的JSNI方法参考)。
 0.  `package` 和 `import` 语句中
 0.  shell中的命令语句

#### 3.5 自动换行

 **术语说明：**一般情况下，一行长代码为了避免超出列限制(80或100个字符)而被分为多行，我们称之为自动换行(line-wrapping)。

##### 3.5.1 从哪里换行断开

自动换行的基本准则是：更倾向于在更高的语法级别处断开。

 0. 如果在非赋值运算符处断开，那么在该符号前断开(比如 +，它将位于下一行)。 这条规则也适用于以下“类运算符”符号：点分隔符(.)，类型界限中的&（\<T extends Foo & Bar>)，catch块中的管道符号(catch (FooException | BarException e)
 0. 如果在赋值运算符处断开，通常的做法是在该符号后断开(比如=，它与前面的内容留在同一行)。这条规则也适用于foreach语句中的分号。
 0. 方法名或构造函数名与左括号留在同一行。
 0. 逗号(,)与其前面的内容留在同一行。
 
##### 3.5.2 自动换行时缩进4个空格

自动换行时，第一行后的每一行比第一行多缩进4个空格。

#### 3.6 空白

##### 3.6.1 空行

以下情况需要使用一个空行：

 0. 类内连续的成员之间：字段，构造函数，方法，嵌套类，静态初始化块，实例初始化块。
    - 例外：两个连续字段之间的空行是可选的，用于字段的空行主要用来对字段进行逻辑分组。
 0. 在函数体内，语句的逻辑分组间使用空行。
 0. 类内的第一个成员前或最后一个成员后空行。
 0. 要满足本文档中其他节的空行要求(比如3.3节：import语句)。
 0. 多个连续的空行是不允许的。

##### 3.6.2 空格

除了语言需求和其它规则，并且除了文字，注释和Javadoc用到单个空格，单个ASCII空格也出现在以下几个地方：

 0. 分隔任何保留字与紧随其后的左括号(()(如if, for catch等)；
 0. 分隔任何保留字与其前面的右大括号(})(如else, catch)；
 0. 在任何左大括号前({)，两个例外：
   - @SomeAnnotation({a, b})(不使用空格)；
   - String[][] x = foo;(大括号间没有空格)。
 0. 在任何二元或三元运算符的两侧。这也适用于以下“类运算符”符号：
   - 类型界限中的&(\<T extends Foo & Bar>)。
   - catch块中的管道符号(catch (FooException | BarException e)。
   - foreach语句中的分号。
 0. 在`,`,` :`,` ;`及右括号`)`后加空格；
 0. 如果在一条语句后做注释，则双斜杠(//)左边都要空格。；

注意：`这个规则并不要求或禁止一行的开关或结尾需要额外的空格，只对内部空格做要求。`

#### 3.7 用小括号来限定组

超过两组必须使用小括号限定组。

#### 3.8 具体结构

##### 3.8.1 枚举类

枚举常量间用逗号隔开，必须换行。

没有方法和文档的枚举类可写成数组初始化的格式：

	private enum Suit { 
		CLUBS, 
		HEARTS, 
		SPADES, 
		DIAMONDS 
	}

由于枚举类也是一个类，因此所有适用于其它类的格式规则也适用于枚举类。

##### 3.8.2 变量声明

###### 3.8.2.1 每次只声明一个变量

不要使用组合声明，比如int a, b;。

###### 3.8.2.2 需要时才声明，并尽快进行初始化

不要在一个代码块的开头把局部变量一次性都声明了(这是c语言的做法)，而是在第一次需要使用它时才声明。 局部变量在声明时最好就进行初始化，或者声明后尽快进行初始化。

##### 3.8.3 数组

###### 3.8.3.1 数组初始化：可写成块状结构

数组初始化可以写成块状结构，比如，下面的写法都是OK的：

		//非注释
		new int[] {
		  0, 1, 2, 3 
		}
		
		//需要注释
		new int[] {
		  0,
		  1,
		  2,
		  3
		}
		
		//矩阵
		new int[] {
		  0,1,
		  2,3
		}

###### 3.8.3.2 非C风格的数组声明

中括号是类型的一部分：String[] args， 而非String args[]。

##### 3.8.4 switch语句

###### 3.8.4.1 缩进

与其它块状结构一致，switch块中的内容一个缩进。

每个switch标签后新起一行，再一个缩进，写下一条或多条语句。

###### 3.8.4.2 Fall-through：注释

在一个switch块内，每个语句组要么通过break, continue, return或抛出异常来终止，要么通过一条注释来说明程序将继续执行到下一个语句组， 任何能表达这个意思的注释都是OK的(典型的是用// fall through)。这个特殊的注释并不需要在最后一个语句组(一般是default)中出现。示例：

	switch (input) {
	  case 1:
	  case 2:
	    prepareOneOrTwo();
	    // fall through
	  case 3:
	    handleOneTwoOrThree();
	    break;
	  default:
	    handleLargeNumber(input);
	}

###### 3.8.4.3 default的情况要写出来

每个switch语句都包含一个default语句组，即使它什么代码也不包含。

##### 3.8.5 注解(Annotations)

注解紧跟在文档块后面，应用于类、方法和构造函数，一个注解独占一行。这些换行不属于自动换行，因此缩进级别不变。

##### 3.8.6 注释

###### 3.8.6.1 块注释风格

块注释与其周围的代码在同一缩进级别。它们可以是/* ... */风格，也可以是// ...风格。对于多行的/* ... */注释，后续行必须从*开始， 并且与前一行的*对齐。以下示例注释都是OK的。

	/*
	 * This is                   
	 * okay.                      
	 */
	 
	 // And so
	 // is this.
	 
	 /* Or you can
	  * even do this. */
	 
注释不要封闭在由星号或其它字符绘制的框架里。


> 在写多行注释时，如果你希望在必要时能重新换行(即注释像段落风格一样)，那么使用/* ... */。

##### 3.8.7 修饰语法

类和成员的modifiers如果存在，则按Java语言规范中推荐的顺序出现。

	public protected private abstract static final transient volatile synchronized native strictfp

### 四、命名约定

#### 4.1 对所有标识符都通用的规则

标识符只能使用ASCII字母和数字，因此每个有效的标识符名称都能匹配正则表达式 `\w+` 。

其它编程语言风格中使用的特殊前缀或后缀，如 `name_`, `mName`, `s_name`和`kName`，在Java编程风格中都不再使用。

#### 4.2 标识符类型的规则

##### 4.2.1 包名

包名全部小写，连续的单词只是简单地连接起来，不使用下划线。

##### 4.2.2 类名

类名都以 `UpperCamelCase` 风格编写。

类名通常是名词或名词短语，接口名称有时可能是形容词或形容词短语。现在还没有特定的规则或行之有效的约定来命名注解类型。

测试类的命名以它要测试的类的名称开始，以Test结束。例如，`HashTest` 或 `HashIntegrationTest`。

#### 4.2.3 方法名

方法名都以 `lowerCamelCase` 风格编写。

方法名通常是动词或动词短语。

#### 4.2.4 常量名

常量名命名模式为CONSTANT_CASE，全部字母大写，用下划线分隔单词。那，到底什么算是一个常量？

每个常量都是一个静态final字段，但不是所有静态final字段都是常量。在决定一个字段是否是一个常量时， 考虑它是否真的感觉像是一个常量。例如，如果任何一个该实例的观测状态是可变的，则它几乎肯定不会是一个常量。 只是永远不打算改变对象一般是不够的，它要真的一直不变才能将它示为常量。

	// Constants
	static final int NUMBER = 5;
	static final ImmutableList<String> NAMES = ImmutableList.of("Ed", "Ann");
	static final Joiner COMMA_JOINER = Joiner.on(',');  // because Joiner is immutable
	static final SomeMutableType[] EMPTY_ARRAY = {};
	enum SomeEnum { ENUM_CONSTANT }
	
	// Not constants
	static String nonFinal = "non-final";
	final String nonStatic = "non-static";
	static final Set<String> mutableCollection = new HashSet<String>();
	static final ImmutableSet<SomeMutableType> mutableElements = ImmutableSet.of(mutable);
	static final Logger logger = Logger.getLogger(MyClass.getName());
	static final String[] nonEmptyArray = {"these", "can", "change"};

这些名字通常是名词或名词短语。

#### 4.2.5 非常量字段名

非常量字段名以`lowerCamelCase`风格编写。

这些名字通常是名词或名词短语。

#### 4.2.6 参数名

参数名以`lowerCamelCase`风格编写。

参数应该避免用单个字符命名。

#### 4.2.7 局部变量名

局部变量名以`lowerCamelCase`风格编写，比起其它类型的名称，局部变量名可以有更为宽松的缩写。

虽然缩写更宽松，但还是要避免用单字符进行命名，除了临时变量和循环变量。

即使局部变量是final和不可改变的，也不应该把它示为常量，自然也不能用常量的规则去命名它。

#### 4.2.8 类型变量名

类型变量可用以下两种风格之一进行命名：

 - 单个的大写字母，后面可以跟一个数字(如：E, T, X, T2)。
 - 以类命名方式(5.2.2节)，后面加个大写的T(如：RequestT, FooBarT)。

#### 4.3 驼峰式命名法(CamelCase)

**驼峰式命名法** 分大驼峰式命名法(`UpperCamelCas`e)和小驼峰式命名法(`lowerCamelCase`)。 有时，我们有不只一种合理的方式将一个英语词组转换成驼峰形式，如缩略语或不寻常的结构(例如"IPv6"或"iOS")。Google指定了以下的转换方案。

名字从`散文形式(prose form)`开始:

 1. 把短语转换为纯ASCII码，并且移除任何单引号。例如："Müller’s algorithm"将变成"Muellers algorithm"。
 2. 把这个结果切分成单词，在空格或其它标点符号(通常是连字符)处分割开。
   - 推荐：如果某个单词已经有了常用的驼峰表示形式，按它的组成将它分割开(如"AdWords"将分割成"ad words")。 需要注意的是"iOS"并不是一个真正的驼峰表示形式，因此该推荐对它并不适用。
 3. 现在将所有字母都小写(包括缩写)，然后将单词的第一个字母大写：
   - 每个单词的第一个字母都大写，来得到大驼峰式命名。
   - 除了第一个单词，每个单词的第一个字母都大写，来得到小驼峰式命名。
 4. 最后将所有的单词连接起来得到一个标识符。
  
    示例：

		Prose form                Correct               Incorrect
		------------------------------------------------------------------
		"XML HTTP request"        XmlHttpRequest        XMLHTTPRequest
		"new customer ID"         newCustomerId         newCustomerID
		"inner stopwatch"         innerStopwatch        innerStopWatch
		"supports IPv6 on iOS?"   supportsIpv6OnIos     supportsIPv6OnIOS
		"YouTube importer"        YouTubeImporter
		                          YoutubeImporter*
加星号处表示可以，但不推荐。

> Note：在英语中，某些带有连字符的单词形式不唯一。例如："nonempty"和"non-empty"都是正确的，因此方法名checkNonempty和checkNonEmpty也都是正确的。

### 五、编程实践

#### 5.1 @Override : 尽可能使用

只要是合法的，就把`@Override`注解给用上。

#### 5.2 捕获的异常：不能忽视

除了下面的例子，对捕获的异常不做响应是极易出错的。(典型的响应方式是打印日志，或者如果它被认为是不可能的，则把它当作一个`AssertionError`重新抛出。)

如果它确实是不需要在catch块中做任何响应，需要做注释加以说明(如下面的例子)。

	try {
	  int i = Integer.parseInt(response);
	  return handleNumericResponse(i);
	} catch (NumberFormatException ok) {
	  // it's not numeric; that's fine, just continue
	}
	return handleTextResponse(response);

例外：在测试中，如果一个捕获的异常被命名为expected，则它可以被不加注释地忽略。下面是一种非常常见的情形，用以确保所测试的方法会抛出一个期望中的异常， 因此在这里就没有必要加注释。

	try {
	  emptyStack.pop();
	  fail();
	} catch (NoSuchElementException expected) {
	}

#### 5.3 静态成员：使用类进行调用

使用类名调用静态的类成员，而不是具体某个对象或表达式。

	Foo aFoo = ...;
	Foo.aStaticMethod(); // good
	aFoo.aStaticMethod(); // bad
	somethingThatYieldsAFoo().aStaticMethod(); // very bad

#### 5.4 Finalizers: 禁用

极少会去重载`Object.finalize`。

> Tip：不要使用finalize。如果你非要使用它，请先仔细阅读和理解Effective Java 第7条款：“Avoid Finalizers”，然后不要使用它。

### 六、Javadoc

#### 6.1 格式

##### 6.1.1 一般形式

Javadoc块的基本格式如下所示：

	/**
	 * Multiple lines of Javadoc text are written here,
	 * wrapped normally...
	 */
	public int method(String p1) { ... }

或者是以下单行形式：

	/** An especially short bit of Javadoc. */

基本格式总是OK的。当整个Javadoc块能容纳于一行时(且没有Javadoc标记@XXX)，可以使用单行形式。

##### 6.1.2 段落

空行(即，只包含最左侧星号的行)会出现在段落之间和Javadoc标记(@XXX)之前(如果有的话)。 除了第一个段落，每个段落第一个单词前都有标签`<p>`，并且它和第一个单词间没有空格。

##### 6.1.3 Javadoc标记

标准的Javadoc标记按以下顺序出现：`@param, @return, @throws, @deprecated`, 前面这4种标记如果出现，描述都不能为空。 当描述无法在一行中容纳，连续行需要增加一个缩进。

##### 6.2 摘要片段（一年后启用英文注释后按此标准执行）

每个类或成员的Javadoc以一个简短的摘要片段开始。这个片段是非常重要的，在某些情况下，它是唯一出现的文本，比如在类和方法索引中。

这只是一个小片段，可以是一个名词短语或动词短语，但不是一个完整的句子。它不会以`A {@code Foo} is a...`或`This method returns...`开头, 它也不会是一个完整的祈使句，如`Save the record...`。然而，由于开头大写及被加了标点，它看起来就像是个完整的句子。

> Tip：一个常见的错误是把简单的Javadoc写成/** @return the customer ID */，这是不正确的。它应该写成/** Returns the customer ID. */。

#### 6.3 哪里需要使用Javadoc

至少在每个public类及它的每个public和protected成员处使用Javadoc，以下是一些例外：

##### 6.3.1 例外：不言自明的方法

 1. 对于简单明显的方法如getFoo，Javadoc是可选的(即，是可以不写的)。这种情况下除了写“Returns the foo”，确实也没有什么值得写了。

 2. 单元测试类中的测试方法可能是不言自明的最常见例子了，我们通常可以从这些方法的描述性命名中知道它是干什么的，因此不需要额外的文档说明。

> Tip：如果有一些相关信息是需要读者了解的，那么以上的例外不应作为忽视这些信息的理由。例如，对于方法名getCanonicalName， 就不应该忽视文档说明，因为读者很可能不知道词语canonical name指的是什么。

##### 6.3.2 例外：重载

如果一个方法重载了超类中的方法，那么Javadoc并非必需的。

##### 6.3.3 可选的Javadoc

对于包外不可见的类和方法，如有需要，也是要使用Javadoc的。如果一个注释是用来定义一个类，方法，字段的整体目的或行为， 那么这个注释应该写成Javadoc，这样更统一更友好。


