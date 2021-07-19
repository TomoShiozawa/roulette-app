<template>
  <TabView>
    <TabPanel header="抽選">
      <Raffle />
    </TabPanel>
    <TabPanel header="進数変換">
      <base-converter />
    </TabPanel>
    <TabPanel header="タイマー">
      <Timer />
    </TabPanel>
  </TabView>
</template>

<script>
import Raffle from './raffle/Raffle.vue';
import BaseConverter from './baseconverter/BaseConverter.vue';
import Timer from './timer/Timer.vue';

export default {
  name: 'App',
  components: {
    Raffle,
    BaseConverter,
    Timer,
  },
};
</script>

<style lang="scss"></style>
