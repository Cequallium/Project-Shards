<script>
    import About from "../routes/about/+page.svelte"
    import { page } from '$app/stores';
    // import { onMount } from "svelte";
    /**
     * @type {HTMLDialogElement}
	 */
    let menu;
        /**
	 * @type {HTMLDialogElement}
	 */
    let aboutDiag;
    let isOpen = false;
    function toggleMenu(){
        if(menu.open){
            menu.close();
            isOpen = true
        }
        else{
            menu.show();
            isOpen = false
        }
    }
    // onMount(()=>{
    //     menu.addEventListener("click", e => {
    //         const dialogDimensions = menu.getBoundingClientRect()
    //         if (
    //             e.clientX < dialogDimensions.left ||
    //             e.clientX > dialogDimensions.right ||
    //             e.clientY < dialogDimensions.top ||
    //             e.clientY > dialogDimensions.bottom
    //         ) {
    //             menu.close()
    //         }
    //     })
    // })
</script>

<nav>
    <div class="nav">
        <a href="/" class:onPage={$page.url.pathname === "/"}>Home</a>
        <a href="idk">Community</a>
    </div>
    <button on:click={toggleMenu} class="menu">
        <img src="/icons/menu.svg" alt="menu icon">
    </button>
</nav>
<dialog bind:this={menu} class="menuDiag">
    <div class="items">
        <button on:click={()=>{aboutDiag.showModal(); toggleMenu();}}>
            About Project Shards
        </button>
    </div>
</dialog>
<dialog class="about" bind:this={aboutDiag}>
    <About isDialog on:closeAboutPage={()=>{aboutDiag.close()}}/>
</dialog>

<style>
    .about{
        color: white;
        background-color: #282828;
        border: 2px solid #383838;
        border-radius: 15px;
        padding: 1em;
        min-width: 70vw;
        max-width: 50ch;
        height: 80vh;
    }
    .about::backdrop{
        background-color: #181818;
        opacity: 0.4;
        backdrop-filter: blur(5px);
    }
    .menuDiag{
        margin-right: 1vw;
        margin-top: -0.5em;
        border-radius: 10px;
        padding: 0.3em 0.3em;
        border: none;
        background-color: #3E3E3E;
        color: white;     
    }

    .items{
        display: flex;
        flex-direction: column;
        gap: 3px;
    }
    .items button{
        padding: 0.35em 0.8em;
        font-size: 0.9rem;
        border-radius: 6px;
        transition: 60ms background-color;
        user-select: none;
        background-color: inherit;
        color: inherit;
        font-family: inherit;
        text-align: inherit;
    }
    .items button:hover{
        background-color: #4d4d4d;

    }
    nav{
        width: 100vw;
        height: 3em;
        background-color: #303030;
        border-bottom: solid 2px #414141;
        display: flex;
        flex-direction: row;
    }
    .nav{
        width: 100vw;
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        gap: 0.5vw;
        justify-self: center;
    }
    nav a,.menu{
        padding: 0.4em 2vw;
        font-weight: bold !important;
        font-size: medium;
        user-select: none;
        border-radius: 6px;
        transition: background-color 280ms cubic-bezier(0.215, 0.610, 0.355, 1);
        color: white;
        background-color: #303030;
    }
    nav a:hover,.menu:hover{
        background-color: #3E3E3E;
    }

    .onPage{
        background-color: #454545;
    }
    .onPage:hover{
        background-color: #4d4d4d;
    }
    .menu{
        padding: 0px;
        justify-self: end;
        width: 3ch;
        height: 3ch;
        margin-top:auto;
        margin-bottom:auto;
        margin-left: -5ch;
        display: flex;
    }
    .menu img{
        margin: auto;
        width: 1.4ch;
    }
</style>