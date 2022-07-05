<script setup>
import Button from '@/components/Button.vue'

const eventForButton = () => {
  alert('You clicked danger button')
}
</script>

<template>
  <h1 class="heading-1">Button</h1>
  <h2 class="heading-2">Disabled</h2>
  <div class="line">
    <Button label="Primary" color="primary" :disabled="true"/>
    <Button label="Secondary" color="second" :disabled="true"/>
  </div>
  <h2 class="heading-2">Colors</h2>
  <div class="line">
    <Button label="Primary" color="primary" />
    <Button label="Secondary" color="second" />
    <Button label="Success" color="success" />
    <Button label="Info" color="info" />
    <Button label="Warning" color="warning" />
    <Button label="Danger" color="danger" />
  </div>
  <h2 class="heading-2">Rounded</h2>
  <div class="line">
    <Button label="Primary" color="primary" :rounded="true"/>
    <Button label="Secondary" color="second" :rounded="true"/>
    <Button label="Success" color="success" :rounded="true"/>
    <Button label="Info" color="info" :rounded="true"/>
    <Button label="Warning" color="warning" :rounded="true"/>
    <Button label="Danger" color="danger" :rounded="true"/>
  </div>
  <h2 class="heading-2">Outlined</h2>
  <div class="line">
    <Button label="Primary" color="primary" :outlined="true"/>
    <Button label="Secondary" color="second" :outlined="true"/>
    <Button label="Success" color="success" :outlined="true"/>
    <Button label="Info" color="info" :outlined="true"/>
    <Button label="Warning" color="warning" :outlined="true"/>
    <Button label="Danger" color="danger" :outlined="true"/>
  </div>
  <h2 class="heading-2">Icon</h2>
  <div class="line">
    <Button color="primary" icon="heart" :outlined="true"/>
    <Button color="second" icon="hand"/>
    <Button color="success" icon="address-book" :outlined="true"/>
    <Button color="info" icon="credit-card"/>
    <Button color="warning" icon="lemon" :outlined="true"/>
    <Button color="danger" icon="hourglass"/>
  </div>
  <h2 class="heading-2">Size</h2>
  <div class="line">
    <Button label="Normal" color="primary" />
    <Button label="Large" color="primary" size="large"/>
  </div>
  <h2 class="heading-2">Event</h2>
  <div class="line">
    <Button label="@click" color="danger" @click="eventForButton"/>
  </div>
</template>

<style lang="scss" scoped>
.line {
  display: flex;
  flex-wrap: wrap;
  margin-bottom: 20px;
}
</style>