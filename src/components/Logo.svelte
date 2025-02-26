<script>
    import logoImage from "../assets/images/logo.svg";
    import beginRacing from "../assets/images/begin_racing.svg";
    import strips from "../assets/images/strips.svg";
    import { displayPartsToString, flattenDiagnosticMessageText } from "typescript";
    let props = $props();
</script>

{#if props.full}
    <div class="full">
        <img src={logoImage.src} alt="DYSOON.CLUB GO GO GOOOO!!!!!" />
        <div class="marquee">
            <div class="trackLeft">
                <div class="content">
                    <div class="strip">
                        <img src={strips.src} alt="DYSOON.CLUB GO GO GOOOO!!!!!" margin="0" />
                        <img src={strips.src} alt="DYSOON.CLUB GO GO GOOOO!!!!!" margin="0" />
                    </div>
                </div>
            </div>
        </div>
        <style>
            .marquee {
                position: relative;
                width: 100vw;
                max-width: 100%;
                height: 6vh;
                overflow-x: hidden;
                display: flex;
                justify-content: center;
                align-items: center;
            }

            .trackLeft {
                position: absolute;
                white-space: nowrap;
                will-change: transform;
                animation: marquee 10s linear infinite;
                display: flex;
                flex-direction: row;
            }

            .trackRight {
                position: absolute;
                white-space: nowrap;
                will-change: transform;
                animation: marquee 10s linear infinite reverse;
                display: flex;
                flex-direction: row;
            }

            @keyframes marquee {
                from {
                    transform: translateX(0);
                }
                to {
                    transform: translateX(-50%);
                }
            }

            .strip {
                display: inline-block;
                padding: 0;
                margin: 0;
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
        <button on:click={navigate("/home")}>
            <img
                src={beginRacing.src}
                id="beginRacing"
                alt="DYSOON.CLUB GO GO GOOOO!!!!!"
            />
        </button>
        <div class="marquee">
            <div class="trackRight">
                <div class="content">
                    <div class="strip">
                        <img src={strips.src} alt="DYSOON.CLUB GO GO GOOOO!!!!!" margin="0" />
                        <img src={strips.src} alt="DYSOON.CLUB GO GO GOOOO!!!!!" margin="0" />
                    </div>
                </div>
            </div>
        </div>
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
            width: 25%;
        }

        .full * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            width: 100%;
        }
        button {
            background-color: transparent;
            border: none;
            cursor: pointer;
            transform: 1s;
        }
        button:hover {
            filter: contrast(2);
        }
    </style>
{:else}
    <img src={logoImage.src} alt="DYSOON.CLUB GO GO GOOOO!!!!!" />
{/if}
