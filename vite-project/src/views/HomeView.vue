<template>
  <div class="container">
    <div class="header">
      <h1>Sneaker head</h1>
    </div>

    <div class="card" v-for="shoe in inventory" :key="shoe.name">
      <h2>{{ shoe.name }}</h2>
      <h3>{{ shoe.cost }}</h3>
      <h3>{{ shoe.category }}</h3>
      <img :src="shoe.img" alt="">
      <button class="buttons" @click="add(shoe)">Add to Cart</button>
    </div>

    <div class="cart">
      <div class="total">
        <h2>Total: {{ calculateTotal().toFixed(2) }}</h2>
      </div>
      <div class="cartItems" v-for="item in cart" :key="item.name">
        <h3>{{ item.name }}</h3>
        <h3>{{ item.cost }}</h3>
        <h3>{{ item.category }}</h3>
        <img :src="item.img" alt="">
        <button class="buttons" @click="remove(item)">Remove From Cart</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      inventory: [
      {
          name: "Jordan 4 Off-White Sail",
          cost: 1048,
          category: "Jordan",
          img: "vite-project/public/pictures/jordan.jpg.avif",
        },
        {
          name: "Nike SB Freddy Krueger Dunk",
          cost: 89500,
          category: "Nike",
          img: "vite-project/public/pictures/Nike-Dunk-SB-Low-Freddy-Krueger.jpg.avif",
        },
        {
          name: "Jordan 1 Retro High Dior",
          cost: 12463,
          category: "Jordan",
          img: "vite-project/public/pictures/Air-Jordan-1-Retro-High-Dior-Product.jpg.avif",
        },
        {
          name: "Nike Air Force 1 Low Louis Vuitton",
          cost: 400000,
          category: "Nike",
          img: "vite-project/public/pictures/Nike-Air-Force-1-Low-Louis-Vuitton-Monogram-Brown-Damier-Azur-Product_V2.jpg.avif",
        },
        {
          name: "Chanel Low Top Trainer",
          cost: 3575,
          category: "designer",
          img: "",
        },
        {
          name: "Louis Vuitton LV Skate Sneaker",
          cost: 3100,
          category: "designer",
          img: "vite-project/public/pictures/Louis-Vuitton-LV-Skate-Sneaker-Black-Black-White-Product.jpg.avif",
        },
        {
          name: "Jordan 1 Retro Chicago (1994)",
          cost: 5002,
          category: "Jordan",
          img: "",
        },
        {
          name: "Dior B23 High",
          cost: 1239,
          category: "designer",
          img: "vite-project/public/pictures/Dior-B23-High-Multicolor-Obliquey.jpg.avif",
        },
        { name: "A Bathing Ape Bape Sta",
          cost: 792,
          category: "designer",
          img: "vite-project/public/pictures/A-Bathing-Ape-Bape-Sta-Bape-Black-White-Silver.jpg.avif",
        },
        {name: "Jordan 4 Retro Eminem",
          cost: 26000,
          category: "Jordan",
          img: "",

        },
        {name: "Jordan 4 Retro Travis Scott Cactus Jack",
          cost: 30000,
          category: "designer",
          img: "",

        },
        {
          name: "Louis Vuitton Nike Air Force 1 Mid",
          cost: 34995,
          category: "designer",
          img: "vite-project/public/pictures/Louis-Vuitton-Nike-Air-Force-1-Mid-By-Virgil-Abloh-Graffiti-Product.jpg.avif",

        },
        { name: "Golden Goose Sky-Star White Black Ice",
          cost: 778,
          category: "designer",
          img: "ggsk",
},
      ],
      cart: [],
    };
  },
  methods: {
    add(item) {
      this.cart.push(item);
    },
    remove(item) {
      const index = this.cart.indexOf(item);
      if (index !== -1) {
        this.cart.splice(index, 1);
      }
    },
    calculateTotal() {
      let total = 0;
      for (const item of this.cart) {
        total += item.cost;
      }
      return total;
    },
  },
};
</script>

<style scoped>
.container {
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
}

.header {
  text-align: center;
  margin-bottom: 20px;
}

.card {
  border: 1px solid #ccc;
  padding: 10px;
  margin-bottom: 10px;
}

.card img {
  max-width: 100%;
  height: auto;
  margin-bottom: 10px;
}

.cart {
  margin-top: 20px;
  border-top: 1px solid #ccc;
  padding-top: 20px;
}

.total {
  text-align: right;
  margin-bottom: 10px;
}

.buttons {
  background-color: #007bff;
  color: #fff;
  border: none;
  padding: 5px 10px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.buttons:hover {
  background-color: #0056b3;
}
</style>
