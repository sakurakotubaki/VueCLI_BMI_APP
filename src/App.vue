<template>
  <div id="app">
   <h1>{{ BMI }}</h1><hr>
   <p>BMI（ボディマス指数 Body Mass Index：肥満指数）、標準体重を計算してみよう！<br>
       計算式はBMI＝<span id="s1">体重(kg) ÷ {身長(m) Ｘ 身長(m)}</span><br>
       BMI=<span id="s2">mass(lb) ÷ {heigiht(in) x height(in)} x 703 </span>(ヤード・ポンド法)</p>
   <input v-model.number="weight" type="number">kg<br>
   <input v-model.number="height" type="number">cm<br>
   <p class="standard">あなたの標準体重{{ calc }}kg</p><br>
   <p class="sm">小数点を切り捨てた数値{{ mf }}kg</p>
  </div>
</template>

<script>
export default {
  data(){
    return{
      BMI: 'BMI値計算アプリ',
      weight: 0,
      height: 0
    }
  },
  computed: {
    calc: function() {
      let w = this.weight
      let h = this.height * 2
      return  h / w * 703
    },
    mf: function() {
      return Math.floor(this.calc)
    }
  }
}
</script>

<style>
h1 {
  color: gray;
}

#s1 {
  color: rgb(83, 41, 237);
}

#s2 {
  color: rgba(242, 44, 44, 0.824);
}

.standard {
  color: rgba(242, 44, 44, 0.824);
  border-bottom: solid 2px gray;
}

.sm {
  color: blue;
}
</style>
