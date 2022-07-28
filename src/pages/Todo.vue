<template>
  <a
    href="https://wa.me/004915784440707"
    target="_blank"
    class="q-pa-sm chat flex flex-center"
    ><q-btn label="Help per Chat" stack glossy color="red"
  /></a>
  <q-page class="bg-grey-3 column">
    <q-list class="bg-white" separator bordered>
      <q-item
        v-for="task in tasks"
        :key="task.title"
        @click="task.done = !task.done"
        :class="{ 'done bg-blue-1': task.done }"
        clickable
        v-ripple
      >
        <q-item-section avatar>
          <q-checkbox v-model="task.done" class="no-pointer-events" color="primary" />
        </q-item-section>
        <q-item-section>
          <q-item-label>{{ task.title }}</q-item-label>
        </q-item-section>
                <q-item-section v-if="task.done" side> <q-btn flat round dense color="primary" icon="delete" />
          <!-- <q-item-label>{{ task.title }}</q-item-label> -->
        </q-item-section>
      </q-item>
    </q-list>
  </q-page>
</template>

<script>
// import { defineComponent } from "vue";

// export default defineComponent({
//   name: "Todo",
// });
export default {
  data() {
    return {
      tasks: [
        {
          title: "One",
          done: false,
        },
        {
          title: "Two",
          done: false,
        },
        {
          title: "Three",
          done: false,
        },
      ],
    };
  },
};
</script>

<style lang="scss">
.done {
  .q-item__label {
    text-decoration: line-through;
  }
}
.chat {
  text-decoration: none;
}
</style>
