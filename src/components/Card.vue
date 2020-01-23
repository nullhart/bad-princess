<template>
  <div class="card">
    <!-- heart -->
    <div class="heart">
      <div class="wishlist-heart-group">
        <input name="product-333" id="product-333" data-product-id="333" type="checkbox" />
        <label for="product-333" data-hover-text="Wish List">
          <svg
            xmlns:dc="http://purl.org/dc/elements/1.1/"
            xmlns:cc="http://creativecommons.org/ns#"
            xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"
            xmlns:svg="http://www.w3.org/2000/svg"
            xmlns="http://www.w3.org/2000/svg"
            xmlns:sodipodi="http://sodipodi.sourceforge.net/DTD/sodipodi-0.dtd"
            xmlns:inkscape="http://www.inkscape.org/namespaces/inkscape"
            version="1.1"
            x="0px"
            y="0px"
            viewBox="0 0 100 100"
          >
            <g transform="translate(0,-952.36218)">
              <path
                style="color:#000000;enable-background:accumulate;"
                d="m 34.166665,972.36218 c -11.41955,0 -19.16666,8.91891 -19.16666,20.27029 0,19.45943 15,27.56753 35,39.72973 20.00001,-12.1622 34.99999,-20.2703 34.99999,-39.72973 0,-11.35137 -7.7471,-20.27029 -19.16665,-20.27029 -7.35014,0 -13.39148,4.05405 -15.83334,6.48647 -2.44185,-2.43241 -8.48319,-6.48647 -15.83334,-6.48647 z"
                fill="transparent"
                id="heart-path"
                stroke="#ff99c5"
                stroke-width="5"
                marker="none"
                visibility="visible"
                display="inline"
                overflow="visible"
              />
            </g>
          </svg>
        </label>
      </div>
    </div>

    <img class="card-image" :src="ImageSrc" />
    <div class="card-line"></div>
    <div class="card-button">
      <div class="card-button-text">{{ButtonText}}</div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["ImageSrc", "ButtonText", "Hearted"],
  data: function() {
    return {};
  },
  methods: {
    HeartItem: () => {
      console.log("Heart Item");
    }
  }
};
</script>

<style lang="scss">
.heart {
  right: 0px;
}
.wishlist-heart-group {
  $size: 40px;
  $heart-color: #ff99c5;
  display: inline-block;
  height: $size;
  position: relative;
  width: $size;
  input[type="checkbox"] {
    // Hide the checkbox, but leave it accessible
    left: -999999px;
    position: absolute;
    top: -999999px;
    & + label svg {
      // Set the base rotation
      transform: rotate(0deg);
    }
    &:checked + label svg {
      // Wiggle Animation on check
      animation: wishlist-heart-wiggle 400ms 50ms forwards ease-in-out;
    }
    &:checked + label svg #heart-path {
      // SVG animation on check
      animation: wishlist-heart-add 300ms forwards;
      stroke: $heart-color;
    }
    & + label svg #heart-path {
      // Transition the fill
      transition: fill 200ms;
    }
    & + label:hover svg #heart-path {
      transition: stroke 150ms linear;
      stroke: $heart-color;
    }
    & + label:before {
      // Color Accessibility For Red Deficient
      align-items: center;
      background-color: #000;
      border-radius: 3px;
      box-sizing: border-box;
      color: #fff;
      content: attr(data-hover-text);
      display: flex;
      font-size: 0.8em;
      height: 25px;
      justify-content: center;
      left: 50%;
      line-height: 1;
      opacity: 0;
      padding: 0.5em;
      position: absolute;
      text-align: center;
      top: -2.25em;
      transform: translateX(-50%);
      transition: opacity 100ms linear;
      white-space: pre;
    }
    & + label:hover:before {
      opacity: 1;
      transition-delay: 400ms;
    }
  }
  label {
    display: inline-block;
    position: relative;
    width: 100%;
  }

  @keyframes wishlist-heart-wiggle {
    0% {
      transform: rotate(0deg);
    }
    25% {
      transform: rotate(-10deg);
    }
    75% {
      transform: rotate(8deg);
    }
    100% {
      transform: rotate(0deg);
    }
  }

  @keyframes wishlist-heart-add {
    0% {
      stroke-width: 5;
    }
    50% {
      stroke-width: 20;
    }
    100% {
      fill: $heart-color;
      stroke-width: 5;
    }
  }
}

.card {
  display: grid;
  width: 350px;
  height: 300px;
  min-width: 350px;
  min-height: 300px;
  background-color: white;
  margin: auto;
  margin-top: 50px;
  border-radius: 15px;
  border: 3px solid rgb(255, 153, 197);
  /* Layout */
  grid-template-rows: 0px 240px 3px 57px;
  grid-template-columns: 100%;

  overflow: hidden;
}

.card-image {
  margin: auto;
  max-height: 240px;
}

.card-line {
  background-color: rgb(255, 153, 197);
}

.card-button {
  display: grid;
  margin: auto;

  width: 100%;
  height: 100%;
  background-color: rgb(255, 153, 197);
}

.card-button-text {
  margin: auto;
  color: white;
  font-size: 1.5em;
}

.card-button:hover {
  background-color: #ffcae1;
}
</style>