<template>
  <div id="app">
    <main :class="filterStatus && 'with-filter'">
      <job-filter
        v-if="filterStatus"
        :filters="filters"
        @removeFilter="removeFilterHandler"
        @clearAll="filters = []"
      />
      <job-offer
        v-for="job in filterJobs"
        :key="job.id"
        :job="job"
        @selectFilter="filterHandler"
        />
    </main>
  </div>
</template>

<script>
/* eslint-disable max-len */
import JobOffer from './components/JobOffer.vue';
import JobFilter from './components/JobFilter.vue';
import data from './assets/data.json';

export default {
  name: 'App',
  components: {
    JobOffer,
    JobFilter,
  },
  computed: {
    filterStatus() {
      return this.filters.length > 0;
    },
    filterJobs() {
      const filteredJobs = this.jobs.filter(({
        role, level, tools, languages,
      }) => {
        const tags = [role, level];
        if (tools) tags.push(...tools);
        if (languages) tags.push(...languages);
        return this.filters.every((filter) => tags.includes(filter));
      });
      return filteredJobs;
    },
  },
  data() {
    return {
      filters: [],
      jobs: [],
    };
  },
  mounted() {
    this.jobs = data;
  },
  methods: {
    filterHandler(val) {
      return !this.filters.includes(val) && this.filters.push(val);
    },
    removeFilterHandler(val) {
      const itemIndex = this.filters.findIndex((filter) => filter === val);
      this.filters.splice(itemIndex, 1);
    },
  },
};
</script>

<style>
body {
  margin: 0;
  padding: 0;
  font-family: "Spartan", sans-serif;
  font-size: 15px;
}

/* stylelint-disable selector-max-id */
#app {
  margin: 0;
  padding: 0;
  min-height: 100vh;
}
/* stylelint-enable selector-max-id */

main {
  padding-top: 212px;
  background: linear-gradient(to bottom, hsl(180, 29%, 50%) 0%, hsl(180, 29%, 50%) 156px, hsl(180, 52%, 96%) 156px, hsl(180, 52%, 96%) 100%);
  transition: padding-top 0.5s ease;
}

.with-filter {
  padding-top: 296px;
}

main::after {
  position: absolute;
  content: "";
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  background-image: url("./assets/images/bg-header-mobile.svg");
  background-repeat: repeat-x;
  background-position: left top;
}

@media screen and (min-width: 1440px) {
  main {
    padding-top: 232px;
  }

  main::after {
    background-image: url("./assets/images/bg-header-desktop.svg");
  }
}
</style>
