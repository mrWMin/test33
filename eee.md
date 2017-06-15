#redux

	解决数据传递问题，组件状态管理框架，运用了flux框架，提供了解决状态管理的方法，是一种模式，而不是实现
	stroe对象，所有的数据都存到stroe里面，作为整个组件的最上层组件，只负责数据存储。任何的子组件都能够取到数据
###store
	Store 就是保存数据的地方，你可以把它看成一个容器。整个应用只能有一个 Store。
	Redux 提供createStore这个函数，用来生成 Store。
	import { createStore } from 'redux';
	const store = createStore(fn);
###state
	Store对象包含所有数据。如果想得到某个时点的数据，就要对 Store 生成快照。这种时点的数据集合，就叫做 State。
###Action
		State 的变化，会导致 View 的变化。但是，用户接触不到 State，只能接触到 View。所以，State 的变化必须是 View 导致的。Action 就是 View 发出的通知，表示 State 应该要发生变化了。
	Action 是一个对象。其中的type属性是必须的，表示 Action 的名称。其他属性可以自由设置，社区有一个规范可以参考。
	
	const action = {
	  type: 'ADD_TODO',
	  payload: 'Learn Redux'
	};
	上面代码中，Action 的名称是ADD_TODO，它携带的信息是字符串Learn Redux。
	可以这样理解，Action 描述当前发生的事情。改变 State 的唯一办法，就是使用 Action。它会运送数据到 Store。
###store.dispatch()
	store.dispatch()是 View 发出 Action 的唯一方法。

	import { createStore } from 'redux';
	const store = createStore(fn);
	
	store.dispatch({
	  type: 'ADD_TODO',
	  payload: 'Learn Redux'
	});
	上面代码中，store.dispatch接受一个 Action 对象作为参数，将它发送出去。
	结合 Action Creator，这段代码可以改写如下。
	
	store.dispatch(addTodo('Learn Redux'));
###Reducer
	Store 收到 Action 以后，必须给出一个新的 State，这样 View 才会发生变化。这种 State 的计算过程就叫做 Reducer。
	Reducer 是一个函数，它接受 Action 和当前 State 作为参数，返回一个新的 State。
###combineReducers
	用于 Reducer 的拆分。你只要定义各个子 Reducer 函数，然后用这个方法，将它们合成一个大的 Reducer。
###connect()
	React-Redux 提供connect方法，用于从 UI 组件生成容器组件。connect的意思，就是将ui组件和逻辑组件这两种组件连起来。
### Provider 组件
	React-Redux 提供Provider组件，可以让容器组件拿到state。
	Provider在根组件外面包了一层，这样一来，App的所有子组件就默认都可以拿到state了。
#vue
	 是一套构建用户界面的渐进式框架。与其他重量级框架不同的是，Vue 采用自底向上增量开发的设计。Vue 的核心库只关注视图层，它不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与单文件组件和 Vue 生态系统支持的库结合使用时，Vue 也完全能够为复杂的单页应用程序提供驱动
