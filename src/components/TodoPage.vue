<template>
<div class="container">
  <h2>Todo List</h2>
  <div class="input-group" style="margin-bottom:10px;">
    <input type="text" class="form-control" placeholder="할일을 입력하세요">
    <span class="input-group-btn">
      <button class="btn btn-default" type="button">추가</button>
    </span>
  </div>
  <ul class="list-group">
    <li class="list-group-item" v-for="(todo, index) in todos">
      {{todo.name}}
      <div class="btn-group pull-right" 
        style="font-size: 12px; line-height: 1;">
        <button type="button" 
        class="btn-link dropdown-toggle" 
        data-toggle="dropdown" 
        aria-haspopup="true" 
        aria-expanded="false">
          더보기<span class="caret"></span>
        </button>
        <ul class="dropdown-menu">
          <li>
            <a href="#" @click="deleteTodo(index)">삭제</a>
          </li>
        </ul>
      </div>
    </li>
  </ul>
</div>
</template>

<script>
export default {
  name: 'TodoPage',
  data () {
    return {
      todos: [
        {
          name:'청소'
        },
        {
          name:'블로그 쓰기'
        },
        {
          name:'밥먹기'
        },
        {
          name:'안녕'
        }
      ]
    }
  },
  methods:{
    deleteTodo(i){
      this.todos.splice(i,1);
    }
  }
}
</script>