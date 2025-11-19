<template>
  <div class="container py-5 position-relative">

    <!-- FULL PAGE LOADER -->
    <div v-if="loading" class="loading-overlay">
      <div class="spinner-border" role="status"></div>
    </div>

    <!-- ALERT -->
    <div v-if="alert.show" :class="['alert', alert.type]" role="alert">
      <h4 class="alert-heading">{{ alert.title }}</h4>
      <p>{{ alert.message }}</p>
    </div>

    <div class="row g-4">

      <!-- LEFT SIDE — FORM -->
      <div class="col-md-8">
        <div class="form-card p-4">

          <h3 class="mb-3" style="font-family: 'Poppins';">Book a Service Request</h3>

          <form @submit.prevent="submitRequest">
            
            <!-- Name -->
            <InputText
              v-model="form.name"
              placeholder="Full Name"
              class="mb-3 w-100 soft-input"
              required
            />

            <!-- Country -->
            <InputText
              v-model="form.country"
              placeholder="Country"
              class="mb-3 w-100 soft-input"
              required
            />

            <!-- State / Address -->
            <InputText
              v-model="form.address"
              placeholder="State / Address"
              class="mb-3 w-100 soft-input"
              required
            />
            
            <!-- Email -->
            <InputText
              v-model="form.email"
              placeholder="Email"
              class="mb-3 w-100 soft-input"
              required
            />

            <!-- Car Brand -->
            <select v-model="form.carBrand" class="form-select mb-3 soft-input" required>
              <option disabled value="">Select Car Brand</option>
              <option v-for="brand in carBrands" :key="brand">{{ brand }}</option>
            </select>

            <!-- Service Type -->
            <select v-model="form.serviceType" class="form-select mb-3 soft-input" required>
              <option disabled value="">Select Service Type</option>
              <option v-for="service in services" :key="service">{{ service }}</option>
            </select>

            <!-- Message / Description -->
            <textarea
              v-model="form.message"
              class="form-control mb-3 soft-input"
              rows="4"
              placeholder="Describe the issue with your car..."
              required
            ></textarea>

            <button class="btn w-100 submit-btn" :disabled="loading">
              Submit Request
            </button>

          </form>
        </div>
      </div>

      <!-- RIGHT SIDE — INFO CARD -->
      <div class="col-md-4">
        <div class="info-card p-4">
          <h4 class="fw-bold mb-3" style="font-family:'Poppins';">What You Should Know</h4>

          <p><strong>Response Time:</strong> We respond within 30–60 minutes.</p>
          <p><strong>Working Days:</strong> Monday – Saturday (8AM – 6PM)</p>
          <p><strong>Location:</strong> 25A Mechanic Village, Lagos, Nigeria</p>
          <p><strong>Phone:</strong> +234 808 123 4567</p>
          <p><strong>Email:</strong> support@nuimmechanics.com</p>

          <hr />

          <p class="text-secondary">
            After submitting your request, our team will contact you through call, SMS, or WhatsApp.
          </p>
        </div>
      </div>

    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
import InputText from "primevue/inputtext";
import { supabase } from "../supabase";

const loading = ref(false);

const alert = ref({
  show: false,
  type: "",   // alert-success or alert-danger
  title: "",
  message: "",
});

// FORM DATA
const form = ref({
  name: "",
  country: "",
  address: "",
  email: "",
  carBrand: "",
  serviceType: "",
  message: "",
});

// DROPDOWN OPTIONS
const carBrands = [
  "Toyota", "Honda", "Lexus", "BMW", "Mercedes", "Peugeot",
  "Mazda", "Kia", "Hyundai", "Nissan", "Ford", "Volkswagen"
];

const services = [
  "Car Service", "Diagnosis", "Body Work", "Steering Alignment",
  "Gear Box", "Interior", "Tyres", "Engine Fault", "Brakes",
  "Clutch", "Lights", "Electrical Issues", "Others"
];

// SUBMIT FORM
async function submitRequest() {
  loading.value = true;
  alert.value.show = false;

  try {
    const { data, error } = await supabase
      .from("request")
      .insert([{ ...form.value, createdAt: new Date() }]);

    if (error) throw error;

    alert.value = {
      show: true,
      type: "alert-success",
      title: "Request Submitted!",
      message: "Your service request has been successfully submitted.",
    };

    Object.keys(form.value).forEach(k => form.value[k] = "");
  } catch (error) {
    alert.value = {
      show: true,
      type: "alert-danger",
      title: "Submission Failed",
      message: error.message,
    };
  }

  loading.value = false;
}
</script>

<style scoped>
/* REMOVE CARD SHADOWS + BORDERS */
.form-card, .info-card {
  border-radius: 12px;
  background-color: #FEFAE0;
  border: none !important;
  box-shadow: none !important;
}

/* SOFT INPUT BACKGROUND */
.soft-input {
  background-color: #f5f2d7 !important;
  border: 1px solid #c9c7b0 !important;
  border-radius: 6px !important;
}

.soft-input:focus {
  border-color: #0A400C !important;
  box-shadow: 0 0 6px rgba(10, 64, 12, 0.4) !important;
}

/* BUTTON */
.submit-btn {
  background-color:#0A400C;
  color:#FEFAE0;
}

/* FULL PAGE LOADING OVERLAY */
.loading-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(10, 64, 12, 0.2);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 2000;
}

.spinner-border {
  width: 3rem;
  height: 3rem;
  border-width: 5px;
  color: #0A400C;
}

/* ALERT STYLING */
.alert {
  border-radius: 10px;
  margin-bottom: 20px;
}
</style>
