<template>
<iframe
  :src="`//web.sdk.qcloud.com/player/tcplayer/samples/vod-player.html?appID=1308879050&fileID=${videoId}&width=560&height=315&psign=${psign}`"
  frameborder="0"
  scrolling="no"
  width="560"
  height="315"
  allowfullscreen>
</iframe>

</template>

<script setup>
const props = defineProps({
  videoId: {
    type: String,
    required: true,
  },
  psign: {
    type: String,
    required: true,
  }
})
</script>


