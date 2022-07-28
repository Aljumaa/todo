<template>
  <q-layout view="lHh Lpr lFf" >
    <q-header elevated class="todo">
      <div class="q-px-lg q-pt-xl q-my-lg">
        <!-- <div class="text-h3">To Do</div> -->
        <!-- <div class="text-subtitlel q-pt-xl">{{ todaysDate }}</div> -->
        <div class="text-weight-bold q-pt-xl">{{ todaysDate }}</div>
        <!-- <div class="text-weight-bold">A.Aljumaa</div> -->
      </div>
      <q-img src="background.jpg" class="header-image absolute-top" height=""></q-img>
    </q-header>
    <q-page-container>
      <keep-alive> <router-view /> </keep-alive>
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from "vue";
import EssentialLink from "components/EssentialLink.vue";
import { date } from "quasar";

export default defineComponent({
  name: "MainLayout",

  components: {
    EssentialLink,
  },

  setup() {
    const leftDrawerOpen = ref(false);

    return {
      leftDrawerOpen,
      toggleLeftDrawer() {
        leftDrawerOpen.value = !leftDrawerOpen.value;
      },
    };
  },
  computed: {
    todaysDate() {
      let timeStamp = Date.now();
      return date.formatDate(timeStamp, "YYYY-MM-DD");
    },
  },
});
</script>

<style lang="scss">
.header-image {
  height: 100%;
  z-index: -1;
  opacity: 1;
  filter: grayscale(100%);
}
.todo{
  color: #2f2f2f;
}
</style>
