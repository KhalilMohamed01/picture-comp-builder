<template>
  <div>
    <div class="preview">
      <div :style="changeBackground(componentElements[3].choosedSide, componentElements[3].choosedColor1, componentElements[3].choosedColor2)" class="pic-component">
        <div class="container">
          <div class="header-content">
            <div class="row g-0">
              <div class="col-lg-6">
                <div style="margin-top: 26%"></div>
                <div @click="$emit('isFocused', 0)" contenteditable="true">
                  <div>
                    <p
                      :style="
                        updateCSS(
                          componentElements[0].txtcolor,
                          componentElements[0].bgcolor,
                          componentElements[0].isHighlited
                        )
                      "
                      :class="[
                        {
                          'text-decoration-underline':
                            componentElements[0].underlineBool,
                          'fst-italic': componentElements[0].italicBool,
                          'fw-bolder': componentElements[0].boldBool,
                          'text-start': componentElements[0].startBool,
                          'text-center': componentElements[0].centerBool,
                          'text-end': componentElements[0].endBool,
                          'text-decoration-line-through':
                            componentElements[0].strikeThroughBool,
                        },
                        componentElements[0].fontSize,
                      ]"
                    >
                      Make your day happier
                    </p>
                  </div>
                </div>
                <div @click="$emit('isFocused', 1)" contenteditable="true">
                  <div class="resizeable">
                    <p
                      :style="
                        updateCSS(
                          componentElements[1].txtcolor,
                          componentElements[1].bgcolor,
                          componentElements[1].isHighlited
                        )
                      "
                      :class="[
                        {
                          'text-decoration-underline':
                            componentElements[1].underlineBool,
                          'fst-italic': componentElements[1].italicBool,
                          'fw-bolder': componentElements[1].boldBool,
                          'text-start': componentElements[1].startBool,
                          'text-center': componentElements[1].centerBool,
                          'text-end': componentElements[1].endBool,
                          'text-decoration-line-through':
                            componentElements[1].strikeThroughBool,
                        },
                        componentElements[1].fontSize,
                        componentElements[1].lineHeight,
                      ]"
                    >
                      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Etiam semper facilisis ligula a euismod. Proin egestas sodales mi et tempus.Etiam semper facilisis ligula a euismod. Proin egestas sodales mi et tempus.
                    </p>
                  </div>
                </div>
                <div class="text-center">
                  <a v-for="(button, index) in componentElements[4].buttons" :key="index" :style="changeButton(button.btnTextColor,button.btnBgColor)" :href="button.btnLink"  class="theme-btn">{{ button.btnText }}</a>
                </div>
                </div>
              <div class="col-lg-6">
                <div style="margin-top: 12%"></div>
                <img
                  @click="$emit('isFocused', 3)"
                  :src="componentElements[5].imgUrl"
                  :class="componentElements[5].imgShape + ' img-fluid'"
                  :alt="componentElements[5].imgAlt"
                />
              </div>
            </div>
          </div>
        </div>
        <svg
          class="wave"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 1440 320"
        >
          <path 
            :fill="componentElements[2].color"
            :fill-opacity="componentElements[2].opacity"
            :d="componentElements[2].waveStyle[componentElements[2].selectedShape].shape"
          ></path>
        </svg>
      </div>
    </div>
    
  </div>
</template>

<script>
export default {
  props: {
    componentElements: Array,
  },
  methods: {
    updateCSS(txtcolor, bgcolor, isHighlited) {
      let updatedCSS;
      if (isHighlited) {
        updatedCSS = "color:" + txtcolor + ";background:" + bgcolor + ";";
        return updatedCSS;
      } else {
        updatedCSS = "color:" + txtcolor + ";background:transparent;";
        return updatedCSS;
      }
    },
    changeBackground(choosedSide, choosedColor1, choosedColor2) {
            return (
                "background-image: linear-gradient(" +
                choosedSide +
                "," +
                choosedColor1 +
                "," +
                choosedColor2 +
                ");"
            );
        },

    changeButton(textcolor, bgcolor) {
            return (
                "background:" +
                bgcolor +
                ";color:" +
                textcolor 
            );
        },
  },
};
</script>

<style>
.preview {
  height: 100vh;
  overflow-y: auto;
  margin: 0px;
  color: blueviolet;
  background-color: #2b2b33;
}

.header-content {
  z-index: 1;
  position: relative;
}

.header-content h1 {
  font-size: 45px;
  font-weight: bold;
  text-transform: capitalize;
  color: white;
}

.header-content p {
  font-size: 20px;
  margin: 20px 0 25px;
  color: white;
  letter-spacing: 1px;
  font-weight: 300;
  text-transform: capitalize;
}

.theme-btn {
  border-radius: 50px;
  padding: 15px 30px;
  min-width: 170px;
  border: 2px solid white;
  font-size: 14px;
  text-transform: uppercase;
  margin-top: 13px;
  display: inline-block;
  text-align: center;
  margin-right: 12px;
  transition: all 0.5s ease-in;
  font-weight: bold;
}

.theme-btn:hover {
  text-decoration: none;
  background-color: #fff;
  color: #9f1b53;
}

.img-responsive {
  width: 100%;
  height: auto;
  max-width: 600px;
  max-height: 500px;
}

.sha-1{
    -webkit-mask: url(@/assets/shape1.svg) center/contain no-repeat;
    max-width: 100%
}

.sha-2{
    -webkit-mask: url(@/assets/shape2.svg) center/contain no-repeat;
    max-width: 100%
}
.sha-3{
    -webkit-mask: url(@/assets/shape2.svg) center/contain no-repeat;
    max-width: 100%
}
</style>
