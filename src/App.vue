<script setup>
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <header>
        <button id="appointment">SCHEDULE AN APPOINTMENT</button>
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
    <footer>
        <p>Address: </p>
        <div class="social-media"></div>
    </footer>
  <HelloWorld msg="Vite + Vue" />
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

.navigation-pans {
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
</style>
