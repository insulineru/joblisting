<template>
  <div id="app">
    <header>
      <img src="@/assets/images/bg-header-mobile.svg">
    </header>
    <main>
      <job-offer v-for="job in jobs" :key="job.id" :job="job" />
    </main>
  </div>
</template>

<script>
import JobOffer from './components/JobOffer.vue';

export default {
  name: 'App',
  components: {
    JobOffer,
  },
  data() {
    return {
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
  background-color: hsl(180, 52%, 96%);
}

header {
  background-color: hsl(180, 29%, 50%);
}

main {
  padding-top: 34px;
}
</style>
