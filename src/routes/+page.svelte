<script>
    import Card from "../lib/Card.svelte";
import DownloadButton from "../lib/DownloadButton.svelte";    

</script>

<svelte:head>
    <title>Project Shards</title>
</svelte:head>

<div>
    <div class="sections">
        <section class="intro">
            <div class="herotext">
                <h1>Project Shards</h1>
                <h3>The next-gen immutable distro <br/>
                    Powered by flatpak and fox giggles
                </h3>
               <DownloadButton/>
            </div>
            <div class="herologo">
                <img src="/logo.svg" alt="The Project Shards logo">
            </div>
        </section>
        <section class="mockup">
            <img src="/mockup.svg" alt="fsdf">
        </section>
        <section class="features">
            <h1>Features</h1><br>
            <div class="cards">
                <Card icon="immutable" title="Immutable!">
                    The entirety of Project Shards has been designed with easy immutability in mind. That means it's really really hard to break your installation. 
                </Card>
                <Card icon="download" title="appD">
                    Simply drag and drop a flatpak or an appimage into the designated folder and it will automatically get installed and set up. 
                </Card>
                <Card icon="partitions" title="Separated system">
                    The system is broken down into a different Btrfs volumes, allowing it to be immutable. 
                </Card>
                <Card icon="github" title="Community driven">
                    All components of Project Shards are fully free and open source, licensed under GPLv3-only. 
                </Card>
            </div>
        </section>
    </div>
    <section class="end">
        <div class="calltoaction">
            <h1>So what are you waiting for?</h1>
            <DownloadButton/>
        </div>
    </section>
</div>

<style>
    .mockup{
        margin: 5em 0em;
        text-align: center;
    }
    .mockup img{
        width: 80vw;
        max-width: 70ch;
        user-select: none;
    }
    .intro{
        margin-top: 1.5em;
    }
    .herotext h1{
        font-size: 2.5rem;
    }
    .herotext h3{
        margin-bottom: 7vh;
    }
    .herologo{
        display: flex;
    }
    .herologo img{
        margin: auto;
        height: 25vh;
    }
    .intro{
        padding: 2em;
        display: grid;
        grid-template-columns: 1fr 1fr;
    }
    .sections{
        padding: 0em 1.5em;
    }
    .cards{
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        gap: 1.5em;
        justify-content: center;
    }
    .features{
        text-align: center;
    }
    .calltoaction{
        margin: auto;
        text-align: center;
    }
    :global(.calltoaction .download){
        margin: 1em auto;
    }
    .end{
        height: 100vw;
        display: flex;
        background: url("/downloadbg.svg") no-repeat;
        background-size: 100vw;
    }
</style>