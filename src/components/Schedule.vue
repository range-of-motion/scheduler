<template>
  <div class="wrapper">
    <div v-for="(column, i) in columns" :key="'column-' + i" class="column">
        <div v-for="hour in endHour - startHour" :key="'hour-' + hour">
            <div v-for="part in hourParts" :key="'hour_part-' + part" class="part">
                <div v-if="part === 1">{{ startHour + hour - 1 }}:00</div>
            </div>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
      return {
          columns: 4,
          startHour: 8,
          endHour: 17,
          hourParts: 4
      };
  }
};
</script>

<style scoped>
.wrapper {
    margin: 20px auto;
    display: flex;
    max-width: 1200px;
    border-top: 1px solid #CCC;
}

.column {
    flex: 1;
    border-left: 1px solid #CCC;
}

.column:last-child {
    border-right: 1px solid #CCC;
}

.part {
    padding: 0 15px;
    display: flex;
    align-items: center;
    height: 32px;
    border-bottom: 1px solid #CCC;
}
</style>
