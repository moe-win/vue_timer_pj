<template>
  <div class="block" v-if="showblock" @click="cleartimer">Click Here {{delay}}</div>
 
</template>

<script>
export default {
    props:['delay'],
    data(){
      return{
        showblock:false,
        reactiontime:0,
        timer:null
      }
    },
   mounted(){
      setTimeout(() => {
         this.showblock=true;
         this.startimer() 
      }, this.delay);
   },
   methods:{
      startimer(){
          this.timer=setInterval(() => {
          this.reactiontime+=100;  
          }, 100);
      },
      cleartimer(){
        clearInterval(this.timer);
        // console.log(this.reactiontime);
        this.$emit("finishGame",this.reactiontime)

      }
   }
  //  updated(){
  //   console.log("data update here");
  //  },
  //  unmounted(){
  //   console.log("Block component unmounted");
  //  }
}
</script>

<style>
.block{
    background-color: blueviolet;
    height: 150px;
    width: 200px;
    margin: 10px auto;
    padding: 40px;
}

</style>