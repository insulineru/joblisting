<template>
  <div class="filter">
    <div class="tag-list">
      <div class="tag"  v-for="filter in filters" :key="filter">
        {{ filter }}
        <button class="remove-button" @click="$emit('removeFilter', filter)"></button>
      </div>
    </div>
    <div class="filter-controls">
      <button class="clear-button" @click="$emit('clearAll')">Clear</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'JobFilter',
  props: {
    filters: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped>
.filter {
  position: absolute;
  top: 120px;
  width: calc(100% - 88px);
  margin: 0 24px;
  padding: 20px;
  background-color: #ffffff;
  z-index: 10;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.tag-list {
  display: flex;
  flex-wrap: wrap;
}

.tag {
  padding: 4px 40px 4px 8px;
  background-color: hsl(180, 52%, 96%);
  color: hsl(180, 29%, 50%);
  font-weight: 700;
  font-size: 13px;
  line-height: 24px;
  border-radius: 4px;
  position: relative;
  margin: 0 16px 8px 0;
}

.remove-button {
  appearance: none;
  border: 0;
  position: absolute;
  right: 0;
  top: 0;
  height: 100%;
  width: 32px;
  background-color: hsl(180, 29%, 50%);
  background-image: url("../assets/images/icon-remove.svg");
  background-position: center center;
  background-repeat: no-repeat;
  border-radius: 0 4px 4px 0;
  cursor: pointer;
  transition: background-color 0.15s ease;
}

.close-button:hover {
  background-color: hsl(180, 14%, 20%);
}

.clear-button {
  cursor: pointer;
  font-weight: 700;
  font-size: 13px;
  line-height: 24px;
  color: hsl(180, 8%, 52%);
  margin-left: 8px;
  transition: color 0.15s ease;
  appearance: none;
  border: 0;
  background-color: transparent;
}

.clear-button:hover {
  color: hsl(180, 29%, 50%);
  text-decoration: underline;
}

@media screen and (min-width: 1440px) {
  .filter {
    width: 1206px;
    margin: 0 auto;
    left: 0;
    right: 0;
    padding: 20px 40px;
  }
}
</style>
