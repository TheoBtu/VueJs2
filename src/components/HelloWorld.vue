<template>
  <v-hover
          v-slot:default="{ hover }"
          close-delay="200"
  >
      <v-card
              :elevation="hover ? 16 : 2"
              class="mx-auto"
              max-width="400"
      >
        <v-img
                class="white--text align-end"
                height="200px"
                :src="image"
        >
          <v-card-title class="title">{{name}}</v-card-title>
        </v-img>

        <v-card-text class="text--primary">
          <div>{{description}}</div>
          <br>
          <div>La taille moyenne est de {{taille}} m </div>
          <div>Le poids moyen est de {{poids}} kg</div>
          <v-divider></v-divider>
          <v-card-text> Article posté durant l'année {{ today | toDate }} </v-card-text>
        </v-card-text>
        <div class="text-center">
          <v-dialog
                  v-model="dialog"
                  width="500"
          >
            <template v-slot:activator="{ on }">
              <v-btn
                      color="primary"
                      dark
                      v-on="on"
              >
                Voir plus
              </v-btn>
            </template>

            <v-card>
              <v-card-title
                      class="headline grey lighten-2"
                      primary-title
              >
                {{name}}
              </v-card-title>

              <v-card-text>
                <div>{{description}}</div>
                <br>
                <div>La taille moyenne est de {{taille}} m </div>
                <div>Le poids moyen est de {{poids}} kg</div>
                  <br>
                  <v-btn @click="showtype=true"> Afficher le type </v-btn>
                  <br>
                  <div>
                      <p v-if="showtype=true"> {{name}} est de type {{type}}
                      </p>
                      <p v-else> Pas de type affiché </p>
                  </div>
              </v-card-text>
              <v-divider></v-divider>
            </v-card>
          </v-dialog>
        </div>
      </v-card>
  </v-hover>
</template>


<style>
  .content{
    height: 100%;
    width: 100%;
  }
  .title{
    color: #252525;
  }
  .text--primary{
    color: #252525;
  }
  h1{
    font-size: 30px;
    font-family: Roboto;
    color: #e3e3e3;
  }
  .nav-bar{
    height: 65px;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: #252525
  }
  .grid{
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      grid-template-rows: repeat(2, 1fr);
      grid-column-gap: 0px;
      grid-row-gap: 0px;
  }
  .boutontype{
    padding-top: 200px;
  }
</style>

<script>
  export default {
    name: 'animaux',
    props: {
      name:String,
      taille:Number,
      poids:Number,
      description:String,
      image:String,
      type:String,
    },
    filters : {
      toDate : function (dateValue) {
        return new Date(dateValue).getFullYear();
      }
    },
    data () {
      return {
          showtype:false,
        today : Date.now(),
        items: [
          {
            src: 'https://resize.prod.docfr.doc-media.fr/img/var/doctissimo/storage/images/fr/www/animaux/chien/soins-chien/bain-pour-un-chien/723393-2-fre-FR/bain-pour-un-chien.jpg',
          },
          {
            src: 'https://www.wikichat.fr/wp-content/uploads/sites/2/comment-soigner-une-plaie-dun-chat.jpg',
          },
          {
            src: 'https://www.cotelandesnaturetourisme.com/app/uploads/cotelandesnature/2019/02/saintjulien-4804-clntsophiepawlak-1920x1278.jpg',
          },
          {
            src: 'https://www.zooplus.fr/magazine/wp-content/uploads/2019/08/race-de-hamster-1.jpg',
          },
          {
            src: 'https://www.fishipedia.fr/wp-content/uploads/2016/01/poisson_rouge-2.jpg',
          },
        ],
         // ICI POUR LA PROCHAINE DATA //
      }
    },
  }
</script>
