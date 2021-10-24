<template>
   <div>
        <h1>Ask a question</h1>
        <div class="mb-3">
            <input
                name="question"
                type="text"
                class="form-control"
                id="question"
                v-model="question"
            />

            <button
                v-if="question"
                class="btn animate__animated animate__fadeIn"
                @click="handleNext"
            >
                Next
            </button>

            <!-- <div v-if="error" class="error">
                You question is to short
            </div>
 -->

        </div>

   </div>
</template>

<script>
export default {
    data(){
        return {
            question:'',
           // error:false
        }
    },
    methods:{
        handleNext(e){
            e.preventDefault();

            if(this.question.length <= 5){
              //  this.error = true;
                this.$emit('handleToast',{
                    type:'error',
                    message:`You question is to short`
                })
            
            } else if(this.question.length >= 50){
                this.$emit('handleToast',{
                    type:'error',
                    message:`You question is to long`
                })
            } else {
                this.error = false;
                this.$emit('goto',1);
                this.$emit('question',this.question)
            }


        }
    }
}
</script>
