<template>
  <span>Next Task unlocks in {{ time_left }}</span>
</template>

<script setup lang="ts">
let time_left = ref('unknown');
useFetch('/api/task/waittime').then((data) => {
  if (data.data.value === null) return;
  if (data.data.value <= 60) {
    time_left.value = 'under a minute!';
    return;
  }

  const days_left = Math.floor(data.data.value / (60 * 60 * 24));
  const hours_left = Math.floor(
    (data.data.value - days_left * 60 * 60 * 24) / (60 * 60),
  );
  const minutes_left = Math.floor(
    (data.data.value - days_left * 60 * 60 * 24 - hours_left * 60 * 60) / 60,
  );

  time_left.value = `${days_left > 0 ? `${days_left} day(s)` : ``}${
    hours_left > 0 ? ` ${hours_left} hour(s)` : ``
  }${minutes_left > 0 ? ` ${minutes_left} minute(s)` : ``}!`;
});
</script>
