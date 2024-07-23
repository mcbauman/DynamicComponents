<script setup>
import json from '../JSON.json'
import ComponentA from './components/ComponentA.vue';
import ComponentB from './components/ComponentB.vue';
import Number from './components/Number.vue'
import Text from './components/Text.vue';
import Select from './components/Select.vue';
import { ref } from 'vue';

const switchVar=ref("ComponentA")

const tabs={ComponentA, ComponentB}
const inputFields={number:Number, text:Text, select:Select}
const data=ref(json)
</script>

<template>
  <header>
    <select v-model="switchVar" >
      <option v-for="(_,term) in tabs" :value="term">{{term}}</option>
    </select>
  </header>
  <main>
    <hr>
    <component :is="tabs[switchVar]"></component>
    <pre>{{ data }}</pre>
    <component v-for="item in data.Werte" :is="inputFields[item.type]" :value="item"></component>
  </main>
</template>
