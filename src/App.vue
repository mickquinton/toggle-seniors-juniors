<template>
  <div class="wrap-toggle">
    
    <!-- Senior toggle -->
    <div class="button" v-if="isSenior == false" @click="toggleSenior()">Hide Seniors</div>
    <div class="button-clicked" v-else @click="toggleSenior()">Show Seniors</div>

    <!-- Junior toggle -->
    <div class="button" v-if="isJunior == false" @click="toggleJunior()">Hide Juniors</div>
    <div class="button-clicked" v-else @click="toggleJunior()">Show Juniors</div>
  </div>

  <!-- UX full list -->
  <div v-if="isSenior == false && isJunior == false">
    <div class="wrap-list" v-for="member in uxTeam" :key="member">
      <div>{{ member.name }}:&nbsp;</div>
      <div>{{ member.rank }}</div>
    </div>
  </div>

  <!-- UX senior list -->
  <div v-if="isSenior == false && isJunior == true">
    <div class="wrap-list" v-for="member in uxSeniors" :key="member">
      <div>{{ member.name }}:&nbsp;</div>
      <div>{{ member.rank }}</div>
    </div>
  </div>

  <!-- UX junior list -->
  <div v-if="isSenior == true && isJunior == false">
    <div class="wrap-list" v-for="member in uxJuniors" :key="member">
      <div>{{ member.name }}:&nbsp;</div>
      <div>{{ member.rank }}</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      uxTeam: [
        { name: "Anthony", rank: "Senior" },
        { name: "Kleine", rank: "Senior" },
        { name: "Kiyu", rank: "Senior" },
        { name: "Mick", rank: "Senior" },
        { name: "Michelle", rank: "Junior" },
        { name: "Jarvey", rank: "Junior" }
      ],

      uxSeniors: [
        { name: "Anthony", rank: "Senior" },
        { name: "Kleine", rank: "Senior" },
        { name: "Kiyu", rank: "Senior" },
        { name: "Mick", rank: "Senior" }
      ],

      uxJuniors: [
        { name: "Michelle", rank: "Junior" },
        { name: "Jarvey", rank: "Junior" }
      ],

      isSenior: false,
      isJunior: false
    }
  },

  methods: {
    toggleSenior() {
      this.isSenior = !this.isSenior
    },

    toggleJunior() {
      this.isJunior = !this.isJunior
    }
  }
}
</script>

<style lang="scss">
body {
  font-family: Source Sans pro, sans-serif;
}
.wrap-toggle {
  display: flex;

  .button {
    cursor: pointer;
    background-color: rgba(#ff9200, 1);
    padding: 0.75rem;
    border-radius: 0.5rem;
    margin: 0 1rem 1rem 0;
    font-weight: 600;
    width: 7rem;
    text-align: center;

    &:hover {
      background-color: rgba(#ff9200, 0.9);
    }
  }

  .button-clicked {
    cursor: pointer;
    background-color: rgba(aquamarine, 0.8);
    padding: 0.75rem;
    border-radius: 0.5rem;
    margin: 0 1rem 1rem 0;
    font-weight: 600;
    width: 7rem;
    text-align: center;

    &:hover {
      background-color: rgba(aquamarine, 0.6);
    }
  }
}

.wrap-list {
  display: flex;
  background-color: rgba(#111, 0.1);
  margin: 0 0 1rem 0;
  width: 7rem;
  padding: 0.75rem;
  border-radius: 0.5rem;
}
</style>
