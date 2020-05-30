<template>
  <div class="app-container">
    <transition name="step-aside" mode="out-in">
      <div v-if="showText" class="cover-container" key="cover">
        <span id="hold-the-line">Hold the line</span>
        <div class="text-spacing" />
        <span id="love-isnt-always">Love isn't always</span>
        <span id="on">- on -</span>
        <span id="time">time</span>
        <button @click="showText = false">> My thoughts</button>
      </div>
      <div v-if="!showText" class="explaination-content" key="explaination">
        <span class="header">
          Love timing is different for all of us.
        </span>

        <span>
          Sometimes when we haven't found love,
          we believe it doesn't exist and that it will never come.
        </span>

        <span>
          This phrase, along with the upbeat timbre of the song,
          brings me hope and to never give up on love.
        </span>

        <span>
          To hold the line and dont hang up on love, whose timing
          may not be the one that you expect.
        </span>
        <button @click="showText = true">Go back to cover</button>
      </div>
    </transition>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      showText: true,
    };
  },
};
</script>

<style>
body {
  min-height: 100vh;
  height: fit-content;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin: 0;
  padding: 0;
  background: linear-gradient(to bottom, #c33764, #1d2671);
  font-family: 'Lato', sans-serif;
  font-size: 1.2rem;
  overflow-x: hidden;
}

.app-container {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: whitesmoke;
  height: 100%;
  width: 100%;
}

.cover-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  position: relative;
  left: 0;
  overflow: hidden;
}

#hold-the-line {
  font-size: 4.8vw;/* 6.4rem */
  font-family: 'Hammersmith One', sans-serif;
  font-weight: bold;
}

.text-spacing {
  height: 8.8vw; /* 12rem */
}

#love-isnt-always {
  font-size: 6vw; /* 8rem */
  margin: -2.4vw 0; /* -3rem 0 */
  font-family: 'Kaushan Script', cursive;

/*
  Other cool fonts that I tried
  font-family: 'Euphoria Script', cursive;
  font-family: 'Satisfy', cursive;
  font-family: 'Qwigley', cursive;
*/
}

#on {
  font-size: 6.4vw; /* 8.8rem */
  margin: -1vw 0; /* 2rem 0 */
  font-family: 'Annie Use Your Telescope', cursive;
}

#time {
  font-size: 7.2vw; /* 10rem */
  margin: -2.4vw 0; /* -3.2rem 0 */
  font-family: 'Carter One', cursive;
}

button {
  background-color: transparent;
  border-radius: 8px;
  margin: 3.2rem 0;
  font-size: 1.32rem;
  padding: 8px 12px;
  color: whitesmoke;
  cursor: pointer;
  transition: all 0.16s ease-in;
}

button:hover {
  background-color: rgba(219, 219, 219, 0.16);
}

.explaination-content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  position: relative;
  left: 0;
  font-size: 2rem;
  padding: 0 10vw;
  overflow: auto;
}

.explaination-content .header {
  font-size: 3.2rem;
}

.explaination-content span {
  margin: 16px 0;
}

/* Transitions */
/* left side */
.step-aside-enter-active, .step-aside-leave-active {
  transition: all .8s ease-in-out;
}

.step-aside-leave {
  left: 0;
}


.step-aside-leave-to {
  left: 50vw;
  opacity: 0;
}

.step-aside-enter {
  left: 60vw;
}

.step-aside-enter-to {
  left: 0;
}
</style>
