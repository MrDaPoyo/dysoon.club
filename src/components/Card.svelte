<script>
    let el;
    let shine;

    function handleMouseMove(event) {
        shine.style.transform = `scale(1)`;
        const rect = el.getBoundingClientRect();
        const x = event.clientX - rect.left;
        const y = event.clientY - rect.top;

        const rx = (y - rect.height / 2) / 20;
        const ry = (x - rect.width / 2) / 20;

        el.style.transform = `rotateX(${rx}deg) rotateY(${ry}deg)`;
        shine.style.left = `${x - 100}px`;
        shine.style.top = `${y - 100}px`;
    }

    function handleMouseLeave() {
        shine.style.transform = `scale(0)`;
        el.style.transform = `rotateX(0deg) rotateY(0deg)`;
    }
</script>

<div
    class="card"
    bind:this={el}
    on:mousemove={handleMouseMove}
    on:mouseleave={handleMouseLeave}
>
    <div class="shine" bind:this={shine} />
    <slot />
</div>

<style>
    .card {
        position: relative;
        width: 100%;
        height: 100%;
        padding: 1vh;
        background-color: #A45A00;
        border-radius: 10px;
        transform-style: preserve-3d;
        transition: transform 0.1s ease-out;
        overflow: hidden;
        border: 1px dashed white;
    }

    .shine {
        position: absolute;
        top: 0;
        left: 0;
        width: 200px;
        height: 200px;
        background: radial-gradient(rgba(255,255,255,0.3) 0%, rgba(255,255,255,0.1) 26%, rgba(255,255,255,0) 52%);
        border-radius: 50%;
        transform: translateZ(1px) scale(0);
        pointer-events: none;
        transition: 0.05s;
    }
</style>