<template>
  <div class="container flex justify-center align-center">
    <div class="card flex flex-column align-center">
      <h1>
        LOGIN (user: admin , pass: admin)
      </h1>
      <div class="login">
        <div class="row mb-6">
          <div class="col">
            Email :
          </div>
          <div class="col">
            <input type="text" v-model="form.email">
          </div>
        </div>
        <div class="row mb-6">
          <div class="col">
            Pass :
          </div>
          <div class="col">
            <input type="text" v-model="form.password">
          </div>
        </div>
        <div class="flex justify-end">
          <button
            class="btn"
            @click="update()">
            submit
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Login',
  props: {
    form: {
      type: Object,
      default: () => ({})
    }
  },
  methods: {
    update () {
      this.$emit('submit', this.form)
    }
  }
}
</script>

<style scoped>
  h1 {
    margin-top: 0px;
    margin-bottom: 60px;
  }
  .flex {
    display: flex;
  }
  .flex-column {
    flex-direction: column;
  }
  .justify-center {
    justify-content: center;
  }
  .justify-end {
    justify-content: flex-end;
  }
  .align-center {
    align-items: center;
  }
  .card {
    border: 4px solid black;
    padding: 60px 24px;
    width: 500px;
  }
  .container {
    padding: 0 32px;
    height: 100vh;
  }
  .login {
    width: 300px;
    border: 1px solid black;
    padding: 24px;
  }
  .row {
    display: flex;
    width: 100%;
  }
  .col {
    width: 50%;
  }
  .mb-6 {
    margin-bottom: 24px;
  }
  .btn {
    padding: 8px 16px;
    background-color: white;
  }
  .btn:hover {
    background-color: lightgray;
  }
</style>