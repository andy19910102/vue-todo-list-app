<script setup>
</script>

<template>
  <div class="container">
      <div class="card">
          <div class="card-header">
              <h3 class="card-header-title">待辦事項產生器</h3>
          </div>
          <div class="card-body">
              <form>
                  <div class="form-group">
                      <label for="todoTitleInput">標題</label>
                      <input id="todoTitleInput" type="text" class="form-control" placeholder="請輸入標題" required>
                  </div>
                  <div class="form-group">
                      <label for="todoColorInput">顏色</label>
                      <select name="todoColorInput" id="todoColorInput" class="form-control" required>
                          <option value="normal">普通</option>
                          <option value="warning">緊急</option>
                          <option value="danger">重要</option>
                      </select>
                  </div>
                  <div class="form-group">
                      <button class="btn">產生待辦項目</button>
                  </div>
              </form>
          </div>
          <div class="card-footer">
              <div class="todo-item">
                  <div class="todo-item-title-group"> 
                      <div class="box box-normal"></div>
                      <h4>早起跑步</h4>
                  </div>
                  <div class="todo-button-group">
                      <button class="remove-todo-btn">&times;</button>
                  </div>
              </div>
              <div class="todo-item">
                  <div class="todo-item-title-group"> 
                      <div class="box box-warning"></div>
                      <h4>採買食品</h4>
                  </div>
                  <div class="todo-button-group">
                      <button class="remove-todo-btn">&times;</button>
                  </div>
              </div>
              <div class="todo-item">
                  <div class="todo-item-title-group"> 
                      <div class="box box-danger"></div>
                      <h4>準備簡報</h4>
                  </div>
                  <div class="todo-button-group">
                      <button class="remove-todo-btn">&times;</button>
                  </div>
              </div>
          </div>
      </div>
      
  </div>
</template>
