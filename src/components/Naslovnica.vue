<template>
  <div style="margin-top:100px">
    <b-container fluid>
      <b-jumbotron id="naslovnica">
        <div style="text-align:center">
          <b-img
            fluid
            right
            src="https://www.liquor.com/thmb/kPBP5k0--LffkmerIVD4QvvNqtc=/0x250/filters:no_upscale():max_bytes(150000):strip_icc():format(webp)/01cocktail-00home-b01b390c314f42fb859434fd6731dc6e.png"
          ></b-img>
          <h1>Welcome to The CocktailDB</h1>
          <h3>Best cocktails recipes from aroud the world</h3>
          <br />
          <br />
          <b-button variant="dark" v-on:click="randomCocktail">Click me for random cocktail!</b-button>
          <br />
          <br />
          <br />
          <br />
          <b-row>
            <b-col cols="4" style="margin-left:150px">
                <b-input-group>
                  <b-img
                    style="margin-right:5px"
                    v-on:click="prikaziJezik"
                    height="38px"
                    width="38px"
                    src="https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Fwww.clipartbest.com%2Fcliparts%2F9T4%2FeRM%2F9T4eRMjTE.jpeg&f=1&nofb=1"
                  ></b-img>
                  <b-img
                    style="margin-right:5px"
                    v-on:click="prikaziJezik"
                    height="38px"
                    width="38px"
                    src="https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2F4.bp.blogspot.com%2F-mPly-j3GwvM%2FTcL2ehiJKcI%2FAAAAAAAAAhk%2FA2Q1eUfb2ZY%2Fs1600%2FGermany%2BFlag%2BWallpaper%2B%2525286%252529.jpg&f=1&nofb=1"
                  ></b-img>
                  <b-form-input
                    placeholder="Search for cocktail"
                    v-model="pretraga"
                    v-on:keyup.enter="getCocktail"
                  ></b-form-input>
                  <template v-slot:append>
                    <b-dropdown text="Search by:" variant="dark">
                      <b-dropdown-item v-on:click="getCocktail">Name</b-dropdown-item>
                      <b-dropdown-item v-on:click="getIngredient">Ingredient</b-dropdown-item>
                    </b-dropdown>
                  </template>
                </b-input-group>
            </b-col>
          </b-row>
        </div>
      </b-jumbotron>
      <b-row>
        <b-col cols="3" v-for="cocktail in cocktails" v-bind:key="cocktail.idDrink">
          <div>
            <b-card
              :title="cocktail.strDrink"
              :img-src="cocktail.strDrinkThumb"
              img-top
              style="max-width: 20rem;"
              class="mb-2"
              bg-variant="dark"
              text-variant="light"
            >
              <b-list-group>
                <b-list-group-item
                  v-if="cocktail.strIngredient1 != null"
                  variant="dark"
                  class="d-flex justify-content-between align-items-center"
                >
                  {{ cocktail.strIngredient1 }}
                  <b-badge variant="dark" pill>{{ cocktail.strMeasure1 }}</b-badge>
                </b-list-group-item>

                <b-list-group-item
                  v-if="cocktail.strIngredient2 != null"
                  variant="dark"
                  class="d-flex justify-content-between align-items-center"
                >
                  {{ cocktail.strIngredient2 }}
                  <b-badge variant="dark" pill>{{ cocktail.strMeasure2 }}</b-badge>
                </b-list-group-item>

                <b-list-group-item
                  v-if="cocktail.strIngredient3 != null"
                  variant="dark"
                  class="d-flex justify-content-between align-items-center"
                >
                  {{ cocktail.strIngredient3 }}
                  <b-badge variant="dark" pill>{{ cocktail.strMeasure3 }}</b-badge>
                </b-list-group-item>

                <b-list-group-item
                  v-if="cocktail.strIngredient4 != null"
                  variant="dark"
                  class="d-flex justify-content-between align-items-center"
                >
                  {{ cocktail.strIngredient4 }}
                  <b-badge variant="dark" pill>{{ cocktail.strMeasure4 }}</b-badge>
                </b-list-group-item>

                <b-list-group-item
                  v-if="cocktail.strIngredient5 != null"
                  variant="dark"
                  class="d-flex justify-content-between align-items-center"
                >
                  {{ cocktail.strIngredient5 }}
                  <b-badge variant="dark" pill>{{ cocktail.strMeasure5 }}</b-badge>
                </b-list-group-item>

                <b-list-group-item
                  v-if="cocktail.strIngredient6 != null"
                  variant="dark"
                  class="d-flex justify-content-between align-items-center"
                >
                  {{ cocktail.strIngredient6 }}
                  <b-badge variant="dark" pill>{{ cocktail.strMeasure6 }}</b-badge>
                </b-list-group-item>

                <b-list-group-item
                  v-if="cocktail.strIngredient7 != null"
                  variant="dark"
                  class="d-flex justify-content-between align-items-center"
                >
                  {{ cocktail.strIngredient7 }}
                  <b-badge variant="dark" pill>{{ cocktail.strMeasure7 }}</b-badge>
                </b-list-group-item>

                <b-list-group-item
                  v-if="cocktail.strIngredient8 != null"
                  variant="dark"
                  class="d-flex justify-content-between align-items-center"
                >
                  {{ cocktail.strIngredient8 }}
                  <b-badge variant="dark" pill>{{ cocktail.strMeasure8 }}</b-badge>
                </b-list-group-item>

                <b-list-group-item
                  v-if="cocktail.strIngredient9 != null"
                  variant="dark"
                  class="d-flex justify-content-between align-items-center"
                >
                  {{ cocktail.strIngredient9 }}
                  <b-badge variant="dark" pill>{{ cocktail.strMeasure9 }}</b-badge>
                </b-list-group-item>

                <b-list-group-item
                  v-if="cocktail.strIngredient10 != null"
                  variant="dark"
                  class="d-flex justify-content-between align-items-center"
                >
                  {{ cocktail.strIngredient10 }}
                  <b-badge variant="dark" pill>{{ cocktail.strMeasure10 }}</b-badge>
                </b-list-group-item>

                <b-list-group-item
                  v-if="cocktail.strIngredient11 != null"
                  variant="dark"
                  class="d-flex justify-content-between align-items-center"
                >
                  {{ cocktail.strIngredient11 }}
                  <b-badge variant="dark" pill>{{ cocktail.strMeasure11 }}</b-badge>
                </b-list-group-item>

                <b-list-group-item
                  v-if="cocktail.strIngredient12 != null"
                  variant="dark"
                  class="d-flex justify-content-between align-items-center"
                >
                  {{ cocktail.strIngredient12 }}
                  <b-badge variant="dark" pill>{{ cocktail.strMeasure12 }}</b-badge>
                </b-list-group-item>

                <b-list-group-item
                  v-if="cocktail.strIngredient13 != null"
                  variant="dark"
                  class="d-flex justify-content-between align-items-center"
                >
                  {{ cocktail.strIngredient13 }}
                  <b-badge variant="dark" pill>{{ cocktail.strMeasure13 }}</b-badge>
                </b-list-group-item>

                <b-list-group-item
                  v-if="cocktail.strIngredient14 != null"
                  variant="dark"
                  class="d-flex justify-content-between align-items-center"
                >
                  {{ cocktail.strIngredient14 }}
                  <b-badge variant="dark" pill>{{ cocktail.strMeasure14 }}</b-badge>
                </b-list-group-item>

                <b-list-group-item
                  v-if="cocktail.strIngredient15 != null"
                  variant="dark"
                  class="d-flex justify-content-between align-items-center"
                >
                  {{ cocktail.strIngredient15 }}
                  <b-badge variant="dark" pill>{{ cocktail.strMeasure15 }}</b-badge>
                </b-list-group-item>
              </b-list-group>
              <br />
              <b-card-text v-if="prikazi">{{ cocktail.strInstructions }}</b-card-text>
              <b-card-text v-else>{{ cocktail.strInstructionsDE }}</b-card-text>

              <br />
            </b-card>
          </div>
        </b-col>
        <b-col v-if="cocktails == null" cols="1">
          <p style="color: white; background-color: black">No results.</p>
        </b-col>
      </b-row>
    </b-container>
    <div style="margin-top:150px">
      <b-navbar variant="dark" type="dark" toggleable="false">
        <b-navbar-brand
          v-for="(slovo, index) in slova"
          v-bind:key="slovo"
          v-on:click="getLetter(index)"
          style="cursor:pointer;"
        >
          <b>{{ slovo }}</b>
        </b-navbar-brand>
      </b-navbar>
    </div>
  </div>
</template>

<script>
export default {
  name: "Naslovnica",
  data: function() {
    return {
      prikazi: true,
      pretraga: "",
      cocktails: [],
      slova: [
        "A",
        "B",
        "C",
        "D",
        "E",
        "F",
        "G",
        "H",
        "I",
        "J",
        "K",
        "L",
        "M",
        "N",
        "O",
        "P",
        "Q",
        "R",
        "S",
        "T",
        "U",
        "V",
        "W",
        "X",
        "Y",
        "Z"
      ]
    };
  },
  methods: {
    getCocktail: function() {
      this.axios
        .get(
          "https://www.thecocktaildb.com/api/json/v1/1/search.php?s=" +
            this.pretraga
        )
        .then(response => {
          console.log(response.data.drinks);

          this.cocktails = response.data.drinks;
        });
    },
    getIngredient: function() {
      this.axios
        .get(
          "https://www.thecocktaildb.com/api/json/v1/1/filter.php?i=" +
            this.pretraga
        )
        .then(response => {
          console.log(response.data.drinks);

          this.cocktails = response.data.drinks;
        });
    },
    prikaziJezik: function() {
      this.prikazi = !this.prikazi;
    },
    randomCocktail: function() {
      this.axios
        .get("https://www.thecocktaildb.com/api/json/v1/1/random.php")
        .then(response => {
          console.log(response.data.drinks);

          this.cocktails = response.data.drinks;
        });
    },
    getLetter: function(i) {
      this.axios
        .get(
          "https://www.thecocktaildb.com/api/json/v1/1/search.php?f=" +
            this.slova[i]
        )
        .then(response => {
          console.log(response.data.drinks);

          this.cocktails = response.data.drinks;
        });
    }
  }
};
</script>

<style>
#naslovnica {
  opacity: 80%;
}
</style>