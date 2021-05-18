<template>
  <div id="app">
   <Header />
   <Home />
   <Footer />
  </div>
</template>

<script>

import './styles/style.css'

import Header from './components/Header';
import Footer from './components/Footer'
import Home from './pages/Home';

export default {
  name: 'App',
  components: {
    Header,
    Home,
    Footer
    
  }
}
</script>

