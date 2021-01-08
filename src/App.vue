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
    <p>Coded with love by John Philip</p>
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
    console.log("Hire Me! abeg");
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
  margin: 0 !important;
  padding: 0;
  box-sizing: border-box;
  color: white;
}

.designintern {
  width: 100%;
  position: relative;
  background: linear-gradient(
    to right,
    rgb(212, 42, 93) 0%,
    rgb(212, 42, 93) 50%,
    rgb(185, 29, 102) 50%,
    rgb(185, 29, 102) 100%
  );
  overflow: hidden;
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
  top: 40%;
  left: 90%;
}
.socialmedia img {
  width: 60px;
  height: 60px;
}
.socialmedia a {
  display: inline-block;
  transform: scale(0.5);
  transition: 0.5s;
}
.socialmedia a:hover {
  transform: scale(0.5) translateY(-15px);
}
.socialmedia div {
  margin-bottom: 2%;
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
p {
  font-size: 1rem;
}
@media (max-width: 720px) {
  .designintern {
    width: 100%;
    overflow: hidden;
  }
  .menu ul li {
    padding-right: 1%;
    letter-spacing: 1px;
  }
  .menu ul li img {
    width: 60px;
    height: 60px;
    border-radius: 50%;
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
  }
  .menu {
    padding-top: 4rem;
    padding-bottom: 2rem;
  }
}
</style>
