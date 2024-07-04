<template>
  <div class="container-fluid">
    <div class="row">
        <div class="reachMe">

            <div class="contact-content">
             <img src="https://leahbasson.github.io/MyImages/images/contactImage.jpg" alt="leahContact" loading="eager">
             <div class="mt-2">
              <a class="lnk text-white" href="mailto:your-email@example.com" alt="outlook icon" target="_blank"><i class="bi bi-envelope"></i></a>
             <a class="lnk text-white" href="https://www.linkedin.com/in/leah-basson-23a4192a0" alt="linkedin icon" target="_blank"><i class="bi bi-linkedin"></i></a>
             <a class="lnk text-white" href="https://github.com/LeahBasson" target="_blank"><i class="bi bi-github"></i></a>
             </div>
             <div class="contactP">
              <p>South Africa , Cape Town</p>
              <p>Address: Ottery , 7800</p>
              <p>Phone number: +27 66 243 1477</p>
              <p>Email: leahbasson57@gmail.com</p>
             </div>
             
            </div>

            <div class="formsDiv">
              <h2 class="display-3 text-white fadeInUp secHeading">Reach Me</h2>
              <form id="contactForm" action="https://formspree.io/f/mjvqdzra" method="POST" >
                <div class="row mb-5">
                    <div class="col">
                        <div class="form-group">
                            <!-- Name input-->
                            <input class="form-control" id="name" type="text" name="Name" placeholder="Your Name *" required />
                        </div>
                        <div class="form-group">
                            <!-- Email address input-->
                            <input class="form-control" id="email" type="email" name="Email" placeholder="Your Email *" required />
                        </div>
                        <div class="form-group mb-md-0">
                            <!-- Phone number input-->
                            <input class="form-control" id="phone" type="tel" name="cell" placeholder="Your Phone *" required />
                        </div>
                        <div class="form-group form-group-textarea mb-md-0">
                          <!-- Message input-->
                          <textarea class="form-control mb-2" id="message" name="Message" placeholder="Your Message *" required></textarea>
                      </div>
                    </div>
        
                </div>
              
                <!-- Submit Button-->
      <div class="text-center mb-2"><button class="button1" id="submitButton" type="submit">Send Message</button></div>
            </form>
            </div>

        </div>
        

    </div>
  </div>
</template>

<script>

</script>

<style>

</style>