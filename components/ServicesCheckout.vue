<template>
  <section class="contact-area">
    <div class="container">
      <div class="row">
        <div class="col-lg-12">
          <div
            class="contact-colunm"
            data-aos="fade-up"
            data-aos-duration="1000"
          >
          <div class="contact-map-area">
            <h2 class="text-dark">({{  service_name }}) SERVICE PURCHASE</h2>
            <div class="separator-line">
                        <img src="/images/shape/line2.png" alt="shape" />
                        <img src="/images/shape/line1.png" alt="shape" />
                      </div>
            <img src="/images/shape/checkout.png" alt="Purchase Image">
          
                        </div>
            <div class="contact-form">
              <form @submit.prevent="submitData" class="contact-form-wrapper">
                <div class="row">
                  <div class="col-lg-12">
                    <div class="section-title">
                      <div class="subtitle-content">
                        <img src="/images/shape/line-s4.png" alt="shape" />
                        <h5 class="text-light">Purchase this service</h5>
                      </div>


                      <div class="row">
                        <div class="col-md-12">
                  <h4 class=" text-light">
                        Service Name : <span>{{  service_name }} </span>
                      </h4></div>
                        <div class="col-md-12">
                  <h2 class="title text-light">
                        Total due : <span>{{  total_due }} USD</span>
                      </h2></div>
                            <div class="col-md-6">
                                <div class="form-group">
                                
                                </div>
                            </div>
                            <div class="col-md-6">
                                <div class="form-group">
                                    <input id="qty"
                            class="form-control" required
                            type="number"
                            min="1"
                            name="con_quantity"
                            v-model="form.quantity"
                            
                                @change="changeQty" hidden
                          /></div>
                            </div>
                        </div>
                      <div class="separator-line">
                        <img src="/images/shape/line-s4.png" alt="shape" />
                        <img src="/images/shape/line-s4.png" alt="shape" />
                      </div>
                    </div>
                  </div>
                </div>
                <div class="row">
                  <div class="col-md-6">
                    <div class="form-group">
                      <input
                        class="form-control" required
                        type="text"
                        name="con_firstname"
                        v-model="form.firstname"
                        placeholder="Name"
                      />
                    </div>
                  </div>
                  <div class="col-md-6">
                    <div class="form-group">
                      <input
                        class="form-control" required
                        type="text"
                        name="con_lastname"
                        v-model="form.lastname"
                        placeholder="Lastname"
                      />
                    </div>
                  </div>

                  <div class="col-md-12">
                    <div class="form-group">
                      <input
                        class="form-control" required
                        type="email"
                        name="con_email"
                        v-model="form.email"
                        placeholder="Email"
                      />
                    </div>
                  </div>

                  <div class="col-md-12">
                    <div class="form-group">
                      <select
                        v-model="selectedCountry"
                        @change="changeCountry"
                        class="form-control" required
                        id="country"
                      >
                        <option style="color: black" value="0" selected>
                          Select your Country
                        </option>
                        <option
                          style="color: black"
                          v-for="(country, index) in countries"
                          :key="index"
                          :value="country.code"
                        >
                          {{ country.name }}
                        </option>
                      </select>
                    </div>
                  </div>
                  <div class="col-md-12">
                    <div class="form-group">
                      <input
                        class="form-control" required
                        type="text"
                        name="con_city"
                        v-model="form.city"
                        placeholder="city"
                      />
                    </div>
                  </div>
                  <div class="col-md-12">
                    <div class="form-group">
                      <input
                        class="form-control" required
                        type="text"
                        name="con_address"
                        v-model="form.address"
                        placeholder="address"
                      />
                    </div>
                  </div>
                  <div class="col-md-12">
                    <div class="form-group">
                      <input
                        class="form-control" required
                        type="text"
                        name="con_shippingAddress"
                        v-model="form.shippingAddress"
                        placeholder="shipping address"
                      />
                    </div>
                  </div>
                  <div class="col-md-12">
                    <div class="form-group">
                      <input
                        class="form-control" required
                        type="text"
                        name="con_zip"
                        v-model="form.zip"
                        placeholder="zip"
                      />
                    </div>
                  </div>
                  <div class="col-md-12">
                    <div class="form-group">
                      <input
                        class="form-control" required
                        type="text"
                        name="con_save_info"
                        v-model="form.save_info"
                        placeholder="Save info"
                      />
                    </div>
                  </div>
                  <div class="col-md-12">
                    <div class="form-group">
                      <input
                        class="form-control" required
                        type="text"
                        name="con_cc_name"
                        v-model="form.cc_name"
                        placeholder="Name on card"
                      />
                    </div>
                  </div>
                  <div class="col-md-12">
                    <div class="form-group">
                      <input
                        class="form-control" required
                        type="text"
                        name="con_cc_number"
                        v-model="form.cc_number"
                        placeholder="Card Number"
                      />
                    </div>
                  </div>

                  <div class="col-md-4">
                    <div class="form-group">
                      <input
                        class="form-control" required
                        type="number"
                        name="con_cc_expiration_month" max="12" min="1" maxlength="2" 
                        v-model="form.cc_expiration_month"
                        placeholder="MM"
                      />
                    </div>
                  </div>

                  <div class="col-md-4">
                    <div class="form-group">
                      <input
                        class="form-control" required
                        type="number"
                        name="con_cc_expiration_year"
                        maxlength="2"
                        v-model="form.cc_expiration_year"
                        placeholder="YY"
                      />
                    </div>
                  </div>

                  <div class="col-md-4">
                    <div class="form-group">
                      <input
                        class="form-control" required
                        type="number"
                        name="con_cc_ccv"
                        maxlength="3"
                        v-model="form.cc_ccv"
                        placeholder="ccv"
                      />
                    </div>
                  </div>
                  
                  <div class="col-md-12">
                    <div class="form-group mb-0">
                      <button class="btn btn-theme" type="submit">
                        Checkout Now <i class="icofont-long-arrow-right"></i>
                      </button>
                    </div>
                  </div>
                </div>
              </form>
            </div>
          </div>
        </div>
      </div>
      <div class="alert success-a" v-if="showAlert_s">
        Your order of {{ service_name }} was successfully placed <br>An Email has been sent to the email address provided in the form
      </div>

      <div class="alert danger-a" v-if="showAlert_d">
        Error: make sure you have internet
      </div>
    </div>
  </section>
</template>

<script>

import dataT from "~/data/data.json";

function showAlert() {
  setTimeout(() => {
    const elements = document.getElementsByClassName("alert");
    for (let i = 0; i < elements.length; i++) {
      elements[i].style.display = "none";
    }
  }, 3000);
}
async function postData(url, data) {
  try {
    const response = await fetch(url, {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify(data),
    });

    if (!response.ok) {
      throw new Error("Network response was not ok");
      alert("Erreur de connexion");
    }

    const result = await response.json();
    return result;
  } catch (error) {
    console.error("Error:", error);
    throw error;
  }
}

export default {
  data() {
    return {
      form: {
        firstname: "",
        lastname: "",
        email: "",
        country: "",
        city: "",
        address: "",
        shippingAddress: "",
        zip: "",
        save_info: "",
        cc_expiration_month: "",
        cc_expiration_year: "",
        cc_number: "",
        cc_ccv: "",
        cc_name: "",
        quantity: "",
        total: "",
        service_id: "",
      },
      showAlert_s: false, // Initially, hide the alert
      showAlert_d: false,
      alertType: "", // Type of the alert ('success' or 'error')
      alertMessage: "",
      // Message to display in the alert
      selectedCountry: "Benin",
      service_name : "loading",
      service_price : "loading",
      total_due : "",
      countries: [],
    };
  },

  methods: {

    async  submitData() {
          const apiLink = dataT.apiUrl.service_checkout_api_link;
          const url = apiLink;
          const data = {
    

        "firstname": this.form.firstname,
        "lastname": this.form.lastname,
        "email": this.form.email,
        "country": this.form.country,
        "city": this.form.city,
        "address": this.form.address,
        "shippingAddress": this.form.shippingAddress,
        "zip": this.form.zip,
        "save_info": this.form.save_info,
        "cc-expiration-month": this.form.cc_expiration_month,
        "cc-expiration-year": this.form.cc_expiration_year,
        "cc-number": this.form.cc_number,
        "cc-ccv": this.form.cc_ccv,
        "cc-name": this.form.cc_name,
        "quantity": this.form.quantity,
        "total": this.total_due,
        "service_id": this.$route.query.service_id,
          
  };

  try {
    const response = await postData(url, data);
    console.log('Response:', response);
    // alert("Votre message a été envoyé avec succès")

    this.showAlert_s = true;
    showAlert()
    // this.showAlert = true;
    //     this.alertType = 'success';
    //     this.alertMessage = 'Message envoyé';
    // // Handle the response data here
  } catch (error) {
    console.error('Error:', error);
    this.showAlert_d = true;
    showAlert()
    // alert("Erreur: une erreur s'est produite\n; vérifiez votre connexion")
    // this.showAlert = true;
    //     this.alertType = 'error';

    //     this.alertMessage = 'vérifiez votre connexion';
    // // Handle errors here
  }
},
    changeCountry() {
      // Handle country change
      
      this.form.country = this.selectedCountry;
    },
    getTot(){
        // const price = 10
        this.form.quantity = "1"
        this.selectedCountry = "USA";
      this.total_due =  this.$route.query.service_price ?? "00.00"
      this.service_name = this.$route.query.service_name ?? "loading..."
      this.service_price = this.$route.query.service_price ?? "loading..."
    },
    changeQty() {
      // Handle country change
      const price = this.service_price
      this.total_due =    parseInt(this.form.quantity) * price+".00";
    },
    async cData() {
      // Load countries from countries.json
      try {
        const countries = await import("~/data/countries.json");
        this.countries = countries.default; // Assuming the countries are the default export
        // console.log(this.countries);
      } catch (error) {
        console.error("Error loading countries:", error);
      }
    },
  },
  mounted() {
    this.cData();
    this.getTot();
  },
};
</script>

<style lang="scss" scoped></style>
