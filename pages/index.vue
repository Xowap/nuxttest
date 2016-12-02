<template>
    <div>
        <h1>Nuxt Async Test</h1>

        <div v-if="output">
            <h2>He's what HTTP Bin says (outside component)</h2>

            <pre>{{ output }}</pre>
        </div>

        <http-bin></http-bin>
    </div>
</template>

<script type="text/ecmascript-6">
    import HttpBin from '~components/HttpBin.vue';
    import axios from 'axios';

    export default {
        components: {
            HttpBin,
        },
        data() {
            return axios.get('https://httpbin.org/get').then((res) => {
                return {
                    output: res.data,
                }
            });
        },
    };
</script>
