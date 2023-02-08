<template>
  <header>
    <nav class="navbar">
      <a href="#" class="nav-logo">LOGO</a>
      <ul class="nav-menu">
        <li class="nav-item" v-for="link in links" :key="link">
          <a href="#" class="nav-link">{{ link }}</a>
        </li>
        <button class="nav-btn">Sign In</button>
      </ul>

      <div class="hamburger" @click="menuOpen = !menuOpen">
        <i class="fa-solid fa-bars"></i>
      </div>
    </nav>

    <div class="dropdown" :class="{ 'dropdown-after' : menuOpen }">
    <ul class="nav-list">
      <li class="nav-item" v-for="link in links" :key="link">
        <a href="#">{{ link }}</a>
      </li>
      <button class="nav-btn">Sign In</button>

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

<style scoped>
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
header{
  background-color: #f8f7f7;
}
.nav-logo{
  font-weight: bold;
  color: #0084ff;
}
li{
  list-style: none;
}
a{
  color: #919191;
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
  font-weight: 500;
}
.nav-link:hover{
  color: #0084ff;
}

.nav-btn{
  cursor: pointer;
  padding: 10px;
  background-color: #0084ff;
  color: white;
  border-radius: 5px;
}
.nav-btn:hover{
  background-color: #0468c5;
  transition: 0.5s ease;
}

.hamburger{
  display: none;
  cursor: pointer;
  color: #0084ff;
  font-size: 30px;

}

.dropdown{
  display: none;
}
@media (max-width: 768px) {
  .hamburger{
    display: block;
  }

  .nav-btn{
    font-size: 25px;
  }
  .dropdown {
    height: 0;
    background-color: #e7e7e7;
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
    font-weight: 500;
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