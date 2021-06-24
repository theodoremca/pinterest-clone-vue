<template>
  <div @mouseenter="display=true"  @mouseleave="display=false">

      <div class="overlay" :class="{'overlay-display':display}" >

        <div class="link-container"> <a :href="link"><img class="link-icon" style="height:15px; width:15px;"  src="https://img.icons8.com/android/24/000000/link.png" alt="share icon"> <span class="link">{{details}}</span></a></div>
    <div class="left-content" style="  float: right;">
      <img style="height:40px; width:40px;"  src="https://img.icons8.com/bubbles/50/000000/upload.png" alt="share icon">
      <img style="height:40px; width:40px;"  src="https://img.icons8.com/color/48/000000/connection-status-off--v1.png" alt="share icon">
    </div>

      </div>

    <img  :src="img" :alt="altImg" />
    <div class="tile-bottom">
      <p class="description">{{description}} </p>
    </div>


  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    link:String,
    img: String,
    altImg: String,
    title: String,
    details: String,
    description: String
  },
  data: () => ({
    display: true,
  }),
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  img {
    width: 100%;
    height: auto;
    border-radius: 12px;
  }
.description{
  font-family:"Segoe UI";
  font-weight:bolder;
  font-size:14px;
  white-space:nowrap;
  overflow:hidden;
  text-overflow:ellipsis;
  width:200px;
}
  .overlay {
    bottom: 60px;
    display: none;
    margin-bottom:5%;
    margin-right:2%;
    margin-left:2%;
    height: 45px;
    border-radius: 10px;
    position: absolute;
    z-index: 1;
    background-color:#ffffff05;
    min-width:inherit;
  }
  .link-container {
    height: 30px;
    border-radius:20px;
    background-color:floralwhite;
    min-width: 120px;
    align-self: center;
    align-items: center;
    }
  .link{

    position: absolute;
    top: 12px;
    left:30px;
    font-family:"Segoe UI";
    font-weight:bolder;
    font-size:14px;
    white-space:nowrap;
    overflow:hidden;
    text-overflow:ellipsis;
    width:90px;


  }

  .link-icon{

    position: absolute;
    top: 15px;
    left:10px;



  }


  .overlay-display{
    display: flex;
    justify-content: space-between;
    align-items: center;
    min-width:40%;

  }

  .overlay .search-container {
    width: 40%;
    padding: 0;
    margin-left: 10px;
    min-width:100%;
    height: 25px;
    border-radius:10px;
    background-color:floralwhite;
  }

  .save-container {
    background-color: #bd081d;
    width:30%;
    padding-bottom: -50px;
    margin: auto 0;
    color: white;
    height: inherit;
    -webkit-border-top-right-radius: 10px;
    -webkit-border-bottom-right-radius: 10px;
    -moz-border-radius-topright: 10px;
    -moz-border-radius-bottomright: 10px;
    border-top-right-radius: 10px;
    border-bottom-right-radius: 10px;
  }
.left-content{
  position: relative;
  left: 15px;
}
  .dot {
    height: 25px;
    width: 25px;
    background-color: #bbb;
    border-radius: 50%;
    display: inline-block;
    padding:5px;
  }


</style>
