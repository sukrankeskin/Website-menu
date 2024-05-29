<template>
  <div id="menu">
    <div id="menu-items">
      <a href="/" class="menu-item">Home</a>
      <a href="/" class="menu-item">Shop</a>
      <a href="/" class="menu-item">About</a>
      <a href="/" class="menu-item">Contact Us</a>
    </div>
    <div id="menu-background-image"></div>
  </div>
</template>

<script>
document.addEventListener("DOMContentLoaded", function () {
  const menu = document.getElementById("menu");

  Array.from(document.getElementsByClassName("menu-item")).forEach(
    (item, index) => {
      item.onmouseover = () => {
        menu.dataset.activeIndex = index;
      };
    }
  );
});
</script>

<style>
body {
  background-color: rgb(20, 20, 20);
  margin: 0;
  padding: 0;
}
#menu {
  height: 100vh;
  display: flex;
  align-items: center;
}
.menu-item {
  color: white;
  font-size: clamp(2rem, 7vw, 8rem);
  font-family: "Ibarra Real Nova", serif;
  display: block;
  text-decoration: none;
  padding: clamp(0.25rem, 0.5vw, 1rem) 0rem;
  transition: all 0.4s ease;

  text-align: start;
}
#menu-items {
  margin-left: clamp(4rem, 20vw, 48rem);
  position: relative;
  z-index: 2;
}
#menu-items:hover > .menu-item {
  opacity: 0.3;
}
#menu-items:hover > .menu-item:hover {
  opacity: 1;
}

#menu-background-image {
  height: 100vh;
  width: 100vw;
  background-image: url(../assets/background.jpg);

  position: absolute;
  left: 0;
  top: 0;
  z-index: 0;
  background-position: center 40%;
  background-size: 110vmax;
  opacity: 0.15;
  transition: all 0.4s ease;
}
#menu-items:hover ~ #menu-background-image {
  background-size: 100vmax;
  opacity: 0.1;
}

#menu[data-active-index="0"] > #menu-background-image {
  background-position: center 25%;
}
#menu[data-active-index="1"] > #menu-background-image {
  background-position: center 50%;
}
#menu[data-active-index="2"] > #menu-background-image {
  background-position: center 75%;
}
#menu[data-active-index="3"] > #menu-background-image {
  background-position: center 100%;
}
</style>
