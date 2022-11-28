<template>
  <div class="container" id="container">
    <div class="header">
      <div class="header__logo">
        <div class="header__logo__1">
          <button>M</button>
          <div>MILANO</div>
        </div>
        <div class="header__logo__hamburger">
          <span></span>
          <span></span>
          <span></span>
        </div>
      </div>
      <div class="header__text">
        <div class="header__text__get">GET<br> YOURSELF</div>
        <div class="header__text__into">INTO THE<br> RIGHT GEAR</div>
        <div class="header__text__view">VIEW SUMMER COLLECTIONS</div>
      </div>
      <div class="header__search" style="background-image: url('/images/header.jpg')">
        <div class="square"></div>
      </div>
    </div>
    <div class="body">
      <div class="img1" style="background-image: url('/images/img1.jpg') ">
        <span>Hoodies</span>
      </div>
      <div class="img2" style="background-image: url('/images/img2.jpg')">
        <span>Sweatshirts</span>
      </div>
      <div class="img3" style="background-image: url('/images/img3.jpg')">
        <span>Shirts</span>
      </div>
      <div class="img4" style="background-image: url('/images/img4.jpg')">
        <span>T-Shirts</span>
      </div>
      <div class="img5" style="background-image: url('/images/img5.jpg')">
        <span>Jackets</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MainFile',
  props: {
  },

  mounted(){
    let observer = new IntersectionObserver((entries)=>{
      entries.forEach((entry)=>{
        console.log(entry)
        console.log(document.body.scrollTop)
        if(this.prevRat < entry.intersectionRatio){
          console.log('prevRat < entry.intersectionRatio')
        }else{
          console.log('prevRat > entry.intersectionRatio')
        }
        console.log('prevRat ', this.prevRat)
        console.log('entry.intersectionRatio', entry.intersectionRatio)
        this.prevRat = entry.intersectionRatio
      })
    });
    const elemnts = document.getElementById('container');
    observer.observe(elemnts);
  }
} 
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
  @import '../assets/css/body.scss';
</style>
