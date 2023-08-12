
<template>
    <div class="manifesto-container">
        <NavBar @nav-select="checkInfo" currentPage="manifesto" />
        <div class="manifesto-content">
            <h5 class="first-quote">
                “A person is not a closed system, they can never be fully self-sufficient. We need each other because we
                cannot make everything&nbsp;ourselves.”
                <br /><br />
                <span class="second-quote">
                    Everything was invented, but it was not done alone, so we should revere the times we are able to fill
                    this complementary role for others, and cherish when others do so for us. It's the words of others that
                    teach us to speak, the expressions of life by other people that teach us how to express&nbsp;ourselves.
                </span>
            </h5>

            <p class="quote-by">
                Frank Chimero
                <br />
                <span class="quote-from">The Shape of Design</span>
            </p>
        </div>
    </div>
</template>

<script setup>
import NavBar from '../components/NavBar.vue';

const emit = defineEmits(['navSelect']);

console.log("this loaded");

const checkInfo = (info) => {
    console.log(info);

    emit('navSelect', info);
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
    .manifesto-content {
        margin: 1.5rem;
        padding: 4rem 0 0 0;
        display: flex;
        flex-direction: column;

        animation: slideDown 1.5s ease-in-out;
    }

    .first-quote {
        font: var(--sys-type-body-md);
        color: var(--sys-palette-fg-primary);
        padding: 0;
        margin: 0;
    }

    .second-quote {
        font: var(--sys-type-body-md);
        color: var(--sys-palette-fg-secondary);
        padding: 0;
        margin: 0;
    }

    .quote-by {
        padding: 1rem 0 0 0;
        font: var(--sys-type-body-sm);
        color: var(--sys-palette-fg-primary);
    }

    .quote-from {
        padding: 0;
        font: var(--sys-type-body-sm);
        color: var(--sys-palette-fg-secondary);
    }

}

@media screen and (min-width: 541px) and (max-width: 1279px) {
    .manifesto-content {
        width: 50%;
        margin: 1.5rem;
        padding: 4rem 0 0 0;
        display: flex;
        flex-direction: column;

        animation: slideDown 1.5s ease-in-out;
    }

    .first-quote {
        font: var(--sys-type-body-md);
        color: var(--sys-palette-fg-primary);
        padding: 0;
        margin: 0;
    }

    .second-quote {
        font: var(--sys-type-body-md);
        color: var(--sys-palette-fg-secondary);
        padding: 0;
        margin: 0;
    }

    .quote-by {
        padding: 1rem 0 0 0;
        font: var(--sys-type-body-sm);
        color: var(--sys-palette-fg-primary);
    }

    .quote-from {
        padding: 0;
        font: var(--sys-type-body-sm);
        color: var(--sys-palette-fg-secondary);
    }
}


@media screen and (min-width: 1280px) {

    .manifesto-container {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        height: 100vh;
    }

    .manifesto-content {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        height: 50vh;
        margin: 0 2rem 1rem 2rem;
        padding: 2rem 0 0 0;
        border-top: 1px var(--sys-palette-sep-medium) solid;

        animation: slideDown 1.25s ease-in-out;
    }

    .first-quote {
        width: 50%;
        font: var(--sys-type-title-sm);
        color: var(--sys-palette-fg-primary);
        padding: 0;
        margin: 0;

        animation: slideDown 1.5s ease-in-out;
    }

    .second-quote {
        width: 50%;
        font: var(--sys-type-title-sm);
        color: var(--sys-palette-fg-secondary);
        padding: 0;
        margin: 0;

        animation: slideDown 1.5s ease-in-out;
    }

    .quote-by {
        padding: 1rem 0 0 0;
        font: var(--sys-type-body-md);
        color: var(--sys-palette-fg-primary);

        animation: slideDown 1.75s ease-in-out;
    }

    .quote-from {
        padding: 0;
        font: var(--sys-type-body-md);
        color: var(--sys-palette-fg-secondary);

        animation: slideDown 1.75s ease-in-out;
    }
}
</style>