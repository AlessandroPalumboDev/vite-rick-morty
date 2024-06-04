<script>
import {store} from '../store.js';
export default {
    name: 'AppCharacterCard',

    data() {
        return {
            store,
        }
    },
}
</script>

<template>
<p>{{ store.prova }}</p>
</template>