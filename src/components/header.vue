<template>
  <header>
    <nav class="navbar">
      <a href="#" class="nav-logo">LOGO</a>
      <ul class="nav-menu">
        <li class="nav-item" v-for="link in links" :key="link">
          <a href="#" class="nav-link">{{ link }}</a>
        </li>

      </ul>

      <div class="hamburger" @click="menuOpen = !menuOpen">
        <i class="bi bi-list"></i>
      </div>
    </nav>

    <div class="dropdown" :class="{ 'dropdown-after' : menuOpen }">
    <ul class="nav-list">
      <li class="nav-item" v-for="link in links" :key="link">
        <a href="#">{{ link }}</a>
      </li>

    </ul>
  </div>
  </header>
</template>

<script>
export default {
  name: "header-component",
  data(){
    return{
      links:["link1", "link2", "link3"],
      menuOpen: false
    }

  }
}
</script>

<style>
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
header{
  background-color: #4040a4;
}
li{
  list-style: none;
}
a{
  color: white;
  text-decoration: none;
}
.navbar{
  min-height: 70px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 25px;
}
.nav-menu{
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 60px;
  font-size: 20px;
}
.nav-logo{
  font-size: 2rem;
}
.nav-link{
  transition: 0.5s ease;
}
.nav-link:hover{
  color: #0084ff;
}
.hamburger{
  display: none;
  cursor: pointer;
  color: white;
  font-size: 30px;

}

.dropdown{
  display: none;
}
@media (max-width: 768px) {
  .hamburger{
    display: block;
  }

  .dropdown {
    height: 0;
    background-color: #232369;
    transition: height 0.2s ease;
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;
  }

  .dropdown-after {
    height: calc(100vh - 50px);
    transition: height 0.2s ease;
  }


  .nav-list {
    list-style: none;
    display: flex;
    flex-direction: column;

  }

  .nav-item {
    text-transform: uppercase;
    text-align: center;
    padding: 35px;
    margin: 16px;
    font-size: 25px;
  }

  .nav-item a{
    transition: 0.5s ease;
  }
  .nav-item a:hover{
    color: dodgerblue;
  }

  .nav-menu{
    position: fixed;
    left: -100%;
    top: 70px;
    gap: 0;
    flex-direction: column;
    background-color: #39398c;
    width: 100%;
    text-align: center;
    transition: 0.3s;
  }


}
</style>