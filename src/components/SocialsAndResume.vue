<template>
  <div class="social">
    <h1>Find me on</h1>
    <img class="icon gh" @click="goToGithub" src="@/assets/github.png">
    <img class="icon li" @click="goToLinkedin" src="@/assets/linkedin.png">
    <div class="divider" />
    <div class="minor btn" @click="goToResume">Printable Resume</div>
  </div>
</template>

<script>
export default {
  methods: {
    goToGithub() {
      window.open('https://github.com/etekweb', '_blank');
    },
    goToLinkedin() {
      window.open('https://www.linkedin.com/in/ethan-matzdorf-9493b4137/', '_blank');
    },
    goToResume() {
      window.open('https://etekweb.net/resume', '_blank').print();
    }
  }
};
</script>

<style scoped>
.social {
  margin: 57px 0 0 0;
  padding: 32px 0;
  width: 100%;
  background-color: #F0F2F2;
  display: grid;
  gap: 25px;
  grid-auto-flow: column;
  align-items: center;
  justify-items: center;
  justify-content: center;
}
h1 {
  margin: unset;
}
.icon {
  width: 64px;
  height: 64px;
  border-radius: 50%;
  cursor: pointer;
}
.divider {
  width: 1px;
  height: 75px;
  background-color: black;
  margin: 0 15px;
}
/* Social buttons and resume button on separate lines */
@media screen and (max-width: 950px) {
  .divider {
    display: none;
  }
  h1, .icon {
    grid-row: 1 / 2;
  }
  .minor.btn {
    grid-row: 2 / 3;
    grid-column: 1 / 4;
    justify-self: center;
  }
}
/* Text, social buttons, then resume button, all separate lines */
@media screen and (max-width: 515px) {
  .social {
    row-gap: 16px;
  }
  h1 {
    grid-column: 1 / 3;
    justify-self: center;
    line-height: 1em;
  }
  .icon {
    grid-row: 2 / 3;
  }
  .icon.gh {
    justify-self: right;
  }
  .icon.li {
    justify-self: left;
  }
  .minor.btn {
    margin-top: 32px;
    grid-row: 3 / 4;
    grid-column: 1 / 3;
  }
}
</style>