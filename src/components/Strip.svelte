<script>
    let props = $props();
    import strips from "../assets/images/strips.svg";

    let animationDurationLeft = `marquee ${props.width * 5}s linear infinite`;
    let animationDurationRight = `marqueereverse ${props.width * 5}s linear infinite`;
</script>

<style>
    .marquee {
        position: relative;
        width: 100vw;
        max-width: 100%;
        height: 70px;
        display: flex;
        justify-content: center;
        align-items: center;
        overflow: hidden;
    }

    .trackLeft {
        position: absolute;
        white-space: nowrap;
        will-change: transform;
        display: flex;
        flex-direction: row;
        animation: marquee 20s linear infinite; /* Default animation */
    }

    .trackRight {
        position: absolute;
        white-space: nowrap;
        will-change: transform;
        display: flex;
        flex-direction: row;
        animation: marqueereverse 20s linear infinite; /* Default animation */
    }

    @keyframes marquee {
        from {
            transform: translateX(0);
        }

        to {
            transform: translateX(-50%);
        }
    }

    @keyframes marqueereverse {
        from {
            transform: translateX(0);
        }

        to {
            transform: translateX(50%);
        }
    }

    .strip {
        display: inline-block;
        padding: 0;
        margin: 0;
        height: 100%;
        width: 100%;
        display: flex;
        flex-direction: row;
        justify-content: start;
        align-items: center;
    }

    .strip img {
        margin: 0;
    }
</style>

<div class="marquee">
    {#if props.left}
        <div class="trackLeft" style="animation: {animationDurationLeft}">
            <div class="content">
                <div class="strip">
                    {#each Array(props.width) as _}
                        <img src={strips.src} alt="DYSOON.CLUB GO GO GOOOO!!!!!" margin="0" />
                    {/each}
                </div>
            </div>
        </div>
    {:else}
        <div class="trackRight" style="animation: {animationDurationRight}">
            <div class="content">
                <div class="strip">
                    {#each Array(props.width) as _}
                        <img src={strips.src} alt="DYSOON.CLUB GO GO GOOOO!!!!!" margin="0" />
                    {/each}
                </div>
            </div>
        </div>
    {/if}
</div>