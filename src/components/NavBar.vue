
<template>
    <div class="nav-container">
        <img :src="FFLogo" @click.prevent="handleNavSelect('main')" />
        <div class="nav-items-container">
            <p @click.prevent="handleNavSelect('main')" :class="currentPage == 'main' ? 'highlight' : ''"
                class="nav-item-default">
                Main<span v-if="currentPage == 'main'">*</span>
            </p>
            <p @click.prevent="handleNavSelect('manifesto')" :class="currentPage == 'manifesto' ? 'highlight' : ''"
                class="nav-item-default">
                Manifesto<span v-if="currentPage == 'manifesto'">*</span>
            </p>
            <p @click.prevent="handleApply" class="nav-item-default">Apply</p>
        </div>
    </div>
</template>

<script setup>
import FFLogo from "../assets/FeedbackFridayLogo.svg";
import { ref } from "vue";

const emit = defineEmits(['navSelect'])

const props = defineProps({
    currentPage: {
        type: String,
        required: true,
    }
});

const navSelect = ref("main");

function handleNavSelect(page) {
    navSelect.value = page;

    emit("navSelect", navSelect.value);
};

function handleApply() {
    window.open("https://discord.gg/nrMVZHkg", "_blank");
};

</script>

<style scoped>

@keyframes slideDown {
        from {
            transform: translateY(-10px);
            opacity: 0;
        }

        to {
            transform: translateY(0px);
            opacity: 1;
        }
    }

@media screen and (max-width: 540px) {

    .nav-container {
        padding: 0;
        margin: 1.5rem;
        display: grid;
        grid-template-columns: 1fr 1fr;
        align-items: center;

        justify-content: space-between;

        animation: slideDown 1s ease-in-out;
    }

    .nav-container>img {
        margin: 0;
        height: 24px;
        width: 36px;
        cursor: pointer;
    }

    .nav-items-container {
        display: flex;
        justify-content: space-between;
    }

    .nav-items-container>p {
        margin: 0;
        font: var(--sys-type-body-sm);
    }

    .nav-item-default {
        cursor: pointer;
        color: var(--sys-palette-fg-secondary);
    }

    .highlight {
        color: var(--sys-palette-fg-primary);
        font-weight: 500;
    }
}

@media screen and (min-width: 541px) and (max-width: 1279px) {
    .nav-container {
        padding: 0;
        margin: 1.5rem;
        display: grid;
        grid-template-columns: 1fr 1fr;
        align-items: center;
        justify-content: space-between;

        animation: slideDown 1s ease-in-out;
    }

    .nav-container>img {
        margin: 0;
        height: 24px;
        width: 36px;
        cursor: pointer;
    }

    .nav-items-container {
        display: flex;
        gap: 2rem;
        justify-content: flex-end;
    }

    .nav-items-container>p {
        margin: 0;
        font: var(--sys-type-body-sm);
    }

    .nav-item-default {
        cursor: pointer;
        color: var(--sys-palette-fg-secondary);
    }

    .highlight {
        color: var(--sys-palette-fg-primary);
        font-weight: 500;
    }
}

@media screen and (min-width: 1280px) {
    .nav-container {
        padding: 0;
        margin: 2rem;
        display: grid;
        grid-template-columns: 1fr 1fr;
        align-items: center;
        justify-content: space-between;

        animation: slideDown 1s ease-in-out;
    }

    .nav-container>img {
        margin: 0;
        height: 24px;
        width: 36px;
        cursor: pointer;
    }

    .nav-items-container {
        display: flex;
        gap: 2rem;
        justify-content: flex-end;
    }

    .nav-items-container>p {
        margin: 0;
        font: var(--sys-type-body-md);
    }

    .nav-item-default {
        cursor: pointer;
        color: var(--sys-palette-fg-secondary);
    }

    .highlight {
        color: var(--sys-palette-fg-primary);
        font-weight: 500;
    }
}
</style>