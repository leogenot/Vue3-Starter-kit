<template>
    <div class="l-content" ref="content">
        <button-primary
            class="c-project-modal-btn"
            label="Open Modal"
            color="light"
            @click="openModal"
        />
    </div>
</template>

<script>
import { defineComponent, computed, ref } from "vue";
import { useStore } from "vuex";
import { MODAL_COMPONENTS } from "@/constants";

import ButtonPrimary from "@/templates/components/_buttons/ButtonPrimary.vue";

export default defineComponent({
    name: "TheContent",
    components: {
        ButtonPrimary,
    },
    setup() {
        const store = useStore();
        function openModal(data) {
            store.dispatch("modal/open", {
                component: MODAL_COMPONENTS.Project,
                data,
            });
        }

        return {
            openModal,
        };
    },
});
</script>

<style lang="scss">
.l-content {
}
</style>
