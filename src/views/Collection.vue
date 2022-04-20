<template>
  <!-- Main Wrapper -->
  <div id="main-wrapper">
    <div class="wrapper style2">
      <div class="inner">
        <div class="container">
          <div id="content">
            <!-- Content -->

            <article>
              <header class="major">
                <h2>Ma Collection</h2>
              </header>
              <div class="card-list" v-for="card in cards" :key="card.id">
                <div class="card-title"><b>#{{card.number}} </b>   {{card.name}}</div>
                <div class="card-action" @click="goToCardDetails(card.id)">👀</div>
              </div>
              <!--<div class="card-list">
                <div class="card-title"><b>#2</b> Card Title</div>
                <div class="card-action"><a href="#">👀</a></div>
              </div>-->
            </article>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import axios from "axios";

export default {
  name: "HomeView",
  data:()=>({
      cards:{},
  }),

  methods:{
    goToCardDetails(cardId){
      console.log(cardId)
      this.$router.push({name:'CardDetails',params:{cardId:cardId}})
      }
  },

  async created() {
    let allcards = await axios.get("https://api.magicthegathering.io/v1/cards");
    this.cards = allcards.data.cards;
  }
};
</script>

<style scoped>
div.card-list{
    border-radius:8px;
    padding:8px;
    border:1px solid grey;
    display: flex;
    box-shadow: rgba(0, 0, 0, 0.1) 0px 4px 12px;
    margin-bottom:4px;
}

div.card-title{
    flex:6
}

div.card-action{
    flex:1
}
div.card-action a{
    outline: none;
    text-decoration: none;
}

</style>
