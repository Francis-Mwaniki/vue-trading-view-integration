<template>
  <div class="main" >
    <div class="flexed">
    <h2 class="title">TradingView Widget</h2>
    <Header />
   

  </div>
  <div class="my" />
  <Tradingview />

  <footer>
    <p>Created by <a href="https://wwww.francismwaniki.tech">franc</a></p>
  </footer>
  </div>


</template>

<script>
import Header from "./components/header.vue"
import Tradingview from "./components/Tradingview.vue"
export default {

  components: {
    Header,
    Tradingview
  },
  setup () {
    

    return {}
  }
}
</script>

<style scoped>
/* import poppins */
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap');

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
font-family: 'Poppins', sans-serif;

}

.main{
  background-color: var(--background-color);
  color: var(--text-color);
  padding: 10px;
  transition: all 0.5s ease;
  position: relative;
}

.flexed {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  gap: 20px;
  background-color: var(--background-color);
  color: var(--text-color);
  padding: 10px;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  opacity: 0.9;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 999;
  right: 0;
  margin: auto;
  transition: all 0.5s ease;


}

@media (max-width: 768px) {
  
}

h2{
  color: var(--text-color);
  font-size: 1rem;
  font-weight: bold;
  
  text-align: center;

  
}




.my{
 margin-top: 100px;
 margin-bottom: 100px;
}

footer{
  text-align: center;
  margin-top: 60px;

}

footer a{
  color: var(--text-color);
  text-decoration: none;
  font-weight: bold;
}

footer a:hover{
  color: var(--text-color);
  text-decoration: underline;
}

</style>