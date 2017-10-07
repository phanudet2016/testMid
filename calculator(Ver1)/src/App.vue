<template>
  <div class="hello">
    <table>
      <tr>
        <td height="200px" colspan="4" bgcolor="#1d181e" style="color: white;"><center><h1>{{result}}</h1></center></td>
      </tr>
      <tr>
        <td height="45px" colspan="4">  {{number1}} {{operate}} {{number2}}</td>
      </tr>
      <tr>
        <td colspan="2"><button style="background-color: #c7c8cc;" type="" name="button" @click="reset()">C</button></td>
        <td><button style="background-color: #c7c8cc;" type="button" name="button" @click="setOperate('%')">%</button></td>
        <td><button style="background-color: #fd9a18; color: white;" type="" name="button" @click="setOperate('/')">/</button></td>
      </tr>
      <tr>
        <td><button type="" name="button" @click="setNumber(7)">7</button></td>
        <td><button type="" name="button" @click="setNumber(8)">8</button></td>
        <td><button type="" name="button" @click="setNumber(9)">9</button></td>
        <td><button style="background-color: #fd9a18; color: white;" type="" name="button" @click="setOperate('*')">x</button></td>
      </tr>
      <tr>
        <td><button type="" name="button" @click="setNumber(4)">4</button></td>
        <td><button type="" name="button" @click="setNumber(5)">5</button></td>
        <td><button type="" name="button" @click="setNumber(6)">6</button></td>
        <td><button style="background-color: #fd9a18; color: white;" type="" name="button" @click="setOperate('-')">-</button></td>
      </tr>
      <tr>
      <td><button type="" name="button" @click="setNumber(1)">1</button></td>
      <td><button type="" name="button" @click="setNumber(2)">2</button></td>
      <td><button type="" name="button" @click="setNumber(3)">3</button></td>
      <td><button style="background-color: #fd9a18; color: white;" type="" name="button" @click="setOperate('+')">+</button></td>
      </tr>
      <tr>
        <td colspan="2"><button type="" name="button" @click="setNumber(0)" style="width:100%;">0</button></td>
        <td><button @click="">.</button></td>
        <td><button style="background-color: #fd9a18; color: white;" type="" name="button" @click="getResult()">=</button></td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  data () {
    return {
      number1: '',
      number2: '',
      operate: '',
      result: '',
      state: 0
    }
  },
  computed: {},
  mounted () {},
  methods: {
    setNumber: function (number) {
      if (this.state === 0) {
        this.number1 += number
      } else if (this.state === 1) {
        this.number2 += number
      }
    },
    setOperate: function (operate) {
      this.operate = operate
      this.state = 1
    },
    getResult: function () {
      if (this.operate === '+') {
        this.result = parseInt(this.number1) + parseInt(this.number2)
      }
      if (this.operate === '-') {
        this.result = parseInt(this.number1) - parseInt(this.number2)
      }
      if (this.operate === '*') {
        this.result = parseInt(this.number1) * parseInt(this.number2)
      }
      if (this.operate === '/') {
        this.result = parseInt(this.number1) / parseInt(this.number2)
      }
      this.state = 3
    },
    reset: function () {
      this.state = 0
      this.number1 = ''
      this.number2 = ''
      this.operate = ''
      this.result = ''
    }

  },
  components: {}
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
  margin-top: 100px;
  border-collapse: collapse;
  box-shadow: 0 10px 100px 0 rgba(0, 0, 0, 0.50);
}

table td{
  border: 1px solid #a7a8ad;
}

button {
    background-color: #e1e0e6; /* Green */
    border: none;
    color: #1d181e;
    font-weight: bold;
    padding: 20px 32px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 20px;
    font-family: 'Microsoft JhengHei UI';
    cursor: pointer;
    width: 100%;
}
</style>
