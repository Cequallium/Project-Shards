<script>
    export let isDialog = false;
    import { createEventDispatcher } from 'svelte';
	const closeAbout = createEventDispatcher();

</script>

{#if isDialog}
    <div class="closebar">
        <div class="close">
            <img on:keyup={()=>{closeAbout("closeAboutPage")}} on:click={()=>{closeAbout("closeAboutPage")}} src="/icons/close.svg" alt="close button">
        </div>
    </div>
{/if}
<div class="about">
    <div class="main">
        <div class="logo"><img src="/logo.svg" alt=""></div>
        <div class="name">
            Project Shards 
        </div>
        <div class="team">The Project Shards team</div>
        <div class="version">0.0.0</div>
    </div>
    <div class="group 1">
        <a href="/new" class="new">What's New </a>
        <a href="/new" class="details">Details</a>
    </div>
</div>

<style>
    .about{
        scrollbar-width: 0;
    }
    .about::-webkit-scrollbar{
        display: none;
    }
    .close{
        width: 1ch;
        height: 1ch;
        margin-right: 1.1em;
    }
    .closebar{
        height: fit-content;
        display: flex;
        flex-direction: row-reverse;
    }
    .close img{
        border-radius: 100%;
        background-color: #3c3c3c;
        width: 1ch;
        height: 1ch;
        padding: 1ch;
        transition: background-color 180ms;
    }
    .close img:hover{
        background-color: #474747;
    }
    .about{
        margin-top: 5em;
        display: flex;
        align-items: center;
        flex-direction: column;
        gap: 2em;
        user-select: none;
    }
    .logo img{
        height: 6em;
    }
    .name{
        font-weight: 900;
        font-size: 1.8rem;
        margin-bottom: -0.1em;
    }
    .main{
        display: flex;
        align-items: center;
        flex-direction: column;
        gap: 0.6em;
        text-align: center;
    }
    .version{
        width: fit-content;
        border-radius: 20px;
        background-color: hsla(152, 62%, 47%, 0.2);
        color: var(--accent);
        font-weight: 900;
        padding: 0.2em 0.8em;
        transition: background-color 160ms;
    }
    .version:hover{
        background-color: hsla(152, 62%, 47%, 0.25);
    }
    .group{
        display: flex;
        flex-direction: column;
        width: 80%;
        align-items: center;
    }
    .group a{
        width: 99%;
        max-width: 90ch;
        background-color: #353535;
        padding: 1em 0.8em;
        transition: background-color 280ms;
        border-bottom: solid 0.2px rgb(34, 34, 34);
        color: white;
    }
    .group a::before{
        content: "🡲";
        /* color: #ffffff00;
        background: url("/icons/rightArrow.svg") no-repeat; */
        position: relative;
        left: 95%;
        opacity: 0.8;
    }
    .group a:first-child {
        border-radius: 15px 15px 0px 0px;
    }
    .group a:last-child {
        border: none;
        border-radius: 0px 0px 15px 15px;
    }
    .group a:hover{
        background-color: #3c3c3c;
    }
</style>