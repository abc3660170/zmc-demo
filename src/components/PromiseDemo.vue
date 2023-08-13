<script setup lang="ts">
import { Ref, ref } from 'vue';

    const result: Ref<any> = ref('处理中...')
    const requestA = (callback: Function) => {
        setTimeout(() => {
            callback(null, 10);
        }, 2000);
    }

    new Promise((resolve, reject) => {
        requestA((error: Error, data: any) => {
            if(error){
                reject(error)
            } else {
                resolve(data)
            }
            // xxxxxxxxxxxxxsxx
        })
    }).then(data => {
        result.value = data;
    }, error => {
        result.value = error;
    })

</script>
<template>
    <div>{{result}}</div>
</template>