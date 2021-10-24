<template>
   <div>
      <h3>Your question is:</h3>
      <div class="viewer"> {{ question }} </div>

      <div class="animate__animated animate__bounceIn animate__delay-1s">
         <hr/>
         <button class="btn" @click="goNext">
            Decide it
         </button>
         <button class="btn" @click="goBack">
            Ask a new question
         </button>

      </div>
   </div>
   
</template>

<script>
export default {
   props:['question'],
   methods:{
      goNext(){
         this.$emit('goto',2);
      },
      goBack(){
         this.$emit('goto',0);
         this.$emit('question','')
      }
   }
}

</script>
