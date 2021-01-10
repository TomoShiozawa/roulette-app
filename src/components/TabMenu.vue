<template>
  <TabView>
    <TabPanel header="抽選">
      <Raffle />
    </TabPanel>
    <TabPanel header="進数変換">
      <base-converter />
    </TabPanel>
  </TabView>
</template>

<script>
import Raffle from './raffle/Raffle.vue';
import BaseConverter from './baseconverter/BaseConverter.vue';

export default {
  name: 'App',
  components: {
    Raffle,
    BaseConverter,
  },
};
</script>

<style lang="scss"></style>
