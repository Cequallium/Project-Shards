<script lang=ts>
    export let title:string, icon = "unspecified";
</script>

<div class="card">
    <div class="title">
        <img src="/icons/{icon}.svg" alt="{icon + " icon"}" class="icon"/>
        <h1>{title}</h1>
    </div>
    <h3>
        <slot></slot>
    </h3>
</div>

<style>
    .icon{
        margin-right: 9px;
        height: 2ch;
        margin-bottom: -2px;
    }
    .title{
        align-items: center;
        display: flex;
        flex-direction: row;
    }
    .card{
        background-color: #353535;
        padding: 1.5em;
        border-radius: 15px;
        width: 25vh;
        min-height: 20vh;
        word-wrap: normal;
        box-shadow: 0px 6px 7px -4px rgba(0,0,0,0.25);
    }
    .title{
        font-size: 0.7rem;
        padding-bottom: 0.6em;
        margin-bottom: 1em;
        border-bottom: solid 2px #464646;
    }
    .card h3{
        font-size: small;
    }
</style>