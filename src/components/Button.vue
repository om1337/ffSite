
<template>
    <button @click.prevent="handleLink" class="button" target="_blank">
        {{ cta }}
    </button>
</template>

<script setup>

const props = defineProps({
    cta: {
        type: String,
        required: true,
        default: 'Apply now →'
    },
    link: {
        type: String,
        default: 'https://discord.gg/nrMVZHkg'
    }
});

function handleLink() {
    window.open(props.link, '_blank');
}
</script>

<style scoped>

@media screen and (max-width: 1279px) {
    .button {
        outline: none;
        border: none;
        color: var(--sys-palette-fg-primary);
        background: none;

        padding: .625rem 1rem;
        border-radius: 100px;
        border: 1px solid var(--sep-medium, #DADADD);
        cursor: pointer;
    }
}

@media screen and (min-width: 1280px) {
    .button {
        outline: none;
        border: none;
        background: none;

        font: var(--sys-type-title-md);
        color: var(--sys-palette-fg-primary);

        cursor: pointer;

        display: flex;
        border-radius: 100px;
    }
}

</style>