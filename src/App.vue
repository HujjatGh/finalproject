<script setup>
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <header>
        <nav class="navigation-bar"></nav>
            <div class="container">
            <a class="logo" href="/" alt="Carl's Dental Clinic"></a>
            <div class="navigation-pans">
                <ul>
                  <li class="nav-item">
                    <a class="nav-link" href="/">WHY CARL</a>
                  </li>
                  <li class="nav-item">
                    <a class="nav-link" href="/">OUR SERVICES</a>
                  </li>
                  <li class="nav-item">
                    <a class="nav-link" href="/">THE TEAM</a> 
                  </li>
                    <li class="nav-item">
                    <a class="nav-link" href="/">CONTACT US</a>
                  </li>
                </ul>
              </div>
            </div>
    </header>
    <div class="patient-img">
        <img src="" alt="Satisfied Patient">
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
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
