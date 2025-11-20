<template>
  <div class="border border-1" style="background-color: #FEFAE0;">
    <div class="row m-4 align-items-center" style="min-height: 250px;">

      <!-- LEFT SECTION (Left-aligned now) -->
      <div class="col-sm-6 mb-3 mb-sm-0">
        <div class="card border-0" style="background-color: #FEFAE0;">
          <div class="card-body text-start">

            <h5 class="card-title"
                style="font-family: 'Poppins'; font-size: x-large; font-weight: 500;">
              Automobile works
            </h5>

            <p class="card-text"
               style="font-family: 'Nunito'; font-size: medium;">
              We repair all types of automobiles, your satisfaction is our goal. Spend less to fix, diagonise and maintain your vehichle.
            </p>

            <RouterLink class="btn btn-md" to="/contact" style="background-color: #0A400C; color: #FEFAE0;">Book an appointment</RouterLink>
          </div>
        </div>
      </div>

      <!-- RIGHT SECTION (Centered image) -->
      <div class="col-sm-6 text-center">
        <div class="card border-0" style="background-color: #FEFAE0;">
          <div class="card-body">

            <img src="/src/assets/engines.png"
                 alt="salon picture"
                 class="soft-fade"
                 style="width:260px; height:260px;">
                 
          </div>
        </div>
      </div>

    </div>
  </div>
</template>
