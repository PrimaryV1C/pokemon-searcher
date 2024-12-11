<template>
  <div>
    <div class="grid">
      <div
          v-for="item in gridItems"
          :key="item.id"
          class="card"
          @click="navigateTo(item.url)"
      >
        <img :src="item.image" :alt="item.title" />
        <h3>{{ item.title }}</h3>
        <p>{{ item.text }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "GridComponent",
  methods: {
    navigateTo(url) {
      window.location.href = url;
    },
  },
};
</script>
