<script>
export default {
  data() {
    return {
      questionText:null,
      answerText: null
    }
  },
  methods : {
    addNewCard() {
      this.$emit("add-card", this.questionText, this.answerText);
      this.questionText = null;
      this.answerText = null;
    }
  }
}

</script>

<template>
  
  <div>
    <h1 class="text-center mt-10 text-blue-600 text-2xl hover:text-blue-300 hover:underline hover:cursor-pointer">{{ msg }}</h1>

        <!-- <input @input="updateValue" type="text" :value = "fulltext" /> boyle yazmak yerine-->
            
          <div class="max-w-md mx-auto mt-10 bg-emerald-100 rounded-xl shadow-md overflow-hidden md:max-w-xl lg:max-w-xl">

                <form>
        
                   <label class="block px-8 py-4">
                      <span class="after:content-['*'] after:ml-0.5 text-lg after:text-red-500 block text-sm font-medium text-slate-700">
                           Question
                      </span>
                       <input v-model="questionText" class="mt-1 px-3 py-2 bg-white border shadow-sm border-slate-300 placeholder-slate-400 focus:outline-none focus:border-sky-500 focus:ring-sky-500 block w-full rounded-md sm:text-sm focus:ring-1" placeholder="e.g.: Where is the capital of Turkey?" />
                       <span class="after:content-['*'] after:ml-0.5 mt-5 text-lg after:text-red-500 block text-sm font-medium text-slate-700">
                           Answer
                      </span>
                       <input v-model="answerText" class="mt-1 px-3 py-2 bg-white border shadow-sm border-slate-300 placeholder-slate-400 focus:outline-none focus:border-sky-500 focus:ring-sky-500 block w-full rounded-md sm:text-sm focus:ring-1" placeholder="Ankara" />
                    </label>

                </form>

                      <button @click="addNewCard" class="bg-emerald-500 m-3 px-4 py-2 text-white float-right rounded-xl hover:bg-blue-500 ">
                        Save
                      </button>
           </div>

  </div>

 

  
</template>


