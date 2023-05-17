<script >
import VueDatePicker from '@vuepic/vue-datepicker';
import '@vuepic/vue-datepicker/dist/main.css'



// export default {
//   components: { VueDatePicker },
//   data() {
//     return {
//       date: null,
//     };
//   }
// }



export default {
  components: { VueDatePicker },
  data() {
    return {
      images: [
        'https://media.istockphoto.com/id/1035417946/photo/female-dentist-talking-to-her-patient-at-dentists-office.jpg?b=1&s=170667a&w=0&k=20&c=neY8fxhlFAQxrfb5EGdojadDla8K11wZMty72D9EY7I=',
        'https://media.istockphoto.com/id/1426680238/photo/smiling-woman-holding-an-invisible-teeth-aligner.jpg?b=1&s=170667a&w=0&k=20&c=5tQsjUD_ECHzVBLXfzC0ZnniXGwztpGUcczUZI0NSuE=',
        'https://media.istockphoto.com/id/1404168630/photo/senior-man-looking-the-teeth-in-mirror-at-dentist.jpg?b=1&s=170667a&w=0&k=20&c=vUq_GAZMbFpung85b2fAY9ovt0P2hhtSrlzP9_rv8qE=',
        
      ],
      currentIndex: 0,
      timer: null
    };
  },
  computed: {
    currentImage() {
      return this.images[this.currentIndex];
    }
  },
  mounted() {
    this.startTimer();
  },
  beforeDestroy() {
    this.stopTimer();
  },
  methods: {
    handleKeyPress(event) {
      if (event.keyCode === 37) {
        // Left arrow key pressed
        this.navigate('left');
      } else if (event.keyCode === 39) {
        // Right arrow key pressed
        this.navigate('right');
      }
    },
    navigate(direction) {
      if (direction === 'left') {
        this.currentIndex = (this.currentIndex - 1 + this.images.length) % this.images.length;
      } else if (direction === 'right') {
        this.currentIndex = (this.currentIndex + 1) % this.images.length;
      }
      this.resetTimer();
    },
    startTimer() {
      this.timer = setInterval(() => {
        this.navigate('right');
      }, 3000); // 3 seconds
    },
    stopTimer() {
      clearInterval(this.timer);
      this.timer = null;
    },
    resetTimer() {
      this.stopTimer();
      this.startTimer();
    }
  }
};


</script>

<template>
  <header>
        <button id="appointment" type="submit">SCHEDULE AN APPOINTMENT</button>
        <VueDatePicker placeholder = "Schedule a FREE first visit" v-model="date">Pick a Date</VueDatePicker>
        <nav class="navigation-bar"></nav>
            <div class="container">
            <img class="logo" src="https://media.istockphoto.com/id/1428043564/es/foto/icono-de-diente.jpg?s=612x612&w=0&k=20&c=Ku068NArjnoxQ43xjE3ESUIOAvOQCN_h8uWihplM4VM=" alt="Carl's Dental Clinic">
            <div class="navigation-pans">
                <ul>
                  <li>WHY CARL</li> 
                  <li>OUR SERVICES</li>
                  <li>THE TEAM</li>
                  <li>CONTACT US</li>
                </ul>
              </div>
            </div>
    </header>
    <div class="patient-img">
        <img src="https://media.istockphoto.com/id/1326436029/photo/happy-black-female-patient-looking-at-mirror-after-dental-treatment-in-clinic.jpg?b=1&s=170667a&w=0&k=20&c=7R1JQ3jtSdSSRSbfwWmSFlN09oen_Wthv4YGUXkORmc=" alt="Satisfied Patient">
    </div>
    <div>
        <p>HEAR FROM OUR PATIENTS</p>
    </div>
    <div class="card"></div>
    <div class="card"></div>
    <div class="card"></div>
    
    <div class="clinic-pic">
        <img src="" alt="Carl's Dental Clinic Madrid">
    </div>

    <div class="special-offers">
    </div>

  
  <div class="carousel" tabindex="0" @keydown="handleKeyPress">
    <div class="image-container">
      <img :src="currentImage" alt="Carousel Image">
    </div>
  </div>


  <footer class="footer">
  <div class="container">
    <div class="footer-social">
      <a href="#" class="social-icon">
        <img class="icon-size" src="https://www.svgrepo.com/show/419926/facebook-fb-social-icon.svg" alt="Facebook">
      </a>
      <a href="#" class="social-icon">
        <img class= "icon-size" src="" alt="Twitter">
      </a>
      <a href="#" class="social-icon">
        <img class="icon-size" src="https://www.svgrepo.com/show/353905/instagram-icon.svg" alt="Instagram">
      </a>
      <a href="#" class="social-icon">
        <img class="icon-size" src="" alt="LinkedIn">
      </a>
      <a href="#" class="social-icon">
        <img class="icon-size" src="" alt="YouTube">
      </a>
    </div>
    <div class="footer-contact">
      <p>Contact us: <a href="tel:+1234567890">(123) 456-7890</a></p>
      <p>Email: <a href="mailto:info@example.com">carldental@gmail.com</a></p>
    </div>
    <div class="footer-location">
      <p>123 Main Street, City, State, ZIP</p>
    </div>
  </div>
</footer>



</template>

<style scope>

* {
background-color: #E4C3AD;
}

#appointment {
position: absolute;
width: 248px;
height: 52px;
left: 1005px;
top: 20px;
border-radius: 11px;
background: #0D1F2D;
color: white;
line-height: 0,5px;
text-align: center;
}

.logo {
position: absolute;
width: 216px;
height: 194px;
left: 12px;
top: 20px;
}

.navigation-pans ul {
  list-style: none; 
  display: flex; 
  justify-content: space-between;
  align-items: center; 
  flex-direction: row;
 
}

.navigation-pans li {
  margin-right: 10px; 
  background-color: #546A7B;
}

.patient-img {
position: absolute;
width: 836px;
height: 331px;
left: 222px;
top: 205px;
}
.carousel-container {
  position: relative;
  width: 600px;
  height: 400px;
  overflow: hidden;
}

.carousel-images {
  position: absolute;
  display: flex;
  width: 300%;
  animation: slide 10s infinite;
}

.carousel-images img {
  width: 33.33%;
  height: 100%;
  object-fit: cover;
}

.carousel-controls {
  position: absolute;
  bottom: 20px;
  left: 50%;
  transform: translateX(-50%);
}

.prev-button,
.next-button {
  padding: 10px 20px;
  margin: 0 10px;
  border: none;
  background-color: #ccc;
  color: #fff;
  cursor: pointer;
}

.prev-button:hover,
.next-button:hover {
  background-color: #555;
}

.carousel {
  display: flex;
  align-items: center;
  justify-content: center;
}

.arrow {
  font-size: 24px;
  width: 40px;
  height: 40px;
  background-color: #ccc;
  border: none;
  border-radius: 50%;
  cursor: pointer;
}

.image-container {
  margin: 0 10px;
}

.image-container img {
  max-width: 100%;
  height: auto;
}

.footer {
  background-color: #f2f2f2;
  padding: 20px;
  text-align: center;
}

.footer-social {
  padding: 20px;
  font-size: 30px;
  width: 30px;
  text-align: center;
  text-decoration: none;
  margin: 5px 2px;
  border-radius: 50%;
  max-width: 10px;
  max-height: 10px;
}

.social-icon {
  display: inline-block;
  margin-right: 10px;
  padding: 20px;
  font-size: 30px;
  width: 30px;
  text-align: center;
  text-decoration: none;
  margin: 5px 2px;
  border-radius: 50%;
}

.footer-contact p,
.footer-location p {
  margin-bottom: 10px;
}

.footer-contact a {
  color: #000;
  text-decoration: none;
}

.footer-location {
  font-style: italic;
}

.icon-size {
  width: 50px;
  height: 50px;
  
}

</style>
