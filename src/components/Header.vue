<template>
  <header>
      <img :src="logo" alt="Logo" />
      <nav>
        <a href="#">Home</a>
        <a href="#">About</a>
        <a href="#">Contact</a>
      </nav>
  </header>
</template>

<script>
import Logo from "/src/assets/logo.svg";
export default {
  name: "Header",
  data() {
    return {
      logo: Logo,
    };
  },
};
</script>
