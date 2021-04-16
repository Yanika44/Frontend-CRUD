<template>
  <div class="about">
    <div class="slide_show ml-10 mb-80" id="ss_demo">
      <img src="@/assets/1.jpg" alt="No photo." width="450" height="400" />
      <img src="@/assets/2.jpg" alt="No photo." width="450" height="400" />
      <img src="@/assets/3.jpg" alt="No photo." width="450" height="400" />
    </div>

    <div class="ml-96 pl-72 -mt-32 text-2xl font-bold font-serif">
      <p>
        Our restaurant was built in 2009 with the intention of creating food for
        health. We've put great emphasis on health, so our restaurant focuses on
        healthy food. Which tastes delicious and pleasing to Thai people,
        therefore can enjoy all generations. If interested, please order food
        <router-link
          to="/menu"
          class="px-1 text-yellow-500 underline hover:text-red-700"
          >here</router-link
        >.
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "About",
  methods: {
    playSlideShow(id) {
      function show(n) {
        var imgs = document.getElementById(id).getElementsByTagName("img");
        var l = imgs.length;
        n = n == l ? 0 : n;

        for (var a = 0; a < l; a++) {
          var img = imgs[a];
          if (a == n) {
            img.className = "select";
          } else {
            img.className = "";
          }
        }
        return n;
      }

      var position = show(0);
      window.setInterval(function () {
        position = show(position + 1);
      }, 3000);
    },
  },
  mounted(){
    this.playSlideShow("ss_demo");

  }
};

</script>

<style>
.slide_show {
  position: relative;
  display: inline-block;
  width: 100%;
}
.slide_show img {
  position: absolute;
  left: 0;
  top: 0;
  transition: 1s;
  opacity: 0;
}
.slide_show img.select {
  opacity: 1;
}
</style>



