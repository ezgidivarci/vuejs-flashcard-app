<script>
export default {
    props: ["item"],
    data() {
        return {
            visibility:false
        }
    }
};



</script>

<template>
    
        <div class="flex-wrap max-w-md mx-auto mt-10 bg-yellow-100 rounded-xl shadow-md overflow-hidden md:max-w-xl lg:max-w-xl">

                <form>
        
                   <label class="block px-8 py-4 ">
                      <span class="whitespace-normal after:ml-0.5 text-lg after:text-red-500 block text-sm font-medium text-slate-700">
                           Question
                      </span>
                       <p class="whitespace-normal">{{ item.question }}</p>
                        
                       <span @click="visibility= !visibility" class="whitespace-normal after:ml-0.5 mt-4 text-lg after:text-red-500 block text-sm font-medium text-slate-700 hover:cursor-pointer">
                           Answer
                      </span>
                       <p  v-show="visibility"  class="visibility whitespace-normal"> {{ item.answer }} </p>
                       
                    </label>
                    <button @click= "$emit('delete-card-item', item)" class="float-right rounded-xl text-white bg-pink-400 m-2 px-2 py-1"> delete</button>
                </form>
               <!-- <p> {{ item.question }} {{ item.answer}} </p> -->
        </div>
      
   
</template>



