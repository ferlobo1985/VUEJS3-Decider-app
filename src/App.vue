<template>
  <div class="container">

    <component
      :is="screens[position]"
      :question="question"
      @goto="handleGoTo"
      @question="handleQuestion"
    />

  </div>

</template>

<script>
 import appInitial from './components/initial.vue'
 import appConfirm from './components/confirm.vue';
 import appResults from './components/results.vue';

 export default {
   components:{
     appInitial,
     appConfirm,
     appResults
   },
   data(){
     return{
        screens:['appInitial','appConfirm','appResults'],
        position:0,
        question:''
     }
   },
   methods:{
     handleGoTo(position){
       this.position = position
     },
     handleQuestion(question){
       this.question = question
     }
   }
 }
</script>

<style>
  @import './assets/style.css';

</style>
