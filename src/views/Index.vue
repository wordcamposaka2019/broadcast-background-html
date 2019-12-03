<template>
  <div class="home">
    <div id="SlideView" class="slide_view"></div>
    <EventInfo class="event_info"/>
    <SessionInfo class="session_info"/>
    <div id="SpeakerView" class="speaker_view"></div>
  </div>
</template>

<script>
// @ is an alias to /src
import EventInfo from '@/components/EventInfo.vue'
import SessionInfo from '@/components/SessionInfo.vue'

export default {
  name: 'index',
  components: {
    EventInfo,
    SessionInfo
  }
}
</script>

<style>
  img {
    max-width: 100%;
  }
  .home {
    width: 100%;
    display: flex;
    flex-wrap: wrap;
  }
  .slide_view {
    width: 70vw;
    height: calc((70vw / 16) * 9);
  }
  .event_info {
    width: 30vw;
    height: calc((70vw / 16) * 9);
  }
  .session_info {
    width: 70vw;
    height: calc((30vw / 16) * 9);
  }
  .speaker_view {
    width: 30vw;
    height: calc((30vw / 16) * 9);
  }
</style>