<template>
<h2>App Components</h2>
<NavBar/>
<Spinner/>
<router-view/>
</template>

<script>
import NavBar from './components/NavBar.vue';
import Spinner from './components/Spinner.vue';
 
    export default{
    name: "App",
    components: { NavBar, Spinner }
}
</script>

bootstrap font-awesome axios

npm install bootstrap @fortawesome/fontawesome-free


<style>

</style>
