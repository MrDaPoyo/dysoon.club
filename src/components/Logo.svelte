<script>
    import logoImage from "../assets/images/logo.svg";
    import beginRacing from "../assets/images/begin_racing.svg";
    import strips from "../assets/images/strips.svg";
    let props = $props();
    let beginRacingVisible = true;
</script>

{#if props.full}
    <div class="full">
        <img src={logoImage.src} alt="DYSOON.CLUB GO GO GOOOO!!!!!" style="max-height: 100%; height: auto;" />
        <img src={strips.src} alt="DYSOON.CLUB GO GO GOOOO!!!!!" style="max-height: 100%; height: auto;" />
        <img src={beginRacing.src} alt="DYSOON.CLUB GO GO GOOOO!!!!!" style="max-height: 100%; height: auto; cursor: pointer;" class:fadeOut={beginRacingVisible} on:click={() => beginRacingVisible = false}  />
        <style>
            .fadeOut {
            animation: fadeOut 1s infinite;
            }

            @keyframes fadeOut {
            0% {
                opacity: 1;
            }
            33% {
                opacity: 0;
            }
            66% {
                opacity: 1;
            }
            }
        </style>
        <script>
            let beginRacingVisible = true;
        </script>
        <img src={strips.src} alt="DYSOON.CLUB GO GO GOOOO!!!!!" style="max-height: 100%; height: auto;" />
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
            max-height: 80vh;
        }
    </style>
{:else}
    <img src={logoImage.src} alt="DYSOON.CLUB GO GO GOOOO!!!!!" />
{/if}
