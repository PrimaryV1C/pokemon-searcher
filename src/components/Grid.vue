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
  data() {
    return {
      gridItems: [], // Will be populated with API or fallback data
      dummyData: [
        {
          id: 1,
          image: "./src/assets/profile-images/mario.webp",
          title: "Mario",
          text: "The heroic plumber from the Mushroom Kingdom.",
          url: "https://www.nintendo.com",
        },
        {
          id: 2,
          image: "./src/assets/profile-images/link.webp",
          title: "Link",
          text: "The brave adventurer from The Legend of Zelda.",
          url: "https://www.nintendo.com",
        },
        {
          id: 3,
          image: "./src/assets/profile-images/samus.webp",
          title: "Samus Aran",
          text: "The legendary bounty hunter from Metroid.",
          url: "https://www.nintendo.com",
        },
        {
          id: 4,
          image: "./src/assets/profile-images/kirby.png",
          title: "Kirby",
          text: "The pink puffball who can inhale anything.",
          url: "https://www.nintendo.com",
        },
        {
          id: 5,
          image: "./src/assets/profile-images/pikachu.png",
          title: "Pikachu",
          text: "The iconic Electric-type Pokémon.",
          url: "https://www.nintendo.com",
        },
        {
          id: 6,
          image: "./src/assets/profile-images/dk.webp",
          title: "Donkey Kong",
          text: "The strong and lovable leader of the DK crew.",
          url: "https://www.nintendo.com",
        },
      ],
    };
  },
  methods: {
    async fetchGridItems() {
      try {
        const response = await fetch("https://pokeapi.co/api/v2/pokemon?limit=6");
        if (!response.ok) {
          throw new Error("API request failed");
        }
        const data = await response.json();
        this.gridItems = data.results.map((item, index) => ({
          id: index + 1,
          title: item.name.charAt(0).toUpperCase() + item.name.slice(1),
          text: "Click to learn more about this Pokémon!",
          image: `https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/official-artwork/${
              index + 1
          }.png`,
          url: `https://pokeapi.co/${item.name}`,
        }));
      } catch (error) {
        console.error("Failed to fetch data, using dummy data:", error);
        this.gridItems = this.dummyData; // Use dummy data on failure
      }
    },
    navigateTo(url) {
      window.open(url, "_blank");
    },
  },
  mounted() {
    this.fetchGridItems();
  },
};
</script>
