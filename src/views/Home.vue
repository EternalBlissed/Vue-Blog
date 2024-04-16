<template>
  <div class="home">
    <h1 class="headline center">Eternal's Blog</h1>
    <div class="entries">{{ totalEntriesMessage }}</div>
    <div class="sections">
      <div v-for="(section, index) in Object.keys(entries)" :key="index" class="group">
        <h2 class="center">{{section}}</h2>
        <div class="section" v-for="entry in entries[section]" :key="entry.id">
          <div class="entry">
            <h3 @click="$router.push({name: entry.id})">
              {{entry.title}}
              <span class="subtitle">{{entry.date}}</span>
            </h3>
            <p>{{entry.description}}</p>
          </div>
        </div>
      </div>
    </div>
     <!--<audio controls>
      <source src="../assets/12.flac" type="audio/flac">
       Your browser does not support the audio element.
      </audio>-->
  </div>
</template>

<script>
import BLOGENTRIES from '@/statics/data/blogs.json'

export default {
  name: 'home',
  computed: {
    entries() {
      return BLOGENTRIES
    },
    totalEntriesCount() {
      // Calculate the total count of entries
      return Object.values(this.entries).reduce((total, section) => total + section.length, 0);
    },
    totalEntriesMessage() {
      // Generate the message displaying the total count
      return `Serving ${this.totalEntriesCount} Pages`;
    }
  }
}
</script>

<style scoped>

audio {
  display: block;
  margin-left: auto;
  margin-right: auto;
  margin-top: 8px;
  border: 1px solid #fff;
  border-radius: 10px;
  background-color: rgba(0, 0, 0, 0);
}

.center {
  text-align: center;
}

.headline {
  margin: 4rem auto;
  font-size: 4rem;
}

.entries {
  text-align: center;
  margin: 4rem auto;
  font-size: 1.5rem;
}

img {
  display: block;
  margin: 0 auto;
  width: 150px;
}

h2 {
  color: #fff;
  text-transform: capitalize;
  margin-bottom: 2rem;
}

h3 {
  color: #42b883;
  margin-bottom: 0;
  cursor: pointer;
}

h3:hover {
  text-decoration: underline;
}

.subtitle {
  color: grey;
  font-size: 0.98rem;
  float: right;
  font-weight: normal;
}

p {
  margin-top: 0.4rem;
}

.sections {
  max-width: 40vw;
  margin: 0 auto;
  margin-top: 4rem;
}

.section {
  margin-bottom: 3rem;
}

.group {
  margin-bottom: 4rem;
}

</style>
