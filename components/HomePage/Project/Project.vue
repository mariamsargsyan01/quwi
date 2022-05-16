<template>
    <div class="projectWrapper" @click="changeName(name, id)">
      <div class="info">
        <img :src="logo" width="40px" height="40px" class="logo"/>
        <div class="name">{{name}}</div>
        <div class="active" :class="{ isActive: isActive, isNotActive: !isActive }">{{isActive}}</div>
      </div>
      <div class="timeWrapper">
        <div class="time">
          <div>time this week</div>
          <div>00:00:00</div>
        </div>
        <div class="time">
          <div>this month</div>
          <div>00:00:00</div>
        </div>
        <div class="time">
          <div>total</div>
          <div>00:00:00</div>
        </div>
      </div>
    </div>
</template>

<script>
export default {
    props: {
        id: Number,
        name: String,
        isActive: String,
        logo: String,
        changeName: Function,
    },
}
</script>

<style src="./ProjectStyle.vue"></style>
