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
import moment from 'moment';
export default {
  name: 'SessionInfo',
  data () {
    return {
      now: new Date(),
      speakerName: null,
      speakerIcon: null,
      sessionTitle: null,
      sessionStart: null,
      sessionEnd: null,
      session: {
        op: {
          startTime: '10:10:00',
          endTime: '10:40:00',
          name: 'WordCamp Osaka 2019 実行委員長',
          title: 'WordCamp Osaka 2019 開会挨拶',
          description: '',
          gravatarMD5Hash: '',
        },
        session01: {
          startTime: '10:40:00',
          endTime: '11:40:00',
          name: 'shohei.tanaka',
          title: '任意団体（特にPTA）で WordPress を活用する方法',
          description: '',
          gravatarMD5Hash: '677e512c803c40c0180d4514f876a21f',
        },
        session02: {
          startTime: '11:40:00',
          endTime: '12:40:00',
          name: 'Ana García López',
          title: 'The power of the events — offline magic for your WordPress business',
          description: '',
          gravatarMD5Hash: 'b53ca10cce9d480b297b796feb91db8e',
        },
        lt1: {
          startTime: '13:15:00',
          endTime: '13:50:00',
          name: 'WordCamp Osaka 2019',
          title: 'ランチタイムLT(ライトニングトーク)',
          description: '',
          gravatarMD5Hash: '',
        },
        session03: {
          startTime: '13:50:00',
          endTime: '14:50:00',
          name: 'ササキカオリ',
          title: '子育てしながら通勤・リモートワーク・フリーランス！ きっかけを活かしWordPressで実現した複業という働き方',
          description: '',
          gravatarMD5Hash: '3918916f720b9385d13eb500d28d14d8',
        },
        session04: {
          startTime: '14:50:00',
          endTime: '15:50:00',
          name: 'Néstor Angulo de Ugarte',
          title: 'Hacking WordPress & countermeasures.',
          description: '',
          gravatarMD5Hash: '090b1ad905d338638025bef3598c93c5',
        },
        session05: {
          startTime: '15:50:00',
          endTime: '16:45:00',
          name: '石田 美穂（いしだみほ / みほじさん）',
          title: '現役アフィリエイターが教える、現場で使えるWebマーケティング',
          description: '',
          gravatarMD5Hash: 'eb79be5d40108d7e07e8a50e9ef46c9a',
        },
        session06: {
          startTime: '16:50:00',
          endTime: '17:45:00',
          name: 'Mike Schroder',
          title: 'The Future of WordPress',
          description: '',
          gravatarMD5Hash: '46fa959634a063abefcac94eaf191eca',
        },
        lt2: {
          startTime: '17:45:00',
          endTime: '18:05:00',
          name: 'WordCamp Osaka 2019',
          title: 'LT(ライトニングトーク)タイム',
          description: '',
          gravatarMD5Hash: '',
        },
        ed: {
          startTime: '18:05:00',
          endTime: '18:30:00',
          name: 'WordCamp Osaka 2019 実行委員長',
          title: 'WordCamp Osaka 2019 閉会挨拶',
          description: '',
          gravatarMD5Hash: '',
        },
        after: {
          startTime: '18:15:00',
          endTime: '20:40:00',
          name: 'WordCamp Osaka 2019',
          title: '懇親会ゲリラ配信',
          description: '',
          gravatarMD5Hash: '',
        },
        default: {
          startTime: '00:00:00',
          endTime: '23:59:59',
          name: 'WordCamp Osaka 2019',
          title: 'WordCamp Osaka 2019 セッションデイ 常翔ホール リアルタイム配信',
          description: '',
          gravatarMD5Hash: '',
        },
      }
    }
  },
  filters: {
    moment: function (date) {
      return moment(date).format('HH:mm');
    }
  },
  mounted: function () {
    var toDoubleDigits = function(num) {
      num += "";
      if (num.length === 1) {
        num = "0" + num;
      }
      return num;
    };
    var hh = toDoubleDigits(this.now.getHours());
    var mi = toDoubleDigits(this.now.getMinutes());
    var se = toDoubleDigits(this.now.getMinutes());
    const nowTime = hh + ':' + mi + ':' + se;
    console.log(nowTime);

    if ( nowTime >= this.session.op.startTime && nowTime < this.session.op.endTime ) {
      const sessionData = this.session.op;
      this.speakerName = 'Speaker : ' + sessionData.name;
      this.speakerIcon = 'https://pbs.twimg.com/profile_images/1162163787421454336/9oHVfKNL_400x400.jpg';
      this.sessionTitle = sessionData.title;
      this.sessionStart = sessionData.startTime;
      this.sessionEnd = sessionData.endTime;
    } else if ( nowTime >= this.session.session01.startTime && nowTime < this.session.session01.endTime ) {
      const sessionData = this.session.session01;
      this.speakerName = 'Speaker : ' + sessionData.name;
      this.speakerIcon = 'https://secure.gravatar.com/avatar/' + sessionData.gravatarMD5Hash + '?s=400&d=mm&r=g';
      this.sessionTitle = sessionData.title;
      this.sessionStart = sessionData.startTime;
      this.sessionEnd = sessionData.endTime;
    } else if ( nowTime >= this.session.session02.startTime && nowTime < this.session.session02.endTime ) {
      const sessionData = this.session.session02;
      this.speakerName = 'Speaker : ' + sessionData.name;
      this.speakerIcon = 'https://secure.gravatar.com/avatar/' + sessionData.gravatarMD5Hash + '?s=400&d=mm&r=g';
      this.sessionTitle = sessionData.title;
      this.sessionStart = sessionData.startTime;
      this.sessionEnd = sessionData.endTime;
    } else if ( nowTime >= this.session.lt1.startTime && nowTime < this.session.lt1.endTime ) {
      const sessionData = this.session.lt1;
      this.speakerName = 'Speaker : ' + sessionData.name;
      this.speakerIcon = 'https://pbs.twimg.com/profile_images/1162163787421454336/9oHVfKNL_400x400.jpg';
      this.sessionTitle = sessionData.title;
      this.sessionStart = sessionData.startTime;
      this.sessionEnd = sessionData.endTime;
    } else if ( nowTime >= this.session.session03.startTime && nowTime < this.session.session03.endTime ) {
      const sessionData = this.session.session03;
      this.speakerName = 'Speaker : ' + sessionData.name;
      this.speakerIcon = 'https://secure.gravatar.com/avatar/' + sessionData.gravatarMD5Hash + '?s=400&d=mm&r=g';
      this.sessionTitle = sessionData.title;
      this.sessionStart = sessionData.startTime;
      this.sessionEnd = sessionData.endTime;
    } else if ( nowTime >= this.session.session04.startTime && nowTime < this.session.session04.endTime ) {
      const sessionData = this.session.session04;
      this.speakerName = 'Speaker : ' + sessionData.name;
      this.speakerIcon = 'https://secure.gravatar.com/avatar/' + sessionData.gravatarMD5Hash + '?s=400&d=mm&r=g';
      this.sessionTitle = sessionData.title;
      this.sessionStart = sessionData.startTime;
      this.sessionEnd = sessionData.endTime;
    } else if ( nowTime >= this.session.session05.startTime && nowTime < this.session.session05.endTime ) {
      const sessionData = this.session.session05;
      this.speakerName = 'Speaker : ' + sessionData.name;
      this.speakerIcon = 'https://secure.gravatar.com/avatar/' + sessionData.gravatarMD5Hash + '?s=400&d=mm&r=g';
      this.sessionTitle = sessionData.title;
      this.sessionStart = sessionData.startTime;
      this.sessionEnd = sessionData.endTime;
    } else if ( nowTime >= this.session.session06.startTime && nowTime < this.session.session06.endTime ) {
      const sessionData = this.session.session06;
      this.speakerName = 'Speaker : ' + sessionData.name;
      this.speakerIcon = 'https://secure.gravatar.com/avatar/' + sessionData.gravatarMD5Hash + '?s=400&d=mm&r=g';
      this.sessionTitle = sessionData.title;
      this.sessionStart = sessionData.startTime;
      this.sessionEnd = sessionData.endTime;
    } else if ( nowTime >= this.session.lt2.startTime && nowTime < this.session.lt2.endTime ) {
      const sessionData = this.session.lt2;
      this.speakerName = 'Speaker : ' + sessionData.name;
      this.speakerIcon = 'https://pbs.twimg.com/profile_images/1162163787421454336/9oHVfKNL_400x400.jpg';
      this.sessionTitle = sessionData.title;
      this.sessionStart = sessionData.startTime;
      this.sessionEnd = sessionData.endTime;
    } else if ( nowTime >= this.session.ed.startTime && nowTime < this.session.ed.endTime ) {
      const sessionData = this.session.ed;
      this.speakerName = 'Speaker : ' + sessionData.name;
      this.speakerIcon = 'https://pbs.twimg.com/profile_images/1162163787421454336/9oHVfKNL_400x400.jpg';
      this.sessionTitle = sessionData.title;
      this.sessionStart = sessionData.startTime;
      this.sessionEnd = sessionData.endTime;
    } else if ( nowTime >= this.session.after.startTime && nowTime < this.session.after.endTime ) {
      const sessionData = this.session.after;
      this.speakerName = 'Speaker : ' + sessionData.name;
      this.speakerIcon = 'https://pbs.twimg.com/profile_images/1162163787421454336/9oHVfKNL_400x400.jpg';
      this.sessionTitle = sessionData.title;
      this.sessionStart = sessionData.startTime;
      this.sessionEnd = sessionData.endTime;
    } else {
      const sessionData = this.session.default;
      this.speakerName = 'Speaker : ' + sessionData.name;
      this.speakerIcon = 'https://pbs.twimg.com/profile_images/1162163787421454336/9oHVfKNL_400x400.jpg';
      this.sessionTitle = sessionData.title;
      this.sessionStart = sessionData.startTime;
      this.sessionEnd = sessionData.endTime;
    }
  },
}
</script>

