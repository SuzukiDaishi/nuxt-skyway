<template>
  <skyway-video :room-name="roomName" :user-name="userName"></skyway-video>
</template>
<script lang="ts">
import Vue from 'vue'
import SkywayVideo from '@/components/SkywayVideo.vue'
export default Vue.extend({
  components: {
    SkywayVideo
  },
  data: () => ({
    roomName: 'sample'
  }),
  computed: {
    userName(): string {
      return this.makeRandum(10)
    }
  },
  methods: {
    makeRandum(retLength: number): string {
      // 生成する文字列に含める文字セット
      const chars: string = 'abcdefghijklmnopqrstuvwxyz0123456789'
      const charsLength: number = chars.length
      const ret: string[] = [...Array(retLength)].map((): string => {
        return chars[Math.floor(Math.random() * charsLength)]
      })
      return ret.join('')
    }
  }
})
</script>