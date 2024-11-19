<template>
  <navigation-bar :pages="pages" :active-page="activePage"
    :nav-link-click="(index) => activePage = index"></navigation-bar>

  <page-viewer :page="pages[activePage]"></page-viewer>
  </template>

<script>
import PageViewer from './components/PageViewer.vue';
import NavigationBar from './components/NavigationBar.vue';

export default {
  components: {
    NavigationBar, 
    PageViewer
  },
  data() {
    return {
      activePage: 0,
      pages: [
        { link: { text: 'Home', url: '#' }, pageTitle: 'Home Page', content: 'This is the home page' },
        { link: { text: 'About', url: '#' }, pageTitle: 'About Page', content: 'A little about Sideline Photography' },
        { link: { text: 'Contact', url: '#' }, pageTitle: 'Contact Page', content: 'How to get ahold of us' },
        { link: { text: 'Gallery', url: '#' }, pageTitle: 'Gallery Page', content: 'A beautiful gallery' }
      ]
    };
  }
}
</script>
