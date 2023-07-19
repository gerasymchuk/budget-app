<template>
  <div class="multiselect">
    <div class="multiselect-selected">
      <p>Tags</p>
    </div>
    <div class="multiselect-dropdown">
      <div class="multiselect-selected-tags">
        <div
          class="multiselect-tag"
          v-for="(selectedItem, index) in selectedItems"
          :key="index"
        >
          {{ selectedItem }}
          <button @click="removeItem(selectedItem)">X</button>
        </div>
      </div>
      <div
        class="multiselect-option"
        v-for="(option, index) in options"
        :key="index"
      >
        <label>
          <input
            type="checkbox"
            :value="option.label"
            v-model="selectedItems"
          />
          {{ option.label }}
        </label>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const selectedItems = ref([]);
const options = [
  { label: "Option 1", value: "option1" },
  { label: "Option 2", value: "option2" },
  { label: "Option 3", value: "option3" },
];

const removeItem = (item) => {
  selectedItems.value = selectedItems.value.filter((el) => el !== item);
};
</script>

<style scoped>
body {
  background-color: #fcfbfc !important;
}
.multiselect {
  position: relative;
  box-sizing: border-box;
  width: 200px;
  max-width: 400px;
  height: 40px;
  color: #244e48;
  padding: 12px 16px 12px 16px;
  background-color: #eaf8f5;
  cursor: pointer;
  box-shadow: 4px 4px 10px rgba(0, 0, 0, 0.01);
  border-radius: 8px;
}

.multiselect-selected {
  height: 100%;
  width: 100%;
  display: flex;
  align-items: center;
}
.selected-item {
  margin-right: 4px;
}

.multiselect-dropdown {
  position: absolute;
  top: 110%;
  left: 0;
  width: 100%;
  background-color: #fff;
  border-top: none;
  border-radius: 16px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  padding: 8px 12px 12px 12px;
}
.multiselect-selected-tags {
  display: flex;
  min-height: 34px;
  flex-direction: row;
  flex-wrap: wrap;
  background-color: #fcfbfc;
  border: 1.2px solid #5accba;
  border-radius: 8px;
  padding: 6px 6px 2px 6px;
  margin-bottom: 8px;
}
.multiselect-tag {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 2px 6px;
  margin-right: 4px;
  margin-bottom: 4px;
  color: #244e48;
  box-shadow: 4px 4px 10px rgba(0, 0, 0, 0.01);
  border-radius: 4px;
  font-weight: 400;
  font-size: 14px;
  line-height: 18px;
}

.multiselect-tag button {
  display: flex;
  margin-left: 4px;
  padding: 0;
  border: none;
  background-color: #fff;
  cursor: pointer;
}
.multiselect-tag button img {
  width: 14px;
  height: 14px;
}

.multiselect-placeholder {
  color: #244e48;
  font-weight: 400;
  font-size: 14px;
  line-height: 18px;
}

.multiselect-arrow {
  width: 0;
  height: 0;
  border-top: 5px solid #ccc;
  border-right: 5px solid transparent;
  border-left: 5px solid transparent;
  margin-left: auto;
}

.multiselect-option {
  display: flex;
  align-items: center;
  padding: 4px;
  cursor: pointer;
}

.multiselect-option input[type="checkbox"] {
  margin-right: 4px;
  cursor: pointer;
}

.multiselect-option:hover {
  background-color: #eaf8f5;
  border-radius: 4px;
}
/* .multiselect-search input,
.multiselect-search input:focus,
.multiselect-search input:active {
  appearance: none;
  background-color: transparent;
  border: none;
} */
</style>
