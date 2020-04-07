<template>
  <div class="MainP1">
      <section class="section is-medium">
        <div class="container">

          <!-- Main Columns -->
          <div class="columns">

            <div class="column is-three-fifths">
              <!-- First Message -->
              <article class="message is-dark">
                <div class="message-header">
                  <font size="4">Title</font>
                </div>
                
                <div class="message-body">

                  <div class="columns">
                    <div class="column is-half">

                     <!-- Text Input -->
                    <input class="input" type="text" id="TestInput" placeholder="Test Input">

                     <!-- Slider -->
                    <form oninput="result.value=parseInt(sliderWithValue.value)" style="padding-top: 15px; padding-bottom: 10px;">
                        <div class=slidertext><p>Test Slider</p></div>
                        <input class="slider is-fullwidth has-output" step="1" min="1" max="100" value="50" type="range" id="sliderWithValue" name="sliderWithValue">
                        <output name="result" for="sliderWithValue">50</output>
                    </form>

                    <!-- Button -->
                    <button class="button" id="TestButton">Test Button</button>

                    </div>
                  </div>
                </div>
              </article>
            </div>

             <!-- Second Message -->
            <div class="column is-two-fifths">
             <article class="message is-dark">
                <div class="message-header">
                  Message Title
                </div>
                
                <div class="message-body">
                  Message Body
                </div>
              </article>
             </div>
          </div>

        </div>
      </section>

  </div>
</template>

<script>

/* Example Function */
const button1func = function () {
  const $Input1Text = document.querySelector("#TestInput").value
  const $SliderVal = document.querySelector("#sliderWithValue").value

  var i;
  for (i = 0; i < $SliderVal; i++) {
      console.log($Input1Text)
  }
}

/* Button On Click Stuff (Easiest way due to the way vuejs functions) */
var addHandlers = function () {
  const $Button1 = document.querySelector("#TestButton")

  $Button1.addEventListener('click', () => {
      button1func()
   });
}


export default {
  name: 'MainP1',
  props: {
  },
  mounted: function () {
    addHandlers()
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

@import 'src/assets/MainPanel.scss';

</style>
