<script>
    import logoImage from "../assets/images/logo.svg";
    import beginRacing from "../assets/images/begin_racing.svg";
    import strips from "../assets/images/strips.svg";
    let props = $props();
</script>

{#if props.full}
    <div class="full">
        <img src={logoImage.src} alt="DYSOON.CLUB GO GO GOOOO!!!!!" style="max-height: 40%; width: 100%;" />
        <img src={strips.src} alt="DYSOON.CLUB GO GO GOOOO!!!!!" style="max-height: 40%; width: 100%;" />
        <img src={beginRacing.src} id ="beginRacing" alt="DYSOON.CLUB GO GO GOOOO!!!!!" style="max-height: 40%; width: 100%;" on:click={navigate('/home')} />
        <img src={strips.src} alt="DYSOON.CLUB GO GO GOOOO!!!!!" style="max-height: 40%; width: 100%;" />
    </div>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        .full {
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
        }
    </style>
{:else}
    <img src={logoImage.src} alt="DYSOON.CLUB GO GO GOOOO!!!!!" />
{/if}
