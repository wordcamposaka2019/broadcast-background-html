<template>
  <div class="event_info">
    <div class="hashtag">{{ hashtag }}</div>
  </div>
</template>

<script>
export default {
  name: 'EventInfo',
  data () {
    return {
      hashtag: '#wpmeetuposaka',
    }
  }
}
</script>

<style scoped>
  .event_info {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: flex-end;
  }
  .hashtag {
    display: inline-block;
    padding: calc((1vw / 16) * 9) calc((2vw / 16) * 9);
    background-color: #1da1f2;
    font-size: 36em;
    font-weight: bold;
    margin-bottom: calc((3vw / 16) * 9);
    color: #ffffff;
    border-radius: calc((1vw / 16) * 9);
    box-shadow: 0 1px 5px rgba(0,0,0,.2);
  }
</style>
