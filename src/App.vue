<script setup>
import { useReward } from 'vue-rewards'
const { reward: confettiReward, isAnimating: isConfettiAnimating } = useReward('confetti-elem', 'confetti');
const { reward: balloonsReward, isAnimating: isBalloonsAnimating } = useReward('balloons-elem', 'balloons');
const { reward: emojiReward, isAnimating: isEmojiAnimating } = useReward('emoji-elem', 'emoji');
const { reward: fullPageReward, isAnimating: isFullPageAnimating } = useReward('full-page', 'confetti', {startVelocity:10, spread:180, elementCount:100 });
</script>

<template>
  <div id="full-page">

  </div>
  <div class="mb">
    <img height="200" src="./assets/logo.svg">
  </div>
  <div>
    <button @click="confettiReward" id="confetti-elem" class="mx">
      Confetti
    </button>
    <button @click="balloonsReward" id="balloons-elem" class="mx">
      Balloons
    </button>
    <button @click="emojiReward" id="emoji-elem" class="mx">
      Emojis
    </button>
    <button @click="() => {confettiReward();balloonsReward();emojiReward();}" class="mx">
      All 3
    </button>
    <button @click="fullPageReward" class="mx">
      Full page
    </button>
  </div>
  <div>
    <a href="https://github.com/HamadaFMahdi/vue-rewards" target="_blank">
      VueRewards Github Repo
    </a>
    <a href="https://github.com/HamadaFMahdi/vue-rewards-demo" target="_blank">
      Github Repo for this demo
    </a>

  </div>
</template>

<style scoped>
.mb {
  margin-bottom: 20px;
}
.mx {
  margin-left: 30px;
  margin-right: 30px;
}

#full-page {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -10;
}
</style>
