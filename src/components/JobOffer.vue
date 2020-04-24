<template>
  <div class="job-offer" :class="job.featured && 'job-offer--featured'">
    <img :src="require(`@/assets/images/${job.logo}`)" class="logo">
    <div class="job-offer__left">

      <div class="row">
        <h3 class="title">
          {{ job.company }}
        </h3>
        <p class="badge badge-new" v-if="job.new">New!</p>
        <p class="badge badge-featured" v-if="job.featured">Featured</p>
      </div>
      <div class="row">
        <p class="position">{{ job.position }}</p>
      </div>
      <div class="row">
        <span class="label">{{ job.postedAt }}</span>
        <span class="label">{{ job.contract }}</span>
        <span class="label">{{ job.location }}</span>
      </div>
    </div>
    <hr class="divider">
    <div class="job-offer__right">
      <div class="row">
        <p class="tag">{{ job.role }}</p>
        <p class="tag">{{ job.level }}</p>
        <p class="tag" v-for="tool in job.tools" :key="tool"
        >{{ tool }}</p>
        <p class="tag" v-for="language in job.languages" :key="language"
        >{{ language }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'JobOffer',
  props: {
    job: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
.job-offer {
  margin: 0 24px 40px;
  padding: 24px;
  padding-top: 37px;
  background-color: #ffffff;
  position: relative;
  border-radius: 5px;
}

.job-offer--featured {
  border-left: 5px solid hsl(180, 29%, 50%);
}

.logo {
  position: absolute;
  width: 48px;
  height: 48px;
  border-radius: 50%;
  top: 0;
  left: 24px;
  transform: translateY(-50%);
}

.row {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  margin-bottom: 8px;
}

.title {
  margin: 0;
  margin-right: 16px;
  padding: 0;
  font-weight: 700;
  font-size: 13px;
  color: hsl(180, 29%, 50%);
}

.badge {
  border-radius: 12px;
  padding: 6px 8px 4px;
  text-transform: uppercase;
  font-weight: 700;
  font-size: 11px;
  line-height: 14px;
  color: hsl(0, 0%, 100%);
  margin: 0;
  margin-right: 8px;
}

.badge-new {
  background-color: hsl(180, 29%, 50%);
}

.badge-featured {
  background-color: hsl(180, 14%, 20%);
}

.position {
  margin: 0;
  font-weight: 700;
  line-height: 1.6;
  color: hsl(180, 14%, 20%);
}

.label {
  position: relative;
  font-size: 13px;
  line-height: 24px;
  padding-right: 20px;
  color: hsl(180, 8%, 52%);
}

.label:last-child {
  padding-right: 0;
}

.label:not(:last-child)::after {
  content: "";
  position: absolute;
  right: 8px;
  top: 50%;
  transform: translateY(-50%);
  border-radius: 50%;
  width: 4px;
  height: 4px;
  background-color: hsl(180, 8%, 52%);
}

.divider {
  border: 0;
  height: 1px;
  background-color: hsl(180, 8%, 52%);
  margin: 16px 0;
}

.tag {
  padding: 4px 8px;
  background-color: hsl(180, 52%, 96%);
  color: hsl(180, 29%, 50%);
  font-weight: 700;
  font-size: 13px;
  line-height: 24px;
  border-radius: 4px;
  margin: 0 16px 8px 0;
}

@media screen and (min-width: 1440px) {
  .job-offer {
    display: flex;
    justify-content: space-between;
    padding-left: 152px;
    width: 1110px;
    margin: 0 auto 24px;
  }

  .divider {
    display: none;
  }

  .logo {
    left: 40px;
    width: 88px;
    height: 88px;
    top: 50%;
  }
}
</style>
