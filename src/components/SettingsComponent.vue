<template>
  <div>
        <div class="settings text-center" >
            <div class="settings-title">
                <i class="fa-solid fa-sliders"></i> Settings
            </div>
            <div class="settings-panel">
              <text-panel-component v-if="selectedId === 0 || selectedId === 1" @updateData="$emit('updateData',componentElementsCopy)" :componentElements="componentElements"
            :selectedId="selectedId"></text-panel-component>
                        <image-panel-component :componentElements="componentElements" v-if="selectedId === 3"></image-panel-component>

            <bg-panel-component :componentElements="componentElements" @updateData="$emit('updateData',componentElementsCopy)" ></bg-panel-component>
            <button-panel-component :componentElements="componentElements" @updateData="$emit('updateData',componentElementsCopy)"></button-panel-component>
            </div>
        </div>
            </div>
  
</template>

<script>
import BgPanelComponent from './BgPanelComponent.vue';
import ButtonPanelComponent from './ButtonPanelComponent.vue';
import TextPanelComponent from "./TextPanelComponent.vue";
import ImagePanelComponent from "./ImagePanelComponent.vue";

export default {
  components: {
    TextPanelComponent,
    BgPanelComponent,
    ButtonPanelComponent,
    ImagePanelComponent,
  
  },

  props: {
    componentElements: Array,
    selectedId:Number,
  },
  mounted() {
    this.componentElementsCopy = this.componentElements;
  },
  data() {
    return {
      componentElementsCopy: 1,
    };
  },
};
</script>

<style>
.settings {
    height: 100vh;
    background: #2b2b33;
    text-align: left;
    color: white;
    overflow-y:auto;
}
.settings-title {
  background: #141217;
  text-transform: uppercase;
  padding: 4px;
  font-weight: bold;
  text-align: center;
  font-size: 16px;
  letter-spacing: 1px;
  border-bottom: 1px solid black;
}

.settings-panel {
  padding: 3px;
}



</style>