<template>
    <v-app>
        <v-main fluid>
            <Header :rail="rail" />
            <div style="display: flex; flex-direction: row; justify-content: space-between;">
                <HeaderToolbar :rail="rail" :class="{ 'toolbar-expanded': !rail, 'toolbar-collapsed': rail }" />
                <EditPanel />
            </div>
            <Footer />
        </v-main>
    </v-app>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import Header from '@/components/Header.vue';
import HeaderToolbar from '@/components/HeaderToolbar.vue';
import EditPanel from '@/components/EditPanel.vue';
import Footer from '@/components/Footer.vue';

@Options({
    name: 'FormEdit',
    components: {
        Header,
        HeaderToolbar,
        EditPanel,
        Footer
    }
})
export default class FormEdit extends Vue {
}
</script>

<style></style>