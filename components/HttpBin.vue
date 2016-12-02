<template>
    <div>
        <h2>Here's what HTTP Bin says</h2>

        <pre v-if="output">{{ output }}</pre>
        <p v-if="!output">Loading...</p>
    </div>
</template>

<script type="text/ecmascript-6">
    import axios from 'axios';

    export default {
        data() {
            return axios.get('https://httpbin.org/get').then((res) => {
                return {
                    output: res.data,
                }
            });
        },
    };
</script>
