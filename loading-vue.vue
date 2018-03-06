<template>
    <div>
        <div v-if="'l1'===activar" class="spinnerL1"></div>
        <div v-if="'l2'===activar" class="spinnerL2">
            <div class="double-bounce1"></div>
            <div class="double-bounce2"></div>
        </div>
        <div v-if="'l3'===activar" class="spinnerL3">
            <div class="rect1"></div>
            <div class="rect2"></div>
            <div class="rect3"></div>
            <div class="rect4"></div>
            <div class="rect5"></div>
        </div>
        <div v-if="'l4'===activar" class="spinnerL4">
            <div class="bounce1"></div>
            <div class="bounce2"></div>
            <div class="bounce3"></div>
        </div>
        <div v-if="'l5'===activar" class="sk-circle">
            <div class="sk-circle1 sk-child"></div>
            <div class="sk-circle2 sk-child"></div>
            <div class="sk-circle3 sk-child"></div>
            <div class="sk-circle4 sk-child"></div>
            <div class="sk-circle5 sk-child"></div>
            <div class="sk-circle6 sk-child"></div>
            <div class="sk-circle7 sk-child"></div>
            <div class="sk-circle8 sk-child"></div>
            <div class="sk-circle9 sk-child"></div>
            <div class="sk-circle10 sk-child"></div>
            <div class="sk-circle11 sk-child"></div>
            <div class="sk-circle12 sk-child"></div>
        </div>
    </div>
</template>
<script>
    module.exports = {
        props: ["type"],
        data: function() {
            return {
                activar: null
            }
        },
        created: function() {
            this.activar = this.type.toLowerCase();
        }
    };
</script>
<style scoped>
    /* ---- l1 ---- */
    .spinnerL1 {
        width: 40px;
        height: 40px;
        background-color: #333;
        margin: 100px auto;
        -webkit-animation: sk-rotateplane 1.2s infinite ease-in-out;
        animation: sk-rotateplane 1.2s infinite ease-in-out;
    }

    @-webkit-keyframes sk-rotateplane {
        0% { -webkit-transform: perspective(120px) }
        50% { -webkit-transform: perspective(120px) rotateY(180deg) }
        100% { -webkit-transform: perspective(120px) rotateY(180deg)  rotateX(180deg) }
    }

    @keyframes sk-rotateplane {
        0% { 
            transform: perspective(120px) rotateX(0deg) rotateY(0deg);
            -webkit-transform: perspective(120px) rotateX(0deg) rotateY(0deg) 
        } 50% { 
            transform: perspective(120px) rotateX(-180.1deg) rotateY(0deg);
            -webkit-transform: perspective(120px) rotateX(-180.1deg) rotateY(0deg) 
        } 100% { 
            transform: perspective(120px) rotateX(-180deg) rotateY(-179.9deg);
            -webkit-transform: perspective(120px) rotateX(-180deg) rotateY(-179.9deg);
        }
    }
    /* ---- l2 ---- */
    .spinnerL2 {
        width: 40px;
        height: 40px;

        position: relative;
        margin: 100px auto;
    }

    .double-bounce1, .double-bounce2 {
        width: 100%;
        height: 100%;
        border-radius: 50%;
        background-color: #333;
        opacity: 0.6;
        position: absolute;
        top: 0;
        left: 0;
        
        -webkit-animation: sk-bounce 2.0s infinite ease-in-out;
        animation: sk-bounce 2.0s infinite ease-in-out;
    }

    .double-bounce2 {
        -webkit-animation-delay: -1.0s;
        animation-delay: -1.0s;
    }

    @-webkit-keyframes sk-bounce {
        0%, 100% { -webkit-transform: scale(0.0) }
        50% { -webkit-transform: scale(1.0) }
    }

    @keyframes sk-bounce {
        0%, 100% { 
            transform: scale(0.0);
            -webkit-transform: scale(0.0);
        } 50% { 
            transform: scale(1.0);
            -webkit-transform: scale(1.0);
        }
    }
    /* ---- l3 ---- */
    .spinnerL3 {
        margin: 100px auto;
        width: 50px;
        height: 40px;
        text-align: center;
        font-size: 10px;
    }

    .spinnerL3 > div {
        background-color: #333;
        height: 100%;
        width: 6px;
        display: inline-block;
        -webkit-animation: sk-stretchdelay 1.2s infinite ease-in-out;
        animation: sk-stretchdelay 1.2s infinite ease-in-out;
    }

    .spinnerL3 .rect2 {
        -webkit-animation-delay: -1.1s;
        animation-delay: -1.1s;
    }

    .spinnerL3 .rect3 {
        -webkit-animation-delay: -1.0s;
        animation-delay: -1.0s;
    }

    .spinnerL3 .rect4 {
        -webkit-animation-delay: -0.9s;
        animation-delay: -0.9s;
    }

    .spinnerL3 .rect5 {
        -webkit-animation-delay: -0.8s;
        animation-delay: -0.8s;
    }

    @-webkit-keyframes sk-stretchdelay {
        0%, 40%, 100% { -webkit-transform: scaleY(0.4) }  
        20% { -webkit-transform: scaleY(1.0) }
    }

    @keyframes sk-stretchdelay {
        0%, 40%, 100% { 
            transform: scaleY(0.4);
            -webkit-transform: scaleY(0.4);
        }  20% { 
            transform: scaleY(1.0);
            -webkit-transform: scaleY(1.0);
        }
    }
    /* ---- l4 ---- */
    .spinnerL4 {
        margin: 100px auto 0;
        width: 70px;
        text-align: center;
    }

    .spinnerL4 > div {
        width: 18px;
        height: 18px;
        background-color: #333;
        border-radius: 100%;
        display: inline-block;
        -webkit-animation: sk-bouncedelay 1.4s infinite ease-in-out both;
        animation: sk-bouncedelay 1.4s infinite ease-in-out both;
    }

    .spinnerL4 .bounce1 {
        -webkit-animation-delay: -0.32s;
        animation-delay: -0.32s;
    }

    .spinnerL4 .bounce2 {
        -webkit-animation-delay: -0.16s;
        animation-delay: -0.16s;
    }

    @-webkit-keyframes sk-bouncedelay {
        0%, 80%, 100% { -webkit-transform: scale(0) }
        40% { -webkit-transform: scale(1.0) }
    }

    @keyframes sk-bouncedelay {
        0%, 80%, 100% { 
            -webkit-transform: scale(0);
            transform: scale(0);
        } 40% { 
            -webkit-transform: scale(1.0);
            transform: scale(1.0);
        }
    }
    /* ---- l5 ---- */
    .sk-circle {
        margin: 100px auto;
        width: 40px;
        height: 40px;
        position: relative;
    }
    .sk-circle .sk-child {
        width: 100%;
        height: 100%;
        position: absolute;
        left: 0;
        top: 0;
    }
    .sk-circle .sk-child:before {
        content: '';
        display: block;
        margin: 0 auto;
        width: 15%;
        height: 15%;
        background-color: #333;
        border-radius: 100%;
        -webkit-animation: sk-circleBounceDelay 1.2s infinite ease-in-out both;
        animation: sk-circleBounceDelay 1.2s infinite ease-in-out both;
    }
    .sk-circle .sk-circle2 {
        -webkit-transform: rotate(30deg);
        -ms-transform: rotate(30deg);
        transform: rotate(30deg); 
    }
    .sk-circle .sk-circle3 {
        -webkit-transform: rotate(60deg);
        -ms-transform: rotate(60deg);
        transform: rotate(60deg); 
    }
    .sk-circle .sk-circle4 {
        -webkit-transform: rotate(90deg);
        -ms-transform: rotate(90deg);
        transform: rotate(90deg); 
    }
    .sk-circle .sk-circle5 {
        -webkit-transform: rotate(120deg);
        -ms-transform: rotate(120deg);
        transform: rotate(120deg); 
    }
    .sk-circle .sk-circle6 {
        -webkit-transform: rotate(150deg);
        -ms-transform: rotate(150deg);
        transform: rotate(150deg); 
    }
    .sk-circle .sk-circle7 {
        -webkit-transform: rotate(180deg);
        -ms-transform: rotate(180deg);
        transform: rotate(180deg); 
    }
    .sk-circle .sk-circle8 {
        -webkit-transform: rotate(210deg);
        -ms-transform: rotate(210deg);
        transform: rotate(210deg); 
    }
    .sk-circle .sk-circle9 {
        -webkit-transform: rotate(240deg);
        -ms-transform: rotate(240deg);
        transform: rotate(240deg); 
    }
    .sk-circle .sk-circle10 {
        -webkit-transform: rotate(270deg);
        -ms-transform: rotate(270deg);
        transform: rotate(270deg); 
    }
    .sk-circle .sk-circle11 {
        -webkit-transform: rotate(300deg);
        -ms-transform: rotate(300deg);
        transform: rotate(300deg); 
    }
    .sk-circle .sk-circle12 {
        -webkit-transform: rotate(330deg);
        -ms-transform: rotate(330deg);
        transform: rotate(330deg); 
    }
    .sk-circle .sk-circle2:before {
        -webkit-animation-delay: -1.1s;
        animation-delay: -1.1s; 
    }
    .sk-circle .sk-circle3:before {
        -webkit-animation-delay: -1s;
        animation-delay: -1s; 
    }
    .sk-circle .sk-circle4:before {
        -webkit-animation-delay: -0.9s;
        animation-delay: -0.9s; 
    }
    .sk-circle .sk-circle5:before {
        -webkit-animation-delay: -0.8s;
        animation-delay: -0.8s; 
    }
    .sk-circle .sk-circle6:before {
        -webkit-animation-delay: -0.7s;
        animation-delay: -0.7s; 
    }
    .sk-circle .sk-circle7:before {
        -webkit-animation-delay: -0.6s;
        animation-delay: -0.6s; 
    }
    .sk-circle .sk-circle8:before {
        -webkit-animation-delay: -0.5s;
        animation-delay: -0.5s; 
    }
    .sk-circle .sk-circle9:before {
        -webkit-animation-delay: -0.4s;
        animation-delay: -0.4s; 
    }
    .sk-circle .sk-circle10:before {
        -webkit-animation-delay: -0.3s;
        animation-delay: -0.3s; 
    }
    .sk-circle .sk-circle11:before {
        -webkit-animation-delay: -0.2s;
        animation-delay: -0.2s; 
    }
    .sk-circle .sk-circle12:before {
        -webkit-animation-delay: -0.1s;
        animation-delay: -0.1s; 
    }
    @-webkit-keyframes sk-circleBounceDelay {
        0%, 80%, 100% {
            -webkit-transform: scale(0);
            transform: scale(0);
        } 40% {
            -webkit-transform: scale(1);
            transform: scale(1);
        }
    }

    @keyframes sk-circleBounceDelay {
        0%, 80%, 100% {
            -webkit-transform: scale(0);
            transform: scale(0);
        } 40% {
            -webkit-transform: scale(1);
            transform: scale(1);
        }
    }
</style>
