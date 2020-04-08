<template>
  <div class="MainP2">
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

                    <!-- Spacer -->
                    <div class="vertdiv"/>

                    <!-- Button -->
                    <button class="button" id="TestButton">Test Button</button>

                    </div>
                  </div>
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
  console.log($Input1Text)
}

/* Button On Click Stuff (Easiest way due to the way vuejs functions) */
var addHandlers = function () {
  const $Button1 = document.querySelector("#TestButton")

  $Button1.addEventListener('click', () => {
      button1func()
   });
}


export default {
  name: 'MainP2',
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
