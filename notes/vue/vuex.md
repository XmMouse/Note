# vuex
## state
1. 配合computed使用
2. mapState
```
...mapState({
   count: state => state.count, 
   count: 'count',
   count(){
       return state.count + this.name
   } 
})
...mapState(['count'])
```
## Getter
1. 配合computed使用
```
getters: {
  // ...
  getTodoById: (state) => (id) => {
    return state.todos.find(todo => todo.id === id)
  }
}
...mapGetters({
  // 把 `this.doneCount` 映射为 `this.$store.getters.doneTodosCount`
  doneCount: 'doneTodosCount'
})
```
## Mutation
1. 配合methods使用
2. store.commit
```
mutations: {
    increment (state) {
      // 变更状态
      state.count++
    }
  }
store.commit('increment')
...mapMutations([
      'increment', // 将 `this.increment()` 映射为 `this.$store.commit('increment')`

      // `mapMutations` 也支持载荷：
      'incrementBy' // 将 `this.incrementBy(amount)` 映射为 `this.$store.commit('incrementBy', amount)`
    ]),
```
## ACTION
1. 配合mehtods使用
2. store.dispatch 返回的是promise
```
actions: {
    increment (context) {
      context.commit('increment')
    }
  }
actions: {
  incrementAsync ({ commit }) {
    setTimeout(() => {
      commit('increment')
    }, 1000)
  }
}
 ...mapActions([
      'increment', // 将 `this.increment()` 映射为 `this.$store.dispatch('increment')`

      // `mapActions` 也支持载荷：
      'incrementBy' // 将 `this.incrementBy(amount)` 映射为 `this.$store.dispatch('incrementBy', amount)`
    ]),
```
## module
>默认情况下，模块内部的 action、mutation 和 getter 是注册在全局命名空间的——这样使得多个模块能够对同一 mutation 或 action 作出响应。
##  双向的计算属性
```
computed: {
  message: {
    get () {
      return this.$store.state.obj.message
    },
    set (value) {
      this.$store.commit('updateMessage', value)
    }
  }
}
```