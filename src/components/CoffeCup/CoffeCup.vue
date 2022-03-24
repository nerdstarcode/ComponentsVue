<template>
    <div class="viewer">
        <div class="cup">

        </div>
    </div>
</template>

<script>
    export default {
        name: 'CoffeCup',

    }
</script>

<style>
    :root{
        --Cup_width: 150px;
        --Cup_height: 180px;
        --Cup_radius: 5px 5px calc(var(--Cup_width)/10) calc(var(--Cup_width)/10);
        --viewer_min_height: 100vh;
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
        background: #262626;
    }
    .cup
    {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: tanslate(-50%, -50%);
        width: var(--Cup_width);
        height: var(--Cup_height);
        border: 8px solid #fff;
        border-top: 2px solid transparent;
        border-radius: var(--Cup_radius);
        background: url('./img/coffe.png');
        background-repeat: repeat-x;
        animation: animate 10s linear infinite;
    }
    @keyframes animate
    {
        0%
        {
            background-position: 0 200px;
        }
        10%
        {
            background-position: 0 200px;
        }
        40%
        {
            background-position: 1000px 50px;
        }
        80%
        {
            background-position: 2000px 40px;
        }
        100%
        {
            background-position:  2500px 200px;
        }
    }
</style>