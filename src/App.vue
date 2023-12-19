<template>
  <div class="main" >
    <div class="flexed">
    <h2 class="title">TradingView Widget</h2>
   

    <!-- fork here -->
    <a href="https://github.com/Francis-Mwaniki/vue-trading-view-integration"
      target="_blank"
      rel="noopener noreferrer"
      class="github"
      aria-label="View source on GitHub">
      <svg
        
       xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" data-slot="icon" class="w-6 h-6 code-corner">
  <path stroke-linecap="round" stroke-linejoin="round" d="M17.25 6.75 22.5 12l-5.25 5.25m-10.5 0L1.5 12l5.25-5.25m7.5-3-4.5 16.5" />
</svg>

    </a>
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



.github{
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: var(--background-color);
  color: var(--text-color);
  padding: 10px;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  opacity: 0.9;
  transition: all 0.5s ease;
}

.github:hover{
  background-color: var(--text-color);
  color: var(--background-color);
  transition: all 0.5s ease;
}

.github svg{
  width: 30px;
  height: 30px;
  transition: all 0.5s ease;
}

.github:hover svg{
  transition: all 0.5s ease;
  animation: fadeIn 0.5s ease;
}

.code-corner {
  position: absolute;
  top: 0.5;
  right: 2;
  border: 0;
  
}

.code-corner svg {
  width: 2rem;
  height: 2rem;
  fill: var(--text-color);
  transition: fill 0.3s ease;
}


@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}


@media (max-width: 768px) {
  .github{
  
  }

  .github svg{
    width: 20px;
    height: 20px;
  }

}

</style>