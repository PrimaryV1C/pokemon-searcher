<template>
  <footer>
      <div>
        <nav>
          <a href="#">Home</a>
          <a href="#">About</a>
          <a href="#">Contact</a>
        </nav>
      </div>
      <div>
        <h1>Get in touch!</h1>
        <p>Dummy Contact Info</p>
        <p>Name: John Doe</p>
        <p>Address: 123 Main St</p>
        <p>Phone: (123) 456-7890</p>
        <p>Email: john.doe@example.com</p>
      </div>
    <div>
      <img :src="logo" alt="Logo" />
    </div>
  </footer>
</template>

<script>
import Logo from "/src/assets/logo.svg";
export default {
  name: "Footer",
  data() {
    return {
      logo: Logo,
    };
  },
};
</script>
