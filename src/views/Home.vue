<template>
  <div>
    <h1>Welcome to {{title2}}!</h1>
    <input type="text" v-model="input1" />
    <button type="button" @click="getinput1">Get</button>
    <button type="button" @click="setinput1">Set</button>

    <select class="form-control" v-model="region">
      <option v-for="(data, index) in options" :key="index" :value="data.v"  >{{data.t}}</option>
    </select>
  </div>
</template>
<script>
export default {
  data() {
    return {
      title: "vuejs 너무재밌다",
      title2 : "My blog",
      input1 : "value = v-model 입니다",
      options: [
        {v: "S", t: "Seoul"},
        {v: "J", t: "Jeju"},
        {v: "B", t: "Busan"},
      ],
      region: "J"
    };
  },

  methods: {
    getinput1() {
      alert(this.input1);
    },
    setinput1() {
      this.input1 = "12345";
    }
  },
  watch: {
    input1() {
      console.log(this.input1)
    }
  },

  beforeCreate() {
    console.log("beforeCreate")
  },
  created() {
    console.log("created")

  },
  beforeMount() {
    console.log("beforeMount")

  },
  mounted() {
    console.log("mounted")

  },
  beforeUpdate() {
    console.log("beforeUpdate")

  },
  updated() {
    console.log("updated")

  }
};
</script>