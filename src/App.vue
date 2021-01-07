<template>
  <div class="designintern">
    <h2>{{ name }}</h2>

    <div class="image">
      <img alt="girl with orange " src="./assets/girlorange.png" />
    </div>
    <div class="socialmedia">
      <div class="instagram">
        <a
          :href="'https://www.instagram.com/' + infos.instagram"
          target="_blank"
          rel="noopener noreferrer"
        >
          <img alt="girl with orange " src="./assets/instagram.png"
        /></a>
      </div>
      <div class="twitter">
        <a
          :href="'https://www.twitter.com/' + infos.twitter"
          target="_blank"
          rel="noopener noreferrer"
          ><img alt="girl with orange " src="./assets/twitter.png"
        /></a>
      </div>
      <div class="snapchat">
        <a
          :href="'https://www.snapchat.com/' + infos.snapchat"
          target="_blank"
          rel="noopener noreferrer"
          ><img alt="girl with orange " src="./assets/snapchat.png"
        /></a>
      </div>
      <div class="email">
        <a
          :href="'mailto:' + infos.email"
          target="_blank"
          rel="noopener noreferrer"
          ><img alt="girl with orange " src="./assets/mail.png"
        /></a>
      </div>
    </div>
    <div class="menu">
      <ul>
        <li><a href="#">HOME</a></li>
        <li><a href="#">ABOUT</a></li>
        <li><img src="./assets/girlorange.png" width="100" height="100" /></li>
        <li><a href="#">GALLERY</a></li>
        <li><a href="#">CONTACT</a></li>
      </ul>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "App",
  data() {
    return {
      infos: {},
      name: "",
    };
  },
  async created() {
    const res = await axios("https://hirng-x2021.glitch.me/api");
    const data = await res.data;

    this.infos = data.social_media;
    this.name = data.name;
    console.log(this.infos);
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap");
#app {
  font-family: "Montserrat", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  color: white;
}
.designintern {
  position: relative;
  background: linear-gradient(
    to right,
    rgb(212, 42, 93) 0%,
    rgb(212, 42, 93) 50%,
    rgb(185, 29, 102) 50%,
    rgb(185, 29, 102) 100%
  );
}
.designintern h2 {
  font-size: 3rem;
  letter-spacing: 10px;
  line-height: 2rem;
  font-weight: 100;
  padding: 2% 2%;
}
.image img {
  width: 700px;
  height: 750px;
  box-shadow: rgba(50, 50, 93, 0.25) 0px 50px 100px -20px,
    rgba(0, 0, 0, 0.3) 0px 30px 60px -30px;
  object-fit: cover;
  background-size: cover;
  background-position: center;
}
.socialmedia {
  position: absolute;
  top: 50%;
  left: 90%;
}
.socialmedia img {
  width: 30px;
  height: 30px;
}
.socialmedia a {
  color: white;
}
.menu ul {
  list-style: none;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 1% 2%;
}
.menu ul li a {
  text-decoration: none;
}
.menu ul li {
  padding-right: 2%;
  letter-spacing: 3px;
}
.menu ul li img {
  width: 100px;
  height: 100px;
  border-radius: 50%;
}
@media (max-width: 601px) {
  .designintern {
    position: relative;
    height: 100vh;
  }
  .image img {
    width: 350px;
    height: 500px;
    box-shadow: rgba(50, 50, 93, 0.25) 0px 50px 100px -20px,
      rgba(0, 0, 0, 0.3) 0px 30px 60px -30px;
    object-fit: cover;
    background-size: cover;
    background-position: center;
  }
  .designintern h2 {
    font-size: 3rem;
    line-height: 3rem;
    font-weight: 100;
    padding: 2% 2%;
  }
}
</style>
