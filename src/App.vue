<template>
  <div id="app">
    <main :class="filterStatus && 'with-filter'">
      <job-filter v-show="filterStatus" />
      <job-offer v-for="job in filterJobs" :key="job.id" :job="job" />
    </main>
  </div>
</template>

<script>
import JobOffer from './components/JobOffer.vue';
import JobFilter from './components/JobFilter.vue';

export default {
  name: 'App',
  components: {
    JobOffer,
    JobFilter,
  },
  computed: {
    filterStatus() {
      return this.filters.length >= 0;
    },
    filterJobs() {
      return this.jobs;
    },
  },
  data() {
    return {
      filters: [],
      jobs: [
        {
          id: 1,
          company: 'Photosnap',
          logo: 'photosnap.svg',
          new: true,
          featured: true,
          position: 'Senior Frontend Developer',
          role: 'Frontend',
          level: 'Senior',
          postedAt: '1d ago',
          contract: 'Full Time',
          location: 'USA Only',
          languages: ['HTML', 'CSS', 'JavaScript'],
        },
        {
          id: 2,
          company: 'Manage',
          logo: 'manage.svg',
          new: true,
          featured: true,
          position: 'Fullstack Developer',
          role: 'Fullstack',
          level: 'Midweight',
          postedAt: '1d ago',
          contract: 'Part Time',
          location: 'Remote',
          languages: ['Python'],
          tools: ['React'],
        },
        {
          id: 3,
          company: 'Account',
          logo: 'account.svg',
          new: true,
          featured: false,
          position: 'Junior Frontend Developer',
          role: 'Frontend',
          level: 'Junior',
          postedAt: '2d ago',
          contract: 'Part Time',
          location: 'USA Only',
          languages: ['JavaScript'],
          tools: ['React', 'Sass'],
        },
        {
          id: 4,
          company: 'MyHome',
          logo: 'myhome.svg',
          new: false,
          featured: false,
          position: 'Junior Frontend Developer',
          role: 'Frontend',
          level: 'Junior',
          postedAt: '5d ago',
          contract: 'Contract',
          location: 'USA Only',
          languages: ['CSS', 'JavaScript'],
        },
        {
          id: 5,
          company: 'Loop Studios',
          logo: 'loop-studios.svg',
          new: false,
          featured: false,
          position: 'Software Engineer',
          role: 'FullStack',
          level: 'Midweight',
          postedAt: '1w ago',
          contract: 'Full Time',
          location: 'Worldwide',
          languages: ['JavaScript'],
          tools: ['Ruby', 'Sass'],
        },
        {
          id: 6,
          company: 'FaceIt',
          logo: 'faceit.svg',
          new: false,
          featured: false,
          position: 'Junior Backend Developer',
          role: 'Backend',
          level: 'Junior',
          postedAt: '2w ago',
          contract: 'Full Time',
          location: 'UK Only',
          tools: ['RoR'],
        },
        {
          id: 7,
          company: 'Shortly',
          logo: 'shortly.svg',
          new: false,
          featured: false,
          position: 'Junior Developer',
          role: 'Frontend',
          level: 'Junior',
          postedAt: '2w ago',
          contract: 'Full Time',
          location: 'Worldwide',
          languages: ['HTML', 'JavaScript'],
          tools: ['Sass'],
        },
        {
          id: 8,
          company: 'Insure',
          logo: 'insure.svg',
          new: false,
          featured: false,
          position: 'Junior Frontend Developer',
          role: 'Frontend',
          level: 'Junior',
          postedAt: '2w ago',
          contract: 'Full Time',
          location: 'USA Only',
          languages: ['JavaScript'],
          tools: ['Vue, Sass'],
        },
        {
          id: 9,
          company: 'Eyecam Co.',
          logo: 'eyecam-co.svg',
          new: false,
          featured: false,
          position: 'Full Stack Engineer',
          role: 'Fullstack',
          level: 'Midweight',
          postedAt: '3w ago',
          contract: 'Full Time',
          location: 'Worldwide',
          languages: ['JavaScript', 'Python'],
          tools: ['Django'],
        },
        {
          id: 10,
          company: 'The Air Filter Company',
          logo: 'the-air-filter-company.svg',
          new: false,
          featured: false,
          position: 'Front-end Dev',
          role: 'Frontend',
          level: 'Junior',
          postedAt: '1mo ago',
          contract: 'Part Time',
          location: 'Worldwide',
          languages: ['JavaScript'],
          tools: ['React', 'Sass'],
        },
      ],
    };
  },
};
</script>

<style>
body {
  margin: 0;
  padding: 0;
  font-family: 'Spartan', sans-serif;
  font-size: 15px;

}

#app {
  margin: 0;
  padding: 0;
  min-height: 100vh;
}

main {
  padding-top: 212px;
  background: linear-gradient(to bottom, hsl(180, 29%, 50%) 0%,
    hsl(180, 29%, 50%) 156px,hsl(180, 52%, 96%) 156px,hsl(180, 52%, 96%) 100%);
  transition: padding-top 0.5s ease;
}

.with-filter {
  padding-top: 296px;
}

main::after {
  position: absolute;
  content: '';
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  background-image: url('./assets/images/bg-header-mobile.svg');
  background-repeat: repeat-x;
  background-position: left top;
}

@media screen and (min-width: 1440px) {
  main {
    padding-top: 232px;
  }

  main::after {
    background-image: url('./assets/images/bg-header-desktop.svg');
  }
}
</style>
