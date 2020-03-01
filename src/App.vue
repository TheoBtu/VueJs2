<template>
  <v-app>
    <v-content>
      <div class="nav-bar">
        <h1> Nos amis les animaux </h1>
        <v-icon> fas fa-paw </v-icon>
      </div>
      <v-carousel hide-delimiters height="656px" cycle>
        <v-carousel-item
                v-for="(item,i) in items"
                :key="i"
                :src="item.src"
        ></v-carousel-item>
      </v-carousel>
      <div class="grid">
      <animaux class="mt-5 pb-5 " v-for="animal in animaux" :name ="animal.name" :taille = "animal.taille" :image="animal.image" :poids="animal.poids" :description="animal.description" :type="animal.type" :key="animal.id">
      </animaux>
      </div>
    </v-content>
  </v-app>
</template>

<script>
import animaux from './components/HelloWorld';

export default {
  name: 'App',

  components: {
    animaux
  },

  data:function(){
  return{
    animaux:[
      {name: "Le Chien", type:"Mammifères", taille: 0.45, poids: 15,image:"https://resize.prod.docfr.doc-media.fr/img/var/doctissimo/storage/images/fr/www/animaux/chien/soins-chien/bain-pour-un-chien/723393-2-fre-FR/bain-pour-un-chien.jpg", description:"Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolores ex explicabo ipsa ipsum laudantium libero numquam quos ut voluptatum? A accusantium consequatur hic incidunt quasi quia, sed sit veniam voluptatem?"},
      {name: "Le Chat", type:"Félin", taille: 0.25, poids: 2,image:"https://www.wikichat.fr/wp-content/uploads/sites/2/comment-soigner-une-plaie-dun-chat.jpg", description:"Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolores ex explicabo ipsa ipsum laudantium libero numquam quos ut voluptatum? A accusantium consequatur hic incidunt quasi quia, sed sit veniam voluptatem?"},
      {name: "Le Cheval", type:"Mammifères", taille: 2.20, poids: 450,image:"https://www.cotelandesnaturetourisme.com/app/uploads/cotelandesnature/2019/02/saintjulien-4804-clntsophiepawlak-1920x1278.jpg", description:"Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolores ex explicabo ipsa ipsum laudantium libero numquam quos ut voluptatum? A accusantium consequatur hic incidunt quasi quia, sed sit veniam voluptatem?"},
      {name: "Le Hamster", type:"Rongeur", taille: 0.07, poids: 0.300,image:"https://www.zooplus.fr/magazine/wp-content/uploads/2019/08/race-de-hamster-1.jpg", description:"Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolores ex explicabo ipsa ipsum laudantium libero numquam quos ut voluptatum? A accusantium consequatur hic incidunt quasi quia, sed sit veniam voluptatem?"},
      {name: "Le Poisson", type:"Poisson", taille: 0.03 , poids: 1,image:"https://www.fishipedia.fr/wp-content/uploads/2016/01/poisson_rouge-2.jpg", description:"Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolores ex explicabo ipsa ipsum laudantium libero numquam quos ut voluptatum? A accusantium consequatur hic incidunt quasi quia, sed sit veniam voluptatem?"},
    ],
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
  }
}
};
</script>
