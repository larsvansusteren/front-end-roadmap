<template>
  <v-container>
    <v-row>
      <v-col cols="12">
        <v-timeline class="mt-6">
          <v-timeline-item
            v-for="(goal, i) in goals"
            :key="i"
            :color="goal.color"
            right            
          >
            <template v-slot:opposite>
              <span
                :class="`headline font-weight-bold ${goal.color}--text`"
                v-text="goal.title"
              ></span>
            </template>
            <div class="py-4">
              <h4>Learned</h4>
              <div v-for="(skill, i) in goal.skills" :key="i" class="mt-1 d-inline-flex">
                <div v-if="skill.done === true">
                  <v-chip
                    color="green"
                    text-color="white"
                    class="mr-1 mb-1 pl-1"
                    
                  >
                    <v-icon class="mr-2">mdi-checkbox-marked-circle</v-icon>
                    {{skill.name}}
                  </v-chip>
                </div>
              </div>
              <h4 class="mt-4">To learn</h4>
              <div v-for="(skill, i) in goal.skills" :key="i" class="mt-1 d-inline-flex">
                <div v-if="skill.done === false">
                  <v-chip
                    color="lightgrey"
                    text-color="grey"
                    class="mr-1 mb-1"
                  >
                    {{skill.name}}
                  </v-chip>
                </div>
              </div>
            </div>
          </v-timeline-item>
        </v-timeline>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
  export default {
    name: 'Roadmap',

    data: () => ({
      goals: [
        {
          title: 'Internet',
          color: 'orange',
          skills: [
            { name: 'How does the internet work?', done: true },
            { name: 'Web browsers', done: true },
            { name: 'Domain names', done: true },
            { name: 'What is web hosting?', done: true },
            { name: 'HTTP', done: false },
            { name: 'DNS', done: false },
          ]
        },
        {
          title: 'HTML',
          color: 'orange',
          skills: [
            { name: 'Composing web pages', done: true },
            { name: 'Semantic HTML', done: true },
            { name: 'Forms and validations', done: false },
            { name: 'Conventions and best practices', done: true },
            { name: 'Accessibility', done: true },
            { name: 'SEO', done: true },
          ]
        },
        {
          title: 'CSS',
          color: 'green',
          skills: [
            { name: 'CSS classes', done: true },
            { name: 'Making layouts', done: true },
            { name: 'Responsive design', done: true },
            { name: 'CSS grid', done: true },
            { name: 'Floats', done: true },
            { name: 'Flex box', done: true },
          ]
        },
        {
          title: 'JavaScript',
          color: 'red',
          skills: [
            { name: 'Syntax and basic constructs', done: true },
            { name: 'DOM manipulation', done: false },
            { name: 'Fetch API / Ajax (XHR)', done: false },
            { name: 'ES6+ and modular JavaScript', done: false },
            { name: 'Hoisting, Event bubbling, Scope, Protype, Shadow DOM, Strict', done: false },
          ]
        },
        {
          title: 'Version Control Systems',
          color: 'green',
          skills: [
            { name: 'Use of Git', done: true },
            { name: 'GitHub', done: true },
            { name: 'Gitlab', done: true },
          ]
        },
        {
          title: 'Web Security',
          color: 'red',
          skills: [
            { name: 'HTTPS', done: false },
            { name: 'CORS', done: false },
            { name: 'Content Security Policy', done: false },
            { name: 'OWASP Security Risks', done: false },
          ]
        },
        {
          title: 'Package managers',
          color: 'green',
          skills: [
            { name: 'NPM', done: true },
            { name: 'Yarn', done: true },
          ]
        },
        // add everything below package managers from here: https://roadmap.sh/frontend
        {
          title: 'Splunk',
          color: 'orange',
          skills: [
            { name: 'Creating search queries', done: true },
            { name: 'Creating alerts', done: true },
            { name: 'Creating dashboards', done: true },
            { name: 'Search performance', done: true },
            { name: 'Advanced searches', done: false },
          ]
        },
        // {
        //   title: '',
        //   color: 'orange',
        //   skills: [
        //     { name: '', done: true },
        //     { name: '', done: false },
        //   ]
        // },
      ],
    }),
  }
</script>
