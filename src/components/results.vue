<template>
   <div>
      <h3>Your answer is:</h3>
      <div class="viewer"> {{ result }} </div>

      <div class="animate__animated animate__bounceIn animate__delay-1s">
         <hr/>
         <button class="btn" @click="startOver">
            Start over
         </button>
         <button class="btn" @click="getResult">
            Decide again
         </button>
      </div>
   </div>
   
</template>

<script>

export default {
   props:['result'],
   mounted(){
      this.getResult()
   },
   methods:{
      startOver(){
        this.$emit('startOver')
      },
      getResult(){
         this.$emit('showResult');
      }

   }
}

</script>
