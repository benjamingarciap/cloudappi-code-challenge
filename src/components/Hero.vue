
<template>
  <div>
    <div class="hero-container">
      <div class="hero-text-wrapper">
        <p class="hero-greeting">Hi! This is the</p>
        <img src="./../assets/cloudappilogo.svg" alt="cloudappi">
        <h1 class="hero-title">User List Code Challenge</h1>
        <p class="hero-greeting">Check it out</p>
      </div>
        <a v-scroll-to="'#friend-list'">
        <div class="center-con">
          <div class="round">
              <div id="cta">
                <span class="arrow primera next "></span>
                <span class="arrow segunda next "></span>
              </div>
          </div>
        </div>
        </a>
  </div>
  </div>
</template>

<script>

  export default {

    name: 'FriendList',
    props: {
      friends: Array
    },

    data: () => ({
      show: false,
    })
  }

</script>

<style scoped lang="scss">

  .hero-container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 100vh;
  }

  .hero-text-wrapper {
    font-family: 'Poppins', sans-serif;
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-bottom: 3em;

    p {
      height: 21px;
      margin-bottom: 6px;
      max-width: 516px;
      padding: 0 10px;
      font-weight: 500;
      font-size: 1.3em;
      color: rgb(52, 52, 52);

      @media screen and (max-width: 726px) {
        font-size: 1em;
      }
    }

    p:last-of-type {
      color: #FF8412;
      margin: 10px 0 0 0;
    }

    img {
      width: 14em;
    
      @media screen and (max-width: 726px) {
        width: 12em;
      }
    }
  }

  .hero-title {
    width: 14.1em;
    text-align: center;
    color: white;
    font-size: 2.7em;
    letter-spacing: -1px;
    font-weight: 500;
    margin: 0;
    padding-left: 5px;
    background-color: #FF8412;
    padding:0px 20px 0px 20px;

    @media screen and (max-width: 726px) {
      width: 13.1em;
      font-size: 2em;
    }

    @media screen and (max-width: 726px) {
      width: 14em;
      font-size: 1.3em;
    }
  };

  .container-list {
    display: flex;
    justify-content: center;
  }

  .center-con {
    display: flex;
    align-items: center;
    justify-content: center;
    transform: rotate(90deg);
    margin-top: 2em;
  }

  .round {
    position: absolute;
    width: 42px;
    height: 42px;
    border-radius: 100%;
  }

  #cta{
      width:100%; cursor: pointer; position: absolute;
  }

  #cta .arrow{ 
    left: 30%;
  }

  .arrow {  position: absolute; bottom: 0;  margin-left:0px; width: 16px; height: 16px; background-size: contain; top:14px; }
  .segunda{  margin-left: 8px;}
  .next {
    background-image: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNDUiIGhlaWdodD0iNzUiIHZpZXdCb3g9IjAgMCA0NSA3NSIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggZD0iTTQyLjYxMjggMzIuMDU4NkM0NS42OTAyIDM1LjEzNTkgNDUuNjQ0NSA0MC4xNjMzIDQyLjUyMTQgNDMuMjg2M0MzOS4zOTg0IDQ2LjQwOTQgMzQuMzcxIDQ2LjQ1NTEgMzEuMjkzNyA0My4zNzc3TDIuMzQ4MzcgMTQuNDMyNEMtMC43MTM3MzUgMTEuMzU1MSAtMC42NjgwMzIgNi4zMjc3MiAyLjQ1NTAxIDMuMjA0NjhDNS41NzgwNiAwLjA4MTYyODkgMTAuNjA1NCAwLjAzNTkyNTYgMTMuNjY3NSAzLjExMzI3TDQyLjYxMjggMzIuMDU4NloiIGZpbGw9IiMwMEJDRDQiLz4KPHBhdGggZD0iTTQyLjYxMjkgNDMuMjU1OUM0NS42OTAzIDQwLjE3ODUgNDUuNjQ0NSAzNS4xNTEyIDQyLjUyMTUgMzIuMDI4MUMzOS4zOTg1IDI4LjkwNTEgMzQuMzcxMSAyOC44NTk0IDMxLjI5MzggMzEuOTM2N0wyLjM0ODQ1IDYwLjg4MkMtMC43Mjg4OTEgNjMuOTU5NCAtMC42ODMxODcgNjguOTg2NyAyLjQzOTg2IDcyLjEwOThDNS41NjI5MSA3NS4yMzI4IDEwLjU5MDMgNzUuMjc4NSAxMy42Njc2IDcyLjIwMTJMNDIuNjEyOSA0My4yNTU5WiIgZmlsbD0iIzAwQkNENCIvPgo8L3N2Zz4K);
  }


  .bounceAlpha {
    animation-name: bounceAlpha;
    animation-duration:1.4s;
    animation-iteration-count:infinite;
    animation-timing-function:linear;

    @keyframes bounceAlpha {
        0% {opacity: 1; transform: translateX(0px) scale(1);}
        25%{opacity: 0; transform:translateX(10px) scale(0.9);}
        26%{opacity: 0; transform:translateX(-10px) scale(0.9);}
        55% {opacity: 1; transform: translateX(0px) scale(1);}
    }
  }

  .arrow.primera.bounceAlpha {
      animation-name: bounceAlpha;
      animation-duration:1.4s;
      animation-delay:0.2s;
      animation-iteration-count:infinite;
      animation-timing-function:linear;
  }

  .round .arrow{
      animation-name: bounceAlpha;
      animation-duration:1.4s;
      animation-iteration-count:infinite;
      animation-timing-function:linear;
  }
  .round .arrow.primera{
      animation-name: bounceAlpha;
      animation-duration:1.4s;
      animation-delay:0.2s;
      animation-iteration-count:infinite;
      animation-timing-function:linear;
  }

</style>
