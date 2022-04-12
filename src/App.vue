<template>
  <Accordion @toggle-item-class="toggleClass" :data="accordionData" :active="activeID" />
</template>

<script>
import Accordion from './components/Accordion';

export default {
  name: 'App',
  components: {
    Accordion
  },
  data() {
    return {
      accordionData: [],
      activeID: 0
    }
  },
  methods: {
    // This method will pull the value of single accordion id
    // and will pass it to this.activeID only if the current accordion isn't active
    toggleClass(id) {
      if(this.activeID === id) {
        this.activeID = 0;
        return;
      }
      
      this.activeID = id;
    }
  },
  created() {
    // Let's create some data to work with
    this.accordionData = [
      {
        id: 1,
        title: 'Accordion Item #1',
        body: '<strong>This is the first item\'s accordion body</strong>. It is shown by default, until the collapse plugin adds the appropriate classes that we use to style each element. These classes control the overall appearance, as well as the showing and hiding via CSS transitions. You can modify any of this with custom CSS or overriding our default variables. It\'s also worth noting that just about any HTML can go within the <code>.accordion-body</code>, though the transition does limit overflow.'
      },
      {
        id: 2,
        title: 'Accordion Item #2',
        body: '<strong>This is the second item\'s accordion body</strong>. It is shown by default, until the collapse plugin adds the appropriate classes that we use to style each element. These classes control the overall appearance, as well as the showing and hiding via CSS transitions. You can modify any of this with custom CSS or overriding our default variables. It\'s also worth noting that just about any HTML can go within the <code>.accordion-body</code>, though the transition does limit overflow.'
      },
      {
        id: 3,
        title: 'Accordion Item #3',
        body: '<strong>This is the third item\'s accordion body</strong>. It is shown by default, until the collapse plugin adds the appropriate classes that we use to style each element. These classes control the overall appearance, as well as the showing and hiding via CSS transitions. You can modify any of this with custom CSS or overriding our default variables. It\'s also worth noting that just about any HTML can go within the <code>.accordion-body</code>, though the transition does limit overflow.'
      }
    ]
  }
}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
    margin-top: 60px;
  }

code {
  color: #dc3545;
  font-size: .9rem;
}
</style>
