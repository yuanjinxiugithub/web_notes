### ES6 特性
1.1 严格的代码规范
语法：
1.1.1 类型规范
			对于常量或不修饰的变量声明使用const,对于只在当前作用域下有效的变量，应使用let,不再使用var;
			优先使用const;
			将所有的const变量放在一起，将所有的let变量放在一起。
1.1.2 直接存取基本类型	
   
1.1.3 通过引用的方式取复杂类型，对所有的应用使用const;
对象 数组 函数

1.1.4 优先使用模板字符串，静态字符串一律使用单引号或反引号，不建议使用双引号；
//bad
 const a = "foobar";
 const b = 'foo'+a+'bb';
// good
const a = 'foobar';
const b = `foo${a}bar`;

1.1.5 使用字面量语法创建数组
// bad
const items = new Array();
// good
const items = [];

1.1.6 使用函数式声明而不是函数表达式
函数声明拥有函数名，在调用栈中更容易识别。并且，函数声明会整体提升，而函数表达式只会提升变量本身。始终使用箭头函数来代替函数表达式。

1.1.7 j绝对不要把参数命名为arguments,浙江覆盖函数作用域传过来的arguments对象.

类相关
1.1.8 总是使用class关键字，避免直接修改prototype,class语法更加简洁 也可容易理解。

定义类时，方法的顺序如下：
1. constructor
2. public get/set公用方法， set只传一个参数。
3. public methods 公用方法，公用相关命名使用小写驼峰命名
4. private methods 私用方法 下划线为前缀
5. private methods 私有方法




