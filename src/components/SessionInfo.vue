<template>
  <div>
    <div class="session_data time">
      <div class="icon">
        <img :src="speakerIcon">
      </div>
      <div class="data">
        <div class="session_title">{{ sessionTitle }}</div>
        <div class="speaker_name">{{ speakerName }}</div>
      </div>
    </div>
  </div>
</template>

<style scoped>
  .session_data {
    color: #ffffff;
    width: 100%;
    height: calc((30vw / 16) * 9);
    display: flex;
    justify-content: flex-start;
    align-items: center;
    flex-wrap: wrap;
  }
  .icon {
    width: calc((22vw / 16) * 9);
    height: calc((22vw / 16) * 9);
    padding: calc((4vw / 16) * 9);
    object-fit: contain;
  }
  .icon img {
    width: 100%;
    height: 100%;
    border-radius: 50%;
    vertical-align: middle;
  }
  .data {
    flex: 1;
    padding: calc((4vw / 16) * 9) calc((4vw / 16) * 9) calc((4vw / 16) * 9) 0;
    text-align: left;
    line-height: 1.2;
  }
  .session_time {
    margin: 0;
    font-weight: bold;
    font-size: 24em;
  }
  .session_title {
    margin: 0 0 .5em;
    font-size: 48em;
    line-height: 1.5;
  }
  .speaker_name {
    margin: 0;
    font-weight: bold;
    font-size: 30em;
  }
</style>

<script>
export default {
  name: 'SessionInfo',
  data () {
    return {
      speakerName: '了（@ddryo_loos）',
      speakerIcon: 'https://pbs.twimg.com/profile_images/1213968632880877568/NHsyFWnv_400x400.jpg',
      sessionTitle: 'HTMLコーディング皆無！ブロック＆CSSだけでサイトを作ってみよう',
    }
  },
}
</script>

