<template>
  <div class="hello">
    <table>
      <tr>
        <td height="200px" colspan="4">{{result}}</td>
      </tr>
      <tr>
        <td><button @click="numb(7)">7</button></td>
        <td><button @click="numb(8)">8</button></td>
        <td><button @click="numb(9)">9</button></td>
        <td><button @click="">x</button></td>
      </tr>
      <tr>
        <td><button @click="numb(4)">4</button></td>
        <td><button @click="numb(5)">5</button></td>
        <td><button @click="numb(6)">6</button></td>
        <td><button @click="" style="width:100%;">-</button></td>
      </tr>
      <tr>
        <td><button @click="numb(1)">1</button></td>
        <td><button @click="numb(2)">2</button></td>
        <td><button @click="numb(3)">3</button></td>
        <td><button @click="op('+')">+</button></td>
      </tr>
      <tr>
        <td colspan="2"><button @click="" style="width:100%;">0</button></td>
        <td><button @click="" style="width:100%;">.</button></td>
        <td><button @click="">=</button></td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: 'hello',
  data () {
    return {
      result: '',
      num: 0,
      text: ''
    }
  },
  methods: {
    numb: function (num) {
      this.result = this.result * 1 + num
    }
  }
}
</script>

<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}

table {
  margin: auto;
  border-color: #b5b4ba;
}

table td{
  border: 1px solid #CCC;
}

button {
    background-color: #e1e0e6; /* Green */
    border: none;
    color: white;
    padding: 20px 32px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 20px;
    font-family: 'Microsoft JhengHei UI';
    cursor: pointer;
}
</style>
