
<template>
    <div class="main-container">
        <NavBar @nav-select="checkInfo" currentPage="main" />
        <div class="main-content">
            <h4 class="body-copy" v-html="mainCopy.explainer"></h4>
            <Button :cta="mainCopy.cta" link="https://discord.gg/nrMVZHkg" />
        </div>

        <div class="values-container">
            <div v-for="value in mainCopy.values" class="values-content">
                <h5 v-html="value.title"></h5>
                <p v-html="value.copy"></p>
            </div>
        </div>

        <div class="desktop-container">
            <div class="desktop-main-content">
                <h4 class="body-copy" v-html="mainCopy.explainer"></h4>
                <Button :cta="mainCopy.cta" />
            </div>

            <div class="spacer"></div>

            <div class="desktop-values-content">
                <div v-for="value in mainCopy.values" class="values-content">
                    <h5 v-html="value.title"></h5>
                    <p v-html="value.copy"></p>
                </div>
            </div>
        </div>

    </div>
</template>

<script setup>
import NavBar from '../components/NavBar.vue';
import Button from '../components/Button.vue';

const emit = defineEmits(['navSelect']);

console.log("this loaded");

const checkInfo = (info) => {
    console.log(info);

    emit('navSelect', info);
}

const mainCopy = {
    explainer: "Feedback Friday is a community platform where designers are encouraged to critique, provide feedback and share their experience and knowledge for the betterment of themselves and the design&nbsp;community.",
    cta: "Apply now →",
    values: [
        {
            title: "Confidential",
            copy: "All shared work, conversation and critique is&nbsp;confidential.",
        },
        {
            title: "Professionalism",
            copy: "Through professionalism we create a culture of&nbsp;trust.",
        },
        {
            title: "Trust",
            copy: "With trust, we commit ourselves to the growth and success of each other—and in doing so, we are aligned with peers who are equally committed to us in&nbsp;return.",
        }
    ],
}
</script>

<style scoped>

@keyframes slideDown {
    from {
        opacity: 0;
    }

    50% {
        transform: translateY(-10px);
        opacity: 0;
    }

    to {
        transform: translateY(0px);
        opacity: 1;
    }
}

@media screen and (max-width: 540px) {


    .desktop-container {
        display: none;
    }

    .main-container {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        height: 100vh;
    }

    .main-content {
        margin: 1.5rem;
        justify-content: center;
        animation: slideDown 1.25s ease-in-out;
    }

    .body-copy {
        font: var(--sys-type-body-md);
        color: var(--sys-palette-fg-primary);
        margin: 0;
        padding-bottom: .75rem;
    }

    .values-container {
        display: flex;
        flex-direction: column;
        gap: 2rem;
        margin: 1.5rem;
        border-top: 1px var(--sys-palette-sep-medium) solid;
        padding-top: 1rem;
        animation: slideDown 1.5s ease-in-out;
    }

    .values-content {
        display: grid;
        grid-template-columns: 1fr 1fr;
        margin: 0;
    }

    .values-content>h5 {
        margin: 0;
        font: var(--sys-type-label-xs);
        color: var(--sys-palette-fg-primary);
    }

    .values-content>p {
        margin: 0;
        font: var(--sys-type-body-xs);
        color: var(--sys-palette-fg-secondary);
    }

}

@media screen and (min-width: 541px) and (max-width: 1279px) {

    .desktop-container {
        display: none;
    }

    .main-container {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        height: 100vh;

        animation: slideDown 1.25s ease-in-out;
    }

    .main-content {
        margin: 1.5rem;
        justify-content: center;
    }

    .body-copy {
        width: 75%;
        font: var(--sys-type-body-md);
        font-size: 1.5rem;
        color: var(--sys-palette-fg-primary);
    }

    .values-container {
        display: flex;
        flex-direction: column;
        gap: 2rem;
        margin: 1.5rem;
        border-top: 1px var(--sys-palette-sep-medium) solid;
        padding-top: 1rem;
    }

    .values-content {
        display: grid;
        grid-template-columns: 1fr 1fr;
        margin: 0;
    }

    .values-content>h5 {
        margin: 0;
        font: var(--sys-type-label-sm);
        font-size: 1rem;
        color: var(--sys-palette-fg-primary);
    }

    .values-content>p {
        margin: 0;
        font: var(--sys-type-body-sm);
        font-size: 1rem;
        color: var(--sys-palette-fg-secondary);
    }

}


@media screen and (min-width: 1280px) {
    .main-container {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        height: 100vh;

    }

    .main-content {
        display: none;
    }

    .desktop-container {
        height: 50vh;
        display: grid;
        grid-template-columns: 2fr 1fr 1fr;
        border-top: 1px var(--sys-palette-sep-medium) solid;
        margin: 2rem;

        animation: slideDown 1.25s ease-in-out;
    }

    .desktop-main-content {
        padding-top: 1.5rem;
        margin: 0;
        display: flex;
        flex-direction: column;
        justify-content: space-between;

        animation: slideDown 1.5s ease-in-out;
    }

    .desktop-values-content {
        display: flex;
        flex-direction: column;
        gap: 2rem;
        padding-top: 1.8rem;
        
        animation: slideDown 1.5s ease-in-out;
    }

    .body-copy {
        margin: 0;
        font: var(--sys-type-body-md);
        font-size: 1.5rem;
        color: var(--sys-palette-fg-primary);
    }

    .values-container {
        display: none;
        flex-direction: column;
        gap: 2.5rem;
        margin: 1.5rem;
        border-top: 1px var(--sys-palette-sep-medium) solid;
        padding-top: 1.5rem;
    }

    .values-content {
        display: flex;
        flex-direction: column;
        gap: .25rem;
        margin: 0;
    }

    .values-content>h5 {
        margin: 0;
        font: var(--sys-type-label-md);
        font-weight: 500;
        font-size: 1rem;
        color: var(--sys-palette-fg-primary);
    }

    .values-content>p {
        margin: 0;
        font: var(--sys-type-body-md);
        font-size: 1rem;
        color: var(--sys-palette-fg-secondary);
    }

}
</style>