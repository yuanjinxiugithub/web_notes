### React 技术栈

babel ： 下一代 JavaScript 编译器

ES6 ： JavaScript 语言的下一代标准

FireBase 实时后端数据库，能够帮助开发者很快的写出web端和移动端应用。

React UI  - JXS 语法

JSX -- React使用其来代替常规的JavaScript。
 优势：
    1 执行更快，它在编译为javascript后进行了优化。
		2 类型安全的，在编译过程中就可以发现错误。
		3 使用JXS编写模板更加简单快速。

React-Router -- 基于 React之上的强大的路路由库，它可以让你向应用中快速添加视图和数据流。

Redux 不是为了方便JavaScript，小型项目中可以不使用Redux,反而会增加项目的复杂度。但是在大型前端项目中，redux能够友好地管理网站中的状态。
   Redux的核心思想：
	    Redux将所有的state构建为state树，保存到一个对象中；将所有可能的行为封装到action中，然后编写reducer函数分别处理action,根据action的种类来更改state从而实现state的管理和控制。


Less(Leaner Style Sheets)  是一门向后兼容的CSS扩展语言，丰富了CSS选择器的种类，减少CSS的代码量。支持选择器之间的嵌套，使得css更具有逻辑，更易维护，也更符合React组件化的思想。既可以在客户端上运行也可以在服务器端运行。

Sass 是一种动态样式语言，sass语法属于缩排语法。

Less 和Sass 的区别：
 Less是基于 JavaScript，是在客户端处理的。
 Sass是基于Ruby的，是在服务器端处理的。
 关于变量在Less和Sass中的唯一区别就是Less用@，Sass用$;

 什么叫钩子：
     钩子函数和回调函数一般用来处理事件‘回调’;
     回调函数是你留一个处理方法的事件，事件发生后会自动执行你留下调处理的方法。
	   钩子函数好比找了个代理，监视事件是否发生，如果发生了这个代理就执行你的事件处理方法;在这个过程中，代理就是钩子函数。

### react 简介
    React 是一个声明式 高效 灵活的用于构建用户界面的javascript库，使用React可以将一些简短，独立的代码片段组合成复杂的UI界面

	React 的核心概念只有2点：
	1. 声明式渲染（Declaeative)
	2. 基于组件（Component-Based）

	声明式编程：告诉机器你想要做什么，让机器想出如何去做。
	
	命令式编程：告诉机器如何去做事情

	React声明式渲染：React 模板写在JS文件中，而不是html的script标签中，能使用所有的JS语法，而不是只有模板语法，所以更加灵活。
	     
 ### react 的生命周期
  React的生命周期分为三种 1 初始化 2 更新 3 销毁
  初始化阶段：（挂载阶段）
	  1. constructor
		     ES6 class的构造函数，接受一个props属性对象，props由父组件中传入，如果父组件为传入，则指向自身。
				  通常用于初始化state，以及绑定事件处理方法等工作。
		2. componentWillMount
		    组件被挂载到DOM前，只会被调用1次，一般用于更靠前的constructor代替。

		3. render
		    组件的唯一方法，根据组件的props与state返回一个React元素，用于描述组件的UI.创建虚拟dom，进行diff算法，更新dom树都在此进行。 此时就不能更改state.

		4. componentDidMount
		    组件渲染之后调用，只调用一次。只在客户端。
			在其中调用this.setState() 会引起组件重新渲染，组件本次的更新还没有执行完成，又会进行新一轮的更新，导致不断循环更新，进入死循环。副作用操作，通常用于向后端请求数据。

		更新阶段: 
		1. componentWillReceiveProps(nextProps)
		    组件初始化时不调用，组件接受新的props时调用。

		2. shouldComponentUpdate(nextProps,nextState)
		   react 性能优化非常重要的一环。组件接受新的state或者props时调用,我们可以设置在此对比前后两个props和state是否相同，如果相同则返回false阻止更新，因为相同的属性状态一定会生成相同的dom树，这样就不需要创造新的dom树和旧的dom树进行diff算法对比，节省大量性能。

		   总而言之，判断组件是否需要继续更新，减少不必要的渲染，优化。

		3. componentWillUpdate(nextProps, nextState)
		    组件初始化时不调用，只有组件将要更新时才调用，此时可以修改state

		4. render() 
		   重新渲染组件		

		5. componentDidUpdate()
		   组件初始化时不调用，组件更新完成后调用，此时可以获取dom节点。  		

		 卸载阶段：
		 1 componentWillUnmount()
           组件将要卸载时调用，一些事件监听和定时器需要在此时清除。

### React 中的专业用语

1. 单页面应用 （SPA)  是一个应用程序，它可以加载单个HTML页面,以及运行应用程序所需的所有必要资源（例如JavaScript和Css）。

2 Compiler(编译器)
   JavaScript Compiler接受JavaScript代码，然后对其进行转换。 React最常用的Compiler是babel

3 props 
   props是React组件的输入，它们是从父组件向下传递子组件的数据。
   props是只读的，不应以任何方式修改它们。
   如果想要修改某些值，以响应用户输入或网络响应，请使用state来替换

   props.children 每个组件可以获取props.children. 包含组件的开始标签和结束标签之间的内容。  

### React 高级指引
1. 无障碍辅助功能
    1.1 React Fragement     有时，语义化HTML会被破坏，可以使用ReactFragements来组合各个组件。
		    Fragements React中一个常见模式是一个组件返回多个元素。Fragments允许你将子列表分组，而无需向DOM节点中添加额外节点。

				短语法：可以使用一种新的， 且更简短的语法来声明Fragments.看起来像空标签：<> </>

				带Key的Fragments
		    
    1.2 使用程序管理焦点
		    我们的React应用在运行时会持续更改HTML DOM,有时会导致键盘焦点的丢失或者是被设置到了意料之外的元素上。如果是这样我们要以编程的方式让键盘聚焦到正确的方向上。

			  我们可以用 DOM元素的Refs 在React中设置焦点。

				DOM元素Refs and the DOM
				Refs提供了一种方式，允许我们访问DOM节点或在render方法中创建的React元素。
				在某些情况下，需要在典型数据流之外强制修改子组件。被修改的子组件可能是一个React组件的实例，也可能是一个DOM元素。

				如何使用Refs：
				下面是几个适合使用refs的情况：
				1 管理焦点，文本选择或媒体播放。
				2 触发强制动画。
				3 集成第三方DOM库。
				避免使用Refs来做任何可以通过声明式实现来完成的事情。
				认真考虑state属性应该被安排在哪个组件层中。----	涉及到 状态提示	 

				如何将DOM Refs暴露给父组件
				在极少情况下，你可能希望在父组件中引用子节点的DOM节点。通常不建议这样做，因为它会打破组件的封装，但它偶尔可用于触发焦点或测量子DOM节点的大小或位置。


		1.3 代码分割
		    webpack Browserify这类构建工具来打包文件。打包是一个将文件引入并合并到一个单独文件的过程，最终形成一个bundle.接着在页面上引入该bundle，整个应用即可一次性加载。


		1.4 Context
        Context 提供一个无需为每层组件手动添加props,就能在组件树间进行数据传递的方法。
				 在一个典型的React应用中，数据是通过props属性自上而下（父向子）进行传递的，但这种做饭对于某些类型的属性而言是及其繁琐的。Context提供了一种在组件之间共享此类值的方式,而不必显示地通过组件树的逐层传递props.
		    引申： js中的一种属性所包含的全部状态。	

    1.5 Refs转发
		    Ref转发是一项将ref自动地通过组件传递到其一组件的技巧。对于大多数应用中的组件来说， 

		1.6 高阶组件
		高阶组件（HOC）是React中用于复用组件逻辑的一种高级技巧。HOC自身不是React API 的一部分，它是一种基于React的组合特性而形成的设计模式。
		参数为组件，返回值为新组件的函数。		



### 对虚拟DOM的理解


### Redux
#### 简介
    JavaScript 状态管理，提供可预测化的状态管理.
### 三大原则
   1 单一数据源： 整个应用的state被存储在一棵object tree中，并且这个object tree 只存在于唯一一个Store中。组件可以派发（dispatch）行为（action）给store,而不是直接通知其他组件，组件内部通过订阅store 中的状态 state 来刷新自己的视图。
   2 只保持只读状态:state是只读的，唯一改变state的方法就是触发action,action 是一个用于描述以发生时间的普通对象。
   3 数据改变只能通过纯函数来执行:为了描述action如何改变state tree,需要编写reducers


### React 性能优化
#### Key 
 使用key的原因是能够让组件保持结构的稳定性。 React DOM diff算法,在实际比节点更新的过程中带有唯一性的 key能够让React更快的定位到变更的节点，从而可以做到最小化更新。
 
#### 数据对比
 我们应该做到让组件避免在非必要的情况下重新渲染，就能使开发出的组件性能更良好。

 知识点1：React 数据比较采用 浅比较；

 知识点2：shouldComponentUpdate 方法来判断是否进行组件渲染。，从而更高的提高页面性能。这个方式在每次props和state变化的时候执行，框架对这个方法的默认返回值是ture,可以复写这个方法 手动进行更新，在更新逻辑清楚的情况下。
  shouldComponentUpdate(nextProps, nextState) {
        return this.props.itemName !== nextProps.itemName;
    }

知识点3：pureComponent
要达到性能优化的目的，有时候也不必手动实现shouldComponentUpdate. 只要让你的组件集成自React.PureComponent即可，它可以内置了浅比算法。

#### 关于箭头函数
直接在组件上写箭头函数虽然写法简便，但由于每次渲染的时候都会重新生成该函数，会导致性能受损。即使组件中其他的props或state没有变更，由于使用了内联的箭头函数也会触发重新渲染。为了避免这个情况的发生，我们可以先声明好时间监听函数后，然后在拿到其他引用传给组件。
class Button extends React.Component {
	handleClick = () => {
		console.log('hello, scq000');
	}
	
	render() {
		return <button onClick={this.handleClick}>click</button>
	}
}

#### useCallBack
 如果我们使用的是函数式组件，React16 中的useCallBack的hook为我们提供了一种新思路；
 将箭头函数出入 useCallBack 方法中，这个一个高阶函数，它会返回一个记忆化的方法。这个方法只有当它所依赖的props或state变化的时候才更新


 #### React.Memo
 针对Functional组件来说，由于缺少shouldComponentUpdate方法，可以考虑用React.Memo来优化组件性能。 React.Memo是一个高阶组件，它内置了useMemo方法来缓存整个组件

#### 不可变数据Immutable
Immutable 是 facebook封装的抽象数据结构，由于其结构的不变性和共享性。能够让引用对象在对比的时候更加快速
 
		





	 			





		









