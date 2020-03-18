<template>
  <b-container>
    <b-list-group>
      <b-list-group-item>
        <b-row class="justify-content-md-center">
          <b-col>
            <b-button variant="light" size="lg">Status</b-button>
          </b-col>
          <b-col class="col-8">
            <b-button variant="light" size="lg">
              Todos
              <b-badge variant="primary">{{todos.filter(todo => !todo.completed).length}}</b-badge>
            </b-button>
          </b-col>
          <b-col>
            <b-button variant="light" size="lg">Delete</b-button>
          </b-col>
        </b-row>
      </b-list-group-item>
    </b-list-group>
    <b-list-group>
      <b-list-group-item :key="todo.id" v-for="todo in todos">
        <div class="row justify-content-md-center">
          <div class="col">
            <b-form-checkbox v-model="todo.completed"></b-form-checkbox>
          </div>
          <div class="col-8" bg-color="red">{{todo.title}}</div>
          <div class="col">
            <b-button variant="danger">
              <b-icon icon="trash"></b-icon>
            </b-button>
          </div>
        </div>
      </b-list-group-item>
    </b-list-group>
  </b-container>
</template>

<script>
export default {
  name: "Todos",
  props: ["todos"]
};
</script>

<style scoped>
</style>