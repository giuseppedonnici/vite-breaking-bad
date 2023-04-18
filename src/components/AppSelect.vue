<script>
import { store } from '../store';

export default {
    name: "AppSelect",
    emits: ["filter"],
    data() {
        return {
            store,
            achetypes: ["Alien", "Ally of Justice", "Ancient Gear"]
        }
    }
}
</script>

<template>
    <h3>Archtype:</h3>
    <select class="form-select w-25 mb-4" name="archetype" id="archetype" v-model="store.selectedArchetype" @change="$emit('filter')">
        <option value="">All</option>
        <option :value="archetype" v-for="archetype in achetypes">{{ archetype }}</option>
    </select>
</template>