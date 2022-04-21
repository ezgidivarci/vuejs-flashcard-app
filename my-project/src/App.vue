<script>
import AddSection from './components/AddSection.vue'
import CardList from './components/CardList.vue'
import ResultBar from './components/ResultBar.vue'

export default {
  components: {
    AddSection,
    CardList,
    ResultBar,

   
  },

  data() {
    return {
      cardList : []
    }
  },
  /* created() {
    this.cardList = [
      { id: 1, question: "question1" , answer: "answer1"},
      { id: 2, question: "question1" , answer: "answer1"},
      { id: 3, question: "question1" , answer: "answer1"},
      { id: 4, question: "question1" , answer: "answer1"},
      { id: 5, question: "question1" , answer: "answer1"},
      { id: 6, question: "question1" , answer: "answer1"},

    ];
  }, */



  methods: {
    addNewCard(questioninput, answerinput) {
      //console.log("inputlarım:" , event ,data);
      this.cardList.push({
        id: new Date().getTime(),
        question: questioninput,
        answer: answerinput
      })
    },
    deleteItem(cardItem) {
      //this.cardList = this.cardList.filter((t) => t !== cardItem)
      const matchedIndex = this.cardList.findIndex((i) => i === cardItem);
      if (matchedIndex > -1) {
        this.cardList.splice(this.cardList[matchedIndex], 1);
      }
    },

    /* prefs(cardList) {
      var p = {
        storedq : this.cardList.question,
        storeda : this.cardList.answer
      };

      return p;
    } */

  },

  /* computed: {
    prefs(cardList) {
      
        storedq : this.cardList.question,
        storeda : this.cardList.answer
      

      return p;
    }
  } */



}
</script>

<template>
<div>
  
  <AddSection @add-card="addNewCard"/>
  <CardList @delete-card-item="deleteItem" :myData="cardList"> </CardList>
  <!--<CardList :myData="cardList"> </CardList> -->
  <ResultBar :itemCount="cardList.length"/>
  
  <!--<p> prefs : {{ prefs }}</p>
  <p> card list: {{ cardList.answer }} </p> -->
</div>
  
</template>

