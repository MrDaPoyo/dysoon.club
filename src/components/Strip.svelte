<script>
    import strips from "../assets/images/strips.svg";
    
    // Export props with default values
    export let left = false;
    export let width = 5;
    export let length = 3;
</script>

<style>
    .marquee {
        position: relative;
        width: 100%;
        height: fit-content;
        overflow: hidden;
    }

    .marquee-content {
        display: flex;
        width: max-content; /* Ensures content takes necessary width */
        animation-duration: calc(20s + (var(--length) * 5s));
        animation-timing-function: linear;
        animation-iteration-count: infinite;
    }

    .left .marquee-content {
        animation-name: scroll-left;
    }

    .right .marquee-content {
        animation-name: scroll-right;
    }

    .strip {
        display: flex;
        flex-direction: row;
        align-items: center;
    }

    @keyframes scroll-left {
        0% { transform: translateX(0); }
        100% { transform: translateX(calc(-50% - 1px)); } /* Small offset to prevent gap */
    }

    @keyframes scroll-right {
        0% { transform: translateX(calc(-50% - 1px)); }
        100% { transform: translateX(0); }
    }
</style>

<div class="marquee {left ? 'left' : 'right'}" style="--length: {length}" transition:persist>
    <div class="marquee-content">
        <!-- First copy of content -->
        <div class="strip">
            {#each Array(width) as _}
                <img src={strips.src} alt="DYSOON.CLUB" />
            {/each}
            <img src={strips.src} alt="DYSOON.CLUB" />
            <img src={strips.src} alt="DYSOON.CLUB" />
            <img src={strips.src} alt="DYSOON.CLUB" />
        </div>
        
        <!-- Duplicate for seamless loop -->
        <div class="strip">
            {#each Array(width) as _}
                <img src={strips.src} alt="DYSOON.CLUB" />
            {/each}
            <img src={strips.src} alt="DYSOON.CLUB" />
            <img src={strips.src} alt="DYSOON.CLUB" />
            <img src={strips.src} alt="DYSOON.CLUB" />
        </div>
    </div>
</div>
