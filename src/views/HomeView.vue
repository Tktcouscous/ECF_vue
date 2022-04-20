<template>
  <div id="page-wrapper">
    <!-- Main Wrapper -->
    <div id="main-wrapper">
      <div class="wrapper style1">
        <div class="inner">
          <!-- Feature 1 -->
          <section class="container box feature1">
            <div class="row">
              <div class="col-12">
                <header class="first major">
                  <h2>Mes 3 Dernières Cartes</h2>
                </header>
              </div>
              <div class="col-4 col-12-medium">
                <section>
                  <a href="#" class="image featured"
                    ><img src="@/assets/images/pic01.jpg" alt=""
                  /></a>
                  <header class="second icon solid fa-dragon">
                    <h3>Titre de la carte</h3>
                    <p>And a subtitle</p>
                  </header>
                </section>
              </div>
              <div class="col-4 col-12-medium">
                <section>
                  <a href="#" class="image featured"
                    ><img src="@/assets/images/pic01.jpg" alt=""
                  /></a>
                  <header class="second icon solid fa-dragon">
                    <h3>Titre de la carte</h3>
                    <p>And a subtitle</p>
                  </header>
                </section>
              </div>
              <div class="col-4 col-12-medium">
                <section>
                  <a href="#" class="image featured"
                    ><img src="@/assets/images/pic01.jpg" alt=""
                  /></a>
                  <header class="second icon solid fa-dragon">
                    <h3>Titre de la carte</h3>
                    <p>And a subtitle</p>
                  </header>
                </section>
              </div>
            </div>
          </section>
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
  data: () => ({
    cards: {},
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