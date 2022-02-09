<script>
import CardItem from "./CardItem.vue"
export default {
    props: ["myData"],

    components : {
        CardItem
    }
};
//:key="cardList.id" 
</script>

<template>
    <CardItem @delete-card-item="$emit('delete-card-item',$event)" v-for="CardItem in myData" key="cardList.id" :item="CardItem"/>
  <!--<CardItem v-for="CardItem in myData" key="cardList.id" :item="CardItem"/> -->
</template>
