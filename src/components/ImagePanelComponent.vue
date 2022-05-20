<template>
  <div class="customize-panel">
    <div class="block-title"><i class="fa-solid fa-image"></i> Image</div>
    <div class="block-tools">
      <table style="color: #fff" class="table table-sm table-borderless">
        <tr>
          <td>Image :</td>
          <td>
            <input @change="$emit('updateData', componentElementsCopy)" type="text" v-model="componentElementsCopy[5].imgUrl" />
          </td>
        </tr>
        <tr>
          <td>Description :</td>
          <td>
            <input @change="$emit('updateData', componentElementsCopy)" type="text" v-model="componentElementsCopy[5].imgAlt" />
          </td>
        </tr>
        <tr>
          <td>Shape :</td>
          <td>
            <select @change="$emit('updateData', componentElementsCopy)"  v-model="componentElementsCopy[5].imgShape" class="custom-select" aria-label=".form-select-sm example">
              <option value="sha-0">
                <label class="custom-select-option" for="s2">None</label>
              </option>
              <option value="sha-1">
                <label class="custom-select-option" for="s2">Shape 1</label>
              </option>
              <option value="sha-2">
                <label class="custom-select-option" for="s2">Shape 2</label>
              </option>
              <option value="sha-3">
                <label class="custom-select-option" for="s2">Shape 3</label>
              </option>
            </select>
          </td>
        </tr>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    componentElements: Array,
  },
  mounted() {
    this.componentElementsCopy = this.componentElements;
  },
  data() {
    return {
      componentElementsCopy: null,
    };
  },
};
</script>

<style>
.customize-panel {
  padding-top: 1px;
  background: #3e3e46;
  border-top: 1px solid black;
  border-bottom: 1px solid black;
  margin-bottom: 3px;
}

.block-title {
  background: #2b2b33;
  text-align: left;
  text-transform: uppercase;
  font-weight: bold;
  font-size: 12px;
  letter-spacing: 1px;
  padding-left: 10px;
  border-bottom: 1px solid black;
}

.block-tools {
  text-align: left;
  padding: 5px;
}

table td {
  color: white;
}
input{
    color:white
}
</style>