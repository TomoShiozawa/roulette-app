<template>
  <h1>Raffle</h1>
  <TextArea v-model="items2" cols="20" rows="10" />
  {{ items2 }}
</template>

<script>
export default {
  name: 'Raffle',
  data() {
    return {
      items2: null,
    };
  },
};
</script>

<style></style>
