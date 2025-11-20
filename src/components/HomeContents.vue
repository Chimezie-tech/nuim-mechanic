<template>
  <div class="container px-4 py-5">
    <h2 class="pb-2 border-bottom">Services We Offer</h2>

    <div class="row row-cols-1 row-cols-md-2 align-items-md-center g-5 py-5">
      
      <!-- LEFT CONTENT -->
      <div class="col d-flex flex-column align-items-start gap-2">
        <h2 class="fw-bold text-body-emphasis">
          Left-aligned title explaining these awesome features
        </h2>
        <p class="text-body-secondary">
          Paragraph of text beneath the heading to explain the heading. We'll add
          onto it with another sentence and probably keep going until we run out of words.
        </p>
        <RouterLink class="btn btn-md" to="/contact" style="background-color: #0A400C; color: #FEFAE0;">Contact mechanic</RouterLink>
      </div>

      <!-- RIGHT FEATURES GRID -->
      <div class="col">
        <div class="row row-cols-1 row-cols-sm-2 g-4">

          <!-- FEATURE BOX 1 -->
          <div class="col d-flex flex-column gap-2 text-start">
            <div class="feature-icon rounded-5 d-flex align-items-center justify-content-center">
              <img :src="toolsImg" class="icon-img" alt="engine">
            </div>
            <h4 class="fw-semibold mb-0 text-body-emphasis">Engine Repairs</h4>
            <p class="text-body-secondary">Fast and reliable engine diagnostics and repairs.</p>
          </div>

          <!-- FEATURE BOX 2 -->
          <div class="col d-flex flex-column gap-2 text-start">
            <div class="feature-icon rounded-5 d-flex align-items-center justify-content-center">
              <img :src="toolsImg" class="icon-img" alt="service">
            </div>
            <h4 class="fw-semibold mb-0 text-body-emphasis">Body Work</h4>
            <p class="text-body-secondary">High-quality finishing and professional body restoration.</p>
          </div>

          <!-- FEATURE BOX 3 -->
          <div class="col d-flex flex-column gap-2 text-start">
            <div class="feature-icon rounded-5 d-flex align-items-center justify-content-center">
              <img :src="toolsImg" class="icon-img" alt="service">
            </div>
            <h4 class="fw-semibold mb-0 text-body-emphasis">Gearbox Service</h4>
            <p class="text-body-secondary">Complete gearbox repair, tuning and maintenance.</p>
          </div>

          <!-- FEATURE BOX 4 -->
          <div class="col d-flex flex-column gap-2 text-start">
            <div class="feature-icon rounded-5 d-flex align-items-center justify-content-center">
              <img :src="toolsImg" class="icon-img" alt="service">
            </div>
            <h4 class="fw-semibold mb-0 text-body-emphasis">Performance Boost</h4>
            <p class="text-body-secondary">Increase speed and performance with expert tuning.</p>
          </div>

        </div>
      </div>

    </div>
  </div>
</template>

<script setup>
import engineImg from '../assets/engines.png'
import salonImg from '../assets/salon.png'
import toolsImg from '../assets/tools.png'
</script>

<style scoped>
.feature-icon {
  width: 50px;
  height: 50px;
  background-color: #0A400C;
  color: #fff;
}

.icon-img {
  width: 45px;
  height: 45px;
  object-fit: contain;
  filter: brightness(95%);
}

/* Smooth hover animation */
.feature-icon:hover,
.icon-img:hover {
  transform: scale(1.08);
  transition: 0.3s ease;
}
</style>
