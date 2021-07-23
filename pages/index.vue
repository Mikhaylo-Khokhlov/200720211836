<template>
  <div>
    <presentation />
    <services />
    <reviews />
  </div>
</template>

<script>
import presentation from "~/components/presentation.vue";
import services from "~/components/services.vue";
import reviews from "~/components/reviews.vue";
export default {
  components: {
    presentation,
    services,
    reviews
  }
};
</script>
