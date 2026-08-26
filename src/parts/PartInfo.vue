<template>
    <div>
        <h1>{{ part.title }}</h1>
        <div>
            {{ part.description }}
        </div>
    </div>
</template>

<script>
import parts from '../data/parts';

export default {
    name: 'PartInfo',
    props: {
        partType: {type: String, required: true},
        id: {type: String, validator(value) {return Number.isInteger(+value);}, required: true}
    },
    computed: {
        part(){
            const {partType, id} = this
            return parts[partType].find(part => part.id === +id);
        }
    },
}
</script>