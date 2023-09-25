<script>
    import Footer from "$lib/Footer.svelte";
import Navbar from "../lib/Navbar.svelte";
</script>

<Navbar/>
<div id="root">
    <div class="content">
        <body>
            <slot/>
        </body>
        <Footer/>
    </div>
</div>

<style>
    @import url("/reset.css");
    #root:focus{
        border: solid 3px hsla(152, 62%, 47%, 0.573);
    }
    #root{
        height: calc(100vh - 3.1em);
        overflow: scroll;
    }
    .content{
        height: 100vh;
        min-width: 100vw;
        max-width: 100ch;
    }
</style>