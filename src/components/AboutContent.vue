<template>
  <section class="py-5" style="background-color: #FEFAE0;">
    <div class="container">

      <!-- TITLE -->
      <div class="text-center mb-5">
        <h2 class="fw-bold" style="color:#0A400C; font-family:'Poppins';">
          About Our Workshop
        </h2>
        <p class="text-secondary" style="max-width:600px; margin:auto;">
          Trusted by car owners for over 10 years. We specialize in offering premium repairs,
          diagnostics, and maintenance services with modern tools and expert technicians.
        </p>
      </div>

      <div class="row align-items-center">

        <!-- LEFT IMAGE -->
        <div class="col-md-6 text-center mb-4">
          <img
            :src="shopImage"
            class="about-img"
            alt="Workshop"
          />
        </div>

        <!-- RIGHT CONTENT -->
        <div class="col-md-6">
          <h3 class="fw-semibold mb-3" style="font-family:'Poppins';">
            Professional Auto Care You Can Trust
          </h3>

          <p class="text-secondary mb-3">
            Our certified mechanics combine hands-on expertise with modern diagnostic tools
            to ensure your vehicle gets the best treatment. From engines to electrical systems,
            we handle it all with care and precision.
          </p>

          <ul class="list-unstyled">
            <li class="mb-2"><i class="bi bi-check-circle-fill text-success"></i> Engine Diagnostics & Repairs</li>
            <li class="mb-2"><i class="bi bi-check-circle-fill text-success"></i> Brake & Suspension Services</li>
            <li class="mb-2"><i class="bi bi-check-circle-fill text-success"></i> Full Vehicle Inspection</li>
            <li class="mb-2"><i class="bi bi-check-circle-fill text-success"></i> Car Body & Paint Work</li>
          </ul>

          <a
            href="/contact"
            class="btn btn-md mt-3"
            style="background-color:#0A400C; color:#FEFAE0;"
          >
            Contact Mechanic
          </a>
        </div>

      </div>
    </div>
  </section>
</template>

<script setup>
import shopImage from '../assets/engines.png' // change to your preferred image
</script>

<style scoped>
.about-img {
  width: 100%;
  max-width: 450px;
  border-radius: 12px;
  box-shadow: 0 4px 18px rgba(0,0,0,0.15);
  transition: transform 0.4s ease, box-shadow 0.4s ease;
}

.about-img:hover {
  transform: scale(1.03);
  box-shadow: 0 6px 24px rgba(0,0,0,0.20);
}
</style>
