<template>
  <div class="main">
    <div class="items">
      <Card
        v-for="(product, i) in products"
        :key="i"
        :ImageSrc="product.image"
        :Hearted="product.hearted"
        ButtonText="ADD TO CART"
      />
    </div>
  </div>
</template>

<style>
/* Main Container */
.main {
  position: relative;
  grid-template-rows: 60px 1fr;
}

.items {
  display: flex;
  flex: 1 1 auto;
  flex-wrap: wrap;
  flex-direction: row;
  /* grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(2, 1fr);
    grid-column-gap: 10px;
    grid-row-gap: 10px; */
  height: 100%;
  width: 100%;
  max-width: 1200px;
  margin: auto;
}
</style>
<script>
import Card from "../components/Card";

export default {
  name: "home",
  components: { Card },
  data: () => {
    return {
      products: [
        {
          price: "1",
          image:
            "https://media.tiffany.com/is/image/Tiffany/EcomItemM/the-tiffany-setting-engagement-ring-in-platinum-22086588_995766_ED_M.jpg?&op_usm=1.75,1.0,6.0&$cropN=0.1,0.1,0.8,0.8&defaultImage=NoImageAvailableInternal&",
          hearted: true
        },
        {
          price: "1",
          image:
            "https://media.tiffany.com/is/image/Tiffany/EcomItemM/the-tiffany-setting-engagement-ring-in-platinum-22086588_995766_ED_M.jpg?&op_usm=1.75,1.0,6.0&$cropN=0.1,0.1,0.8,0.8&defaultImage=NoImageAvailableInternal&",
          hearted: true
        },
        {
          price: "1",
          image:
            "https://media.tiffany.com/is/image/Tiffany/EcomItemM/the-tiffany-setting-engagement-ring-in-platinum-22086588_995766_ED_M.jpg?&op_usm=1.75,1.0,6.0&$cropN=0.1,0.1,0.8,0.8&defaultImage=NoImageAvailableInternal&",
          hearted: true
        },
        {
          price: "1",
          image:
            "https://media.tiffany.com/is/image/Tiffany/EcomItemM/the-tiffany-setting-engagement-ring-in-platinum-22086588_995766_ED_M.jpg?&op_usm=1.75,1.0,6.0&$cropN=0.1,0.1,0.8,0.8&defaultImage=NoImageAvailableInternal&",
          hearted: true
        },
        {
          price: "1",
          image:
            "https://media.tiffany.com/is/image/Tiffany/EcomItemM/the-tiffany-setting-engagement-ring-in-platinum-22086588_995766_ED_M.jpg?&op_usm=1.75,1.0,6.0&$cropN=0.1,0.1,0.8,0.8&defaultImage=NoImageAvailableInternal&",
          hearted: true
        },
        {
          price: "1",
          image:
            "https://media.tiffany.com/is/image/Tiffany/EcomItemM/the-tiffany-setting-engagement-ring-in-platinum-22086588_995766_ED_M.jpg?&op_usm=1.75,1.0,6.0&$cropN=0.1,0.1,0.8,0.8&defaultImage=NoImageAvailableInternal&",
          hearted: true
        },
        {
          price: "1",
          image:
            "https://media.tiffany.com/is/image/Tiffany/EcomItemM/the-tiffany-setting-engagement-ring-in-platinum-22086588_995766_ED_M.jpg?&op_usm=1.75,1.0,6.0&$cropN=0.1,0.1,0.8,0.8&defaultImage=NoImageAvailableInternal&",
          hearted: true
        }
      ]
    };
  }
};
</script>
