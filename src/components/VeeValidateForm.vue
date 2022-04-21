<template>
  <div class="">
    <h1 style="text-align: center">VeeValidate Form</h1>
    <ValidationObserver v-slot="{ handleSubmit }">
      <form @submit.prevent="handleSubmit(onSubmit)">
        <ValidationProvider name="Name" rules="required" v-slot="{ errors }">
          <div class="form-group">
            <label>Name</label>
            <input type="text" class="form-control" v-model="formData.name" />
            <span class="error">{{ errors[0] }}</span>
          </div>
        </ValidationProvider>

        <ValidationProvider
          name="E-mail"
          rules="required|email"
          v-slot="{ errors }"
        >
          <div class="form-group">
            <label>Email</label>
            <input type="email" class="form-control" v-model="formData.email" />
            <span class="error">{{ errors[0] }}</span>
          </div>
        </ValidationProvider>
        <ValidationProvider
          name="Phone"
          rules="required|integer"
          v-slot="{ errors }"
        >
          <div class="form-group">
            <label>Phone</label>
            <input type="text" class="form-control" v-model="formData.phone" />
            <span class="error">{{ errors[0] }}</span>
          </div>
        </ValidationProvider>

        <ValidationProvider
          name="Password"
          rules="required"
          v-slot="{ errors }"
        >
          <div class="form-group">
            <label>Password</label>
            <input
              type="password"
              class="form-control"
              v-model="formData.password"
            />
            <span class="error">{{ errors[0] }}</span>
          </div>
        </ValidationProvider>

        <ValidationProvider name="Gender" rules="required" v-slot="{ errors }">
          <div class="form-group">
            <label>Gender</label>
            <select v-model="formData.gender" class="form-control">
              <option value="male">Male</option>
              <option value="female">Female</option>
              <option value="other">Other</option>
            </select>
            <span class="error">{{ errors[0] }}</span>
          </div>
        </ValidationProvider>

        <ValidationProvider
          name="Accept Terms"
          rules="required"
          v-slot="{ errors }"
        >
          <div class="form-check">
            <input
              type="checkbox"
              class="form-check-input"
              v-model="formData.acceptTerms"
            />
            <label class="form-check-label">AcceptTerms</label>
          </div>
          <span class="error">{{ errors[0] }}</span>
        </ValidationProvider>

        <input type="submit" class="btn btn-primary mt-3" tect="Submit" />
      </form>
    </ValidationObserver>
  </div>
</template>

<script>
export default {
  // name: "VeeValidateForm",
  data: () => ({
    formData: {
      name: "",
      email: "",
      phone: "",
      password: "",
      gender: "",
      acceptTerms: null,
    },
  }),

  methods: {
    onSubmit() {
      console.log(this.formData);
    },
  },
};
</script>

<style scoped>
.error {
  color: red;
  margin-left: 40%;
}
@import url("https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js");
</style>
