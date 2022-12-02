<template>
  <div class="q-pa-md">
    <div class="text-h4" style="text-align: center">
      <a
        style="
          border: none;
          background: none;
          color: black;
          text-decoration: none;
        "
        href="https://www.facebook.com/PontDeLaFonderie/"
        >MY_SIDA IN ALSACE</a
      >
    </div>
    <div class="text-h5 q-ma-lg">
      <a
        style="
          border: none;
          background: none;
          color: black;
          text-decoration: none;
        "
        href="https://www.youtube.com/watch?v=FICwwep6DUY&ab_channel=LesArchivesdeQuentin"
        >Quiz</a
      >
    </div>
    <q-card class="my-card" style="text-align: center" v-if="question == 0">
      <q-card-section>
        <div class="text-h4" style="text-align: center">
          Le
          <a
            style="
              border: none;
              background: none;
              color: black;
              text-decoration: none;
            "
            href="https://www.youtube.com/watch?v=dQw4w9WgXcQ"
            >sida</a
          >
          c'est
          <a
            style="
              border: none;
              background: none;
              color: black;
              text-decoration: none;
            "
            href="https://goo.gl/maps/RpQ49THgVEvtbqfc8"
            >bien</a
          >
          ?
        </div>
      </q-card-section>

      <q-separator />

      <q-card-actions vertical>
        <q-btn
          flat
          href="https://www.youtube.com/watch?v=cfBUMx31MS8&ab_channel=MemeFr"
          >OUI</q-btn
        >
        <q-btn flat @click="changeQuestion()">NON</q-btn>
      </q-card-actions>
    </q-card>
    <q-card class="my-card" style="text-align: center" v-if="question == 1">
      <q-card-section>
        <div class="text-h4" style="text-align: center">
          Avez-vous récemment eu des rapports sans protection ?
        </div>
      </q-card-section>

      <q-separator />

      <q-card-actions vertical>
        <q-btn flat @click="ouiQuestion()">OUI</q-btn>
        <q-btn flat @click="nonQuestion()">NON</q-btn>
      </q-card-actions>
    </q-card>
    <div style="text-align: center">
      <img src="src/assets/pasbien.jpg" v-if="question == 4" />
    </div>
    <div style="text-align: center">
      <img
        src="src/assets/1320x990px-Feautured-image-58-1024x768.jpg"
        v-if="question == 5"
      />
    </div>
  </div>
  <q-separator class="q-ma-lg" style="color: black" />
  <div class="q-pa-md">
    <div class="q-gutter-md">
      <div class="text-h5 q-ma-lg">
        <a
          style="
            border: none;
            background: none;
            color: black;
            text-decoration: none;
          "
          href="https://www.youtube.com/watch?v=of2vBq24kJ8&ab_channel=EthanFonseca"
          >Informations</a
        >
      </div>
      <q-carousel
        v-model="slide"
        transition-prev="scale"
        transition-next="scale"
        swipeable
        animated
        control-color="white"
        navigation
        padding
        arrows
        height="300px"
        class="bg-primary text-white shadow-1 rounded-borders"
      >
        <q-carousel-slide name="style" class="column no-wrap flex-center">
          <h5>LA FELLATION, EST-CE QUE C’EST UN RISQUE ?</h5>
          <div class="q-mt-md text-center">
            "On m’a fait une fellation"
            <br />
            Il n’y a pas de risque VIH quand on reçoit une fellation (quand on
            se fait sucer).
            <br />
            <br />
            "J'ai fait une fellation"
            <br />
            Faire une fellation à un homme qui a le VIH peut comporter un risque
            de transmission du VIH si sa charge virale n’est pas indétectable.
          </div>
        </q-carousel-slide>
        <q-carousel-slide name="tv" class="column no-wrap flex-center">
          <h5>PÉNÉTRATION ANALE SANS CAPOTE : QUELS RISQUES ?</h5>
          <div class="q-mt-md text-center">
            Si je suis pénétré-e ("passif.ve" ou "réceptif.ve")
            <br />
            Le VIH peut être transmis aux 2 partenaires lors d'une pénétration
            anale non protégée par un préservatif si l’un des partenaires est
            porteur de ce virus et que sa charge virale n'est pas indétectable.
            <br />
            <br />
            L’éjaculation dans l’anus augmente le risque de transmission du VIH
            pour la personne pénétrée.
            <br />
            Si je pénètre ("actif" ou "insertif") Le VIH peut être transmis aux
            2 partenaires lors d'une pénétration anale non protégée par un
            préservatif si l’un des partenaires est porteur de ce virus et que
            sa charge virale n'est pas indétectable.
            <br />
            Si l’un des partenaires (ou les deux) est porteur d’une infection
            sexuellement transmissible (IST), le risque de transmission du VIH
            est plus important.
          </div>
        </q-carousel-slide>
        <q-carousel-slide name="layers" class="column no-wrap flex-center">
          <h5>L’ANULINGUS C’EST RISQUÉ POUR LE VIH ?</h5>
          <div class="q-mt-md text-center">
            L'anulingus n'est pas une pratique à risque pour le VIH.
            <br />
            On ne peut pas avoir le VIH en léchant l'anus d'une personne
            séropositive.
            <br />
            En revanche l’anulingus peut présenter un risque pour d'autres
            maladies, notamment la syphilis, la blennorragie, l'hépatite A et
            divers microbes intestinaux.
          </div>
        </q-carousel-slide>
        <q-carousel-slide name="map" class="column no-wrap flex-center">
          <h5>J’AI REÇU DU SPERME DANS L’OEIL</h5>
          <div class="q-mt-md text-center">
            Le contact de sperme avec la muqueuse de l'œil ne représente pas un
            risque de transmission du VIH.
            <br />
            En cas de projection, le réflexe des paupières est de se fermer pour
            protéger l’œil.
            <br />
            La sécrétion de larmes constitue une protection supplémentaire
            contre le contact avec le sperme.
          </div>
        </q-carousel-slide>
      </q-carousel>
    </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue';
import { ref } from 'vue';
import { useRouter } from 'vue-router';

export default defineComponent({
  setup() {
    const question = ref(0);
    // const changeQuestion = function () {
    //   question.value += 1;
    //   console.log(question.value);
    // };
    return {
      changeQuestion: () => {
        question.value += 1;
      },
      ouiQuestion: () => {
        question.value = 4;
      },
      nonQuestion: () => {
        question.value = 5;
      },
      slide: ref('style'),
      lorem:
        'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Itaque voluptatem totam, architecto cupiditate officia rerum, error dignissimos praesentium libero ab nemo.',
      question,
    };
  },
});
</script>
