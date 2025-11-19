<template>
  <div class="row m-4 g-4">

    <div
      class="col-12 col-sm-6 col-md-4 col-lg-3"
      v-for="(card, index) in cards"
      :key="index"
    >
      <div class="card custom-card h-100">

        <!-- IMAGE HEADER -->
        <img :src="card.image" class="card-img-top card-image" alt="Card image">

        <div class="card-body d-flex flex-column">
          <h5 class="card-title" style="font-family: Poppins; font-size: 15px; font-weight: 600;">{{ card.title }}</h5>
          <p class="card-text flex-grow-1">{{ card.text }}</p>
          <a href="/contact" class="btn mt-auto" style="background-color: #0A400C; color: #FEFAE0;">Contact us</a>
        </div>

      </div>
    </div>

  </div>
</template>

<script setup>
const cards = [
  {
    title: "V6 Engines",
    text: "Top-tier industrial engines with the finest durability.",
    image: "/src/assets/engines.png"
  },
  {
    title: "Turbo Engines",
    text: "Luxury designs for modern beauty spaces.",
    image: "/src/assets/mariaEngine1.png"
  },
  {
    title: "Generator Engines",
    text: "Elegant interior setups for warm and cozy homes.",
    image: "/src/assets/generators.png"
  },
  {
    title: "BMW Engines",
    text: "Custom wooden designs crafted for perfection.",
    image: "/src/assets/bmw.png"
  }
];
</script>

<style scoped>
/* Standard card height */
.custom-card {
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  border-radius: 12px;
  overflow: hidden;
  background-color: #FEFAE0;
}

/* Hover animation */
.custom-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 10px 22px rgba(0, 0, 0, 0.15);
}

/* Image header */
.card-image {
  height: 180px;
  object-fit: cover;
  width: 100%;
  display: block;
}
</style>
