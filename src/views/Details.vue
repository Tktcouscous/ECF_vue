<template>
  <!-- Main Wrapper -->
  <div id="main-wrapper">
    <div class="wrapper style2">
      <div class="inner">
        <div class="container">
          <div class="row">
            <div class="col-8 col-12-medium">
              <div id="content">
                <!-- Content -->

                <article>
                  <header class="major">
                    <h2>{{ card.name }}</h2>
                    <p>{{ card.artist }}</p>
                  </header>

                  <span class="image featured">
                    <img :src="card.imageUrl" alt="" />
                  </span>

                  <p>{{ card.text }}</p>
                </article>
              </div>
            </div>
            <div class="col-4 col-12-medium">
              <div id="sidebar">
                <!-- Sidebar -->

                <section>
                  <header class="major">
                    <h2>Infos</h2>
                  </header>
                  <p>
                    set name: <b>{{ card.setName }}</b>
                  </p>
                  <p>
                    rarity: <b>{{ card.rarity }}</b>
                  </p>
                  <p>
                    toughness: <b>{{ card.toughness }}</b>
                  </p>

                  <div class="button alt icon">{{displayPower(card.power)}}</div>
                </section>
              </div>
            </div>
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
  name: "CardDetails",
  data: () => ({
    card: {},
  }),

  async created() {
    const { cardId } = this.$route.params;
    const apiDetailsuri = "https://api.magicthegathering.io/v1/cards/" + cardId;
    console.log("API details : " + apiDetailsuri);
    const card = await axios.get(apiDetailsuri);
    this.card = card.data.card;
    
  },

  methods: {
    displayPower(power) {
      const fire = "💪";
      return fire.repeat(power);
    },
  },
};
</script>
