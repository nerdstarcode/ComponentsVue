<template>
    <div class="viewer">
        <div class="shadow"></div>
        <div class="bowl">
            <div class="liquid">
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'ColorfulGlowingLikidBowl',
    }
</script>

<style>
    :root
    {
        --viewer_min_height: 100vh;
        --viewr_background: #121212;

        --bowl_width__height: 300px; 
        --bowl_background: rgba(255,255,255,0.1);
        --bowl_border: 8px solid transparent;
        --bowl-before_width: 40%;
        --bowl-before_height: 30px;
        --bowl-before_top: -10px;
        --bowl-before_border: 15px solid #444;
        --bowl-before_box_shadow: 0 10px #222;
        --bowl-after_height: 80px;
        --bowl-after_background: rgba(255,255,255,0.05);

        --liquid_background: #41c1fb;
        --liquid_fill: calc(var(--bowl_width__height)/2);
        --liquid-after_background: #1fa4e0;
        
        --shadow_background: rgba(0,0,0,0.5);

        --rotate-recipe: 20deg;
        --rotate-liquid: calc(var(--rotate-recipe)*-1)
    }
</style>
<style scoped> 
    *
    {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }
    .viewer
    {
        display: flex;
        justify-content: center;
        align-items: center;
        min-height: var(--viewer_min_height);
        background: var(--viewr_background);
    }
    .bowl
    {
        position: relative;
        width: var(--bowl_width__height);
        height: var(--bowl_width__height);
        background: var(--bowl_background);
        border-radius: 50%;
        transform: rotate(var(--rotate-recipe));
    }
    .bowl::before
    {
        content: '';
        position: absolute;
        top: var(--bowl-before_top);
        left: 50%;
        transform: translate(-50%);
        width: var(--bowl-before_width);
        height: var(--bowl-before_height);
        border: var( --bowl-before_border);
        border-radius: 50%;
        box-shadow: var(--bowl-before_box_shadow);

    }
    .bowl::after
    {
        content: '';
        position: absolute;
        top: 40%;
        left: 50%;
        transform-origin: bottom center;
        transform: translate(-50%,-50%) rotate(var(--rotate-liquid));
        border-radius: 50%;
        width: calc(var(--bowl_width__height)/2);
        height: var(--bowl-after_height);
        background: var(--bowl-after_background);
    }
    .liquid
    {
        position: absolute;
        inset: var(--liquid_fill) 10px 10px 10px;
        background: var(--liquid_background);
        border-bottom-left-radius: var(--liquid_fill);
        border-bottom-right-radius: var(--liquid_fill);
        filter: drop-shadow(0 0 80px var(--liquid_background));
        transform-origin: top center;
        transform: rotate(var(--rotate-liquid));
    }
    .liquid::before
    {
        content:'';
        position: absolute;
        top: -10px;
        width: 100%;
        height: 20px;
        background: var(--liquid-after_background);
        border-radius: 50%;
        filter: drop-shadow(0 0 80px var(--liquid_background));
    }
    .shadow
    {
        position: absolute;
        top: calc(50% + 150px);
        left: 50%;
        transform: translate(-50%,-50%);
        width: var(--bowl_width__height);
        height: 30px;
        background: var(--shadow_background);
        border-radius: 50%;
    }
</style>