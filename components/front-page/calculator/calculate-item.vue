<template>
  <div class="calculate-item_wrapper">
    <img :src="image" alt="">
    <div class="calc-item">
      <p style="color: #C7C7C7">{{title}}</p>
      <div class="calculate">
        <button @click="minus" class="calc-button"><img src="/minus.svg" alt=""></button>
<!--        <input type="text" :value="number" @change="$emit('number', $event.target.value)">-->
        <p>{{number}} {{edinica}}</p>
        <button @click="plus" class="calc-button"><img src="/plus.svg" alt=""></button>
      </div>

    </div>
  </div>
</template>

<script>
export default {
  data(){
    return{
      number:10
    }
  },
  props:{
    image:{type: String},
    title:{type:String},
    edinica:{type:String}
  },
  methods:{
    plus(){
      this.number+=1
      this.$emit('number', this.number);
    },
    minus(){
      this.number-=1
      this.$emit('number', this.number);
    }
  },
  mounted() {
    this.$emit("number", this.number)
  }
}
</script>

<style>
.calculate-item_wrapper{
  flex-direction: row;
  justify-content: center;
  align-items: center;
  gap: 10px;
}
.calculate{
  flex-direction: row;
  gap: 3px;
}
.calc-button{
  border: none;
  padding: 0;
  background: rgba(0,0,0,0);
}

</style>
