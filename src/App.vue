<template>
   <h2 style="color: black;">
    Counter App
  </h2>
  <div class="container main">
    <div class="row">
      <div class="col">
        <form class="form m-4">
          <div >
            <input type="text" placeholder="0" class="bg-transparent" readonly v-model="counter">
          </div>
          <div class="row2">
            <div class="col-3">
              <button class="btn btn-success" @click.prevent="increase">Increase</button>
            </div>
            <div class="col-3">
              <button class="btn btn-danger"  @click.prevent="decrease">Decrease</button>
            </div>
            <div class="col-3">
              <button class="btn btn-secondary"  @click.prevent="clear">All Clear</button>
            </div>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  computed : {
    counter() {
      return this.$store.state.counter
    }
  },
  methods : {
    increase() {
      this.$store.dispatch('increaseCounter')
    },
    decrease() {
      this.$store.dispatch('decreaseCounter')
    },
    clear() {
      this.$store.dispatch("allClear")
    }
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: white;
  background-color: rgb(75, 73, 73);
  height: 100vh;
  /* margin-top: 60px; */
}

.main {
  height: 500px;
  widows: 300px;
  background-color: grey;
  border-radius: 20px;
}

input {
  height: 100px;
  width: 100px;
  border-radius: 50%;
  text-align: center;
  position: absolute;
  top: 150px;
  left: 42%;
  font-weight: 800;
  font-size: 50px;
}

.row2 {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: absolute;
  top: 280px;
  left: 40%;
}

.col-3 > button {
  width: 100px;
  margin-bottom: 15px;
}




</style>
