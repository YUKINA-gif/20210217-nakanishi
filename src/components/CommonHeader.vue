<template>
      <header id="top-header">
        <div class="flex">
          <h1 class="header-logo">estra inc.</h1>
          <nav class="header-nav">
            <ul>
              <li><a href="#">home</a></li>
              <li><a href="#">about</a></li>
              <li><a href="#">service</a></li>
              <li><a href="#">works</a></li>
              <li><a href="#">price</a></li>
              <li><a href="#">contact</a></li>
            </ul>
          </nav>
        </div>

        <div id="hamburger" @click="hamburger" :class="{'active':isActive}">
          <span></span>
          <span></span>
          <span></span>
        </div>

          <nav class="hbgmenu-nav" :class="{'open':isActive}">
            <p>estra inc.</p>
            <ul class="hbgmenu">
              <li><a href="#">home</a></li>
              <li><a href="#">about</a></li>
              <li><a href="#">service</a></li>
              <li><a href="#">works</a></li>
              <li><a href="#">price</a></li>
              <li><a href="#">contact</a></li>
            </ul>
          </nav>
      </header>
</template>

<script>
export default{
  data() {
    return {
      isActive: false
    };
  },
  methods: {
    hamburger(){
      this.isActive = !this.isActive;
    }
  }
};
</script>


<style scoped>
#top-header {
  height: 70px;
  line-height: 70px;
  background: rgba(0, 0, 0, 1);
}

.header-logo {
  font-size: 20px;
  font-weight: bold;
  margin-left: 35px;
  color: #fff;
  line-height: 70px;
}

.header-nav li {
  display: inline-block;
  margin-right: 35px;
  font-size: 16px;
}

.header-nav a {
  color: #fff;
}

@media screen and (max-width: 768px) {
  #hamburger{
    width: 40px;
    height: 40px;
    position: absolute;
    cursor: pointer;
    z-index: 100;
    top: 15px;
    right: 20px;
    transition: 0.4s;
  }

  #hamburger span{
    position: absolute;
    left: 2px;
    display: block;
    width: 35px;
    height: 2px;
    background-color: #fff;
    transition: 0.4s;
  }

  #hamburger span:nth-of-type(1) {
    top: 10px;
}

  #hamburger span:nth-of-type(2) {
    top: 20px; 
  }

  #hamburger span:nth-of-type(3) {
    top: 30px;
  }

  nav.header-nav{
    display: none;
  }


#hamburger.active span:nth-of-type(1){
  transform: rotate(45deg);
  top: 20px;
}

#hamburger.active span:nth-of-type(2){
  opacity: 0;
}

#hamburger.active span:nth-of-type(3){
  transform: rotate(-45deg);
  top: 20px;
}

.hbgmenu-nav{
  display: block;
  position: fixed;
  top: 0;
  left: calc(-100% - 80px); 
  width: calc(100% - 80px);
  height: 100%;
  background-color: #fff;
  box-shadow: 30px 0 rgba(136, 141, 151, 0.3);
  color: #000;
  z-index: 999;
  text-align: left;
  transition: 0.3s;
}
.hbgmenu-nav.open{
  left:0;
}
}
.hbgmenu-nav p{
  font-size: 20px;
  font-weight: bold;
  margin-left: 10px;
}

.hbgmenu li{
  width: 90%;
  border-bottom: 1px solid darkgray;
}

.hbgmenu li a{
  font-size: 18px;
  margin-left: 10px;
  padding-bottom: 5px;
}

</style>
