<script setup>
</script>

<template>
  <div class="container">
      <div class="card">
          <div class="card-header">
              <h3 class="card-header-title">待辦事項產生器</h3>
          </div>
          <div class="card-body">
              <form @submit.prevent="onSubmit">
                  <div class="form-group">
                      <label for="todoTitleInput">標題</label>
                      <input v-model="todoTitle" id="todoTitleInput" type="text" class="form-control" placeholder="請輸入標題" required>
                  </div>
                  <div class="form-group">
                      <label for="todoColorInput">顏色</label>
                      <select v-model="todoColor" name="todoColorInput" id="todoColorInput" class="form-control" required>
                          <option value="normal">普通</option>
                          <option value="warning">緊急</option>
                          <option value="danger">重要</option>
                      </select>
                  </div>
                  <div class="form-group">
                      <button class="btn">產生待辦項目</button>
                  </div>
              </form>
              <div>
                  <!-- <p>todoTitle: {{ todoTitle }}</p>
                  <p>todoColor: {{ todoColor }}</p>
                  <p>todoList: {{ todoList }}</p> -->
              </div>
              <!-- <h5>{{ todoList.length > 0 ? `待辦清單內有${todoList.length}個資料` : "清單內無資料"  }}</h5> -->
              <h5>{{ showTodoListHint }}</h5>
          </div>
          <div class="card-footer">
              <div v-for="(todo, idx) in todoList" :key="todo.createdAt" class="todo-item">
                  <div class="todo-item-title-group"> 
                      <div :class="['box', `box-${todo.color}`]"></div>
                      <h4>{{ todo.title }}</h4>
                  </div>
                  <div class="todo-button-group">
                      <button @click="removeTodo(idx)" class="remove-todo-btn">&times;</button>
                  </div>
              </div>
          </div>
      </div>
      
  </div>
</template>

<script>
export default {
    data(){
        return {
            // 元件內要使用的資料
            todoTitle: "ABC",
            todoColor: "normal",
            todoList: []
        }
    },
    computed: {
        showTodoListHint() {
            const todoLen = this.todoList.length;
            if (todoLen > 0) {
                return `清單內有${todoLen}個項目`
            } else {
                return "清單內無項目"
            }
        }
    },
    methods: {
        onSubmit() {
            console.log("Vue元件", this);
            console.log("表單被送出了!");
            // 描述一個待辦項目
            const todo = {
                title: this.todoTitle,
                color: this.todoColor,
                createdAt: new Date().getTime()
            };
            // 將待辦項目新增到待辦清單內
            this.todoList.push(todo);
        },
        removeTodo(idx) {
            // 透過索引移除1個索引為idx的資料
            this.todoList.splice(idx, 1);
        }
    }
}
</script>