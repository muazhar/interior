<template>
  <q-item clickable tag="a" :href="link">
    <q-item-section>
      <q-item-label class="text-weight-bold">{{ title }}</q-item-label>
    </q-item-section>
  </q-item>
</template>

<script>
export default {
  name: "EssentialLink",
  props: {
    title: {
      type: String,
      required: true
    },

    link: {
      type: String,
      default: "#"
    },

  }
};
</script>
