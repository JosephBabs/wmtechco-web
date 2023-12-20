<template>
    <section class="contact-area">
        <div class="contact-info-light" data-aos="fade-up" data-aos-duration="1000">
            <div class="contact-info-content">
                <div class="contact-info-item">
                    <div class="icon">
                        <img class="icon-img" src="/images/icons/c1.png" alt="Icon">
                    </div>
                    <div class="content">
                        <h4>Call Us.</h4>
                        <img class="line-icon" src="/images/shape/line-s1.png" alt="Icon">
                        <a href="tel://+1(317)603-4493">+1 (317) 603 4493</a>
                        <a href="tel://"></a>
                    </div>
                </div>
                <div class="contact-info-item">
                    <div class="icon">
                        <img class="icon-img" src="/images/icons/c2.png" alt="Icon">
                    </div>
                    <div class="content">
                        <h4>Email.</h4>
                        <img class="line-icon" src="/images/shape/line-s1.png" alt="Icon">
                        <a href="mailto://support@wmtecho.com">support@wmtecho.com</a>
                        <a href="mailto://contact@wmtecho.com">contact@wmtecho.com</a>
                    </div>
                </div>
                <div class="contact-info-item">
                    <div class="icon">
                        <img class="icon-img" src="/images/icons/c3.png" alt="Icon">
                    </div>
                    <div class="content">
                        <h4>Location.</h4>
                        <img class="line-icon" src="/images/shape/line-s1.png" alt="Icon">
                        <p>INDIANAPOLIS <br>INDIANA, USA</p>
                    </div>
                </div>
            </div>
        </div>
        <div class="container">
            <div class="row">
                <div class="col-lg-12">
                    <div class="contact-colunm" data-aos="fade-up" data-aos-duration="1000">
                        <div class="contact-map-area">
                            <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3151.8402891185374!2d144.95373631590425!3d-37.81720974201477!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x6ad65d4c2b349649%3A0xb6899234e561db11!2sEnvato!5e0!3m2!1sen!2ssg!4v1607294780661!5m2!1sen!2ssg"></iframe>
                        </div>
                        <div class="contact-form">
                            <form @submit.prevent="submitData" class="contact-form-wrapper">
                                <div class="row">
                                    <div class="col-lg-12">
                                        <div class="section-title">
                                            <div class="subtitle-content">
                                                <img src="/images/shape/line-s4.png" alt="shape">
                                                <h5 class="text-light">Contact Us</h5>
                                            </div>
                                            <h2 class="title text-light">Get In <span>Touch.</span></h2>
                                            <div class="separator-line">
                                                <img src="/images/shape/line-s4.png" alt="shape">
                                                <img src="/images/shape/line-s4.png" alt="shape">
                                            </div>
                                        </div>
                                    </div>
                                </div>
                                <div class="row">
                                    <div class="col-md-12">
                                        <div class="form-group">
                                            <input class="form-control" type="text" name="con_name" v-model="form.name" placeholder="Name">
                                        </div>
                                    </div>
                                    <div class="col-md-12">
                                        <div class="form-group">
                                            <input class="form-control" type="email" name="con_email" v-model="form.email" placeholder="Email">
                                        </div>
                                    </div>
                                    <div class="col-md-12">
                                        <div class="form-group">
                                            <input class="form-control" type="text" name="con_phone" v-model="form.phoneNumber" placeholder="Phone">
                                        </div>
                                    </div>
                                    <div class="col-md-12">
                                        <div class="form-group mb-0">
                                            <textarea name="con_message" v-model="form.message" placeholder="Message"></textarea>
                                        </div>
                                    </div>
                                    <div class="col-md-12">
                                        <div class="form-group mb-0">
                                            <button class="btn btn-theme" type="submit">Submit Now <i class="icofont-long-arrow-right"></i></button>
                                        </div>
                                    </div>
                                </div>
                            </form>
                        </div>
                    </div>
                </div>
            </div>
            <div class="alert success-a" v-if="showAlert_s">
       Message sent successfully</div>

       <div class="alert danger-a" v-if="showAlert_d">
       Error: make sure you have internet</div>
        </div>
    </section>
</template>


<script>

import dataT from "~/data/data.json";


function showAlert(){
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
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
      },
      body: JSON.stringify(data),
    });

    if (!response.ok) {
      throw new Error('Network response was not ok');
      alert("Erreur de connexion")
    }

    const result = await response.json();
    return result;
  } catch (error) {
    console.error('Error:', error);
    throw error;
  }
};

export default{
  
  data() {
    return {
      form: {
          
          name: "", 
          email: "",
          phoneNumber: "",
          message: "",
        },
        showAlert_s: false, // Initially, hide the alert
      showAlert_d: false, 
        alertType: '',    // Type of the alert ('success' or 'error')
      alertMessage: '', // Message to display in the alert
    
    }
  },
  name: 'ContactForm',

  methods: {
    
      
      async  submitData() {
          const apiLink = dataT.apiUrl.contact_post_api_link;
          const url = apiLink;
          const data = {
    

          name: this.form.name, 
          email: this.form.email,
          phoneNumber: this.form.phoneNumber,
          message: this.form.message,
          
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

  }
}
</script>



<style scope>

/* The alert message box */
.danger-a{
  background-color: #94100B;
  bottom: 10%;
}
.success-a{
  background-color: #0B9438;
  bottom: 10%;
}

.alert {
  padding: 20px;
  color: white;
  position: fixed;
  z-index: 9999;
  margin-bottom: 15px;
  margin: 10px;
  display: inline-flex;
  flex-direction: column;
  align-items: last baseline;
  justify-self: center;
}

/* The close button */
.closebtn {
  margin-left: 15px;
  color: white;
  font-weight: bold;
  float: right;
  font-size: 22px;
  line-height: 20px;
  cursor: pointer;
  transition: 0.3s;
}

/* When moving the mouse over the close button */
.closebtn:hover {
  color: black;
}


</style>
