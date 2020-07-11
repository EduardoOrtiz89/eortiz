<template>
  <Layout>
  <div class="flex flex-col justify-between py-16 mx-auto hero container-inner sm:flex-row">
    <div class="w-full text-4xl font-bold text-center sm:w-3/5 sm:text-left">
      <div class="leading-tight">Eduardo Ortiz Alvarado</div>
      <div class="leading-tight text-nord-9">Fullstack Developer</div>
    </div>
    <div class="mt-8 sm:mt-0">
      <g-image src="../../static/developer.svg" alt="hero" class="w-64 mx-auto sm:mx-0" />
    </div>
  </div> <!-- end hero -->

  <div class="mx-auto container-inner">
    <p class="text-lg sm:text-xl">
      Lorem ipsum dolor sit amet consectetur, adipisicing elit. Illum quam quasi cupiditate dolore mollitia culpa commodi beatae incidunt nulla id, dolor repellat, corrupti, modi obcaecati assumenda. Quos voluptates veritatis reiciendis!
    </p>

    <div class="flex items-center justify-between py-6">
      <div class="w-full px-8 py-8 sm:w-1/2 sm:py-0">
        <g-image src="../../static/html.svg" class="w-48" alt="browser" />
      </div>
      <div class="justify-end hidden w-1/2 px-8 sm:flex">
        <g-image src="../../static/code_review.svg" class="w-48" alt="mobile" />
      </div>
    </div>
  </div>

  <div class="overflow-x-hidden">
    <div class="relative py-16 mx-auto mb-16 text-xl border-t border-b border-gray-500 projects container-inner">
      <h2 class="mb-6 font-bold" id="projects">Here are some projects I've worked on:</h2>

      <div class="absolute right-0" style="top: 50px; transform: translate(100%) rotate(180deg)">
        <svg width="170px" height="170px"><use xlink:href="#dots-triangle" /></svg>
      </div>

      <ul class="text-lg sm:text-xl space-y-6">
        <li class="checkmark">
          <div>
            <a href="https://apps.apple.com/mx/app/zacatecas-mapa-de-riesgo/id1514009981#?platform=iphone" nofollow>
              Georiesgo Zacatecas
            </a>
          </div>
          <div class="text-lg text-gray-600">
            React Native App with a Map of zones with risk levels of COVID
          </div>
        </li>
        <li class="checkmark">
          <div>Project Two</div>
          <div class="text-lg text-gray-600">Lorem ipsum dolor sit amet consectetur adipisicing elit. Qui ab nam animi iure nemo exercitationem a, eius non culpa itaque!</div>
        </li>
        <li class="checkmark">
          <div>Project Three</div>
          <div class="text-lg text-gray-600">Lorem ipsum dolor sit amet consectetur adipisicing elit. Qui ab nam animi iure nemo exercitationem a, eius non culpa itaque!</div>
        </li>
        <li class="checkmark">
          <div>Project Four</div>
          <div class="text-lg text-gray-600">Lorem ipsum dolor sit amet consectetur adipisicing elit. Qui ab nam animi iure nemo exercitationem a, eius non culpa itaque!</div>
        </li>

      </ul>
    </div> <!-- end projects -->
  </div>

  <div class="overflow-x-hidden border-b border-gray-200">
    <div class="relative pb-16 mx-auto text-xl get-to-know-me container-inner">
      <h2 class="mb-6 font-bold" id="about">Get to know me:</h2>

      <div class="absolute left-0" style="top: 50px; transform: translateX(-100%)">
        <svg width="170px" height="170px"><use xlink:href="#dots-triangle" /></svg>
      </div>

      <div class="flex flex-col items-center justify-between mb-16 sm:flex-row">
        <div><g-image src="../../static/profile.jpg" alt="avatar" class="w-32 h-32 mb-8 rounded-full lg:mb-0" /></div>
        <div class="flex-1 ml-6 text-lg sm:text-xl">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Eum quae architecto minus molestias iusto ducimus fuga quo quia libero dignissimos, fugiat modi assumenda debitis laboriosam.</div>
      </div>

    </div> <!-- end get-to-know me -->
  </div>

  <div class="overflow-x-hidden">
    <div class="pt-16 contact-me bg-background-secondary">
      <div class="relative pb-4 mx-auto text-xl container-inner">
        <h2 class="mb-6 font-bold" id="contact">Get it touch</h2>
        <form name="contact"
              v-on:submit.prevent="handleSubmit"
              action="/success/"
              method="POST" data-netlify="true" class="" >
              <input type="hidden" name="form-name" value="contact" />
              <p hidden>
                <label>
                  Don’t fill this out: <input name="bot-field" />
                </label>
              </p>
              <div class="flex flex-col mb-3">
                <label class="mb-1 font-bold" for="name">Name</label>
                <input
                  v-model="formData.name"
                  type="text"
                  id="name"
                  name="name"
                  class="px-3 py-1 border border-gray-300 rounded-md">
              </div>
              <div class="flex flex-col mb-3">
                <label class="mb-1 font-bold" for="name">Email</label>
                <input
                  v-model="formData.email"
                  type="email"
                  id="email"
                  name="email"
                  class="px-3 py-1 border border-gray-300 rounded-md">
              </div>
              <div class="flex flex-col mb-3">
                <label class="mb-1 font-bold" for="name">Message</label>
                <textarea
                  v-model="formData.message"
                  id="message"
                  name="message"
                  class="px-3 py-1 border border-gray-300 rounded-md">
                </textarea>
              </div>
              <div class="flex justify-center mb-3">
                <button type="submit" class="px-6 py-1 text-white rounded-lg bg-nord-1">Send Message</button>
              </div>
        </form>


        <div class="absolute top-0 right-0" style="transform: translate(100%) rotate(180deg)">
          <svg width="170px" height="170px"><use xlink:href="#dots-triangle" /></svg>
        </div>

        <p class="mb-8 text-center"><a :href="'mailto:' + email + 'eortiz.dev'">{{email + 'eortiz.dev'}}</a></p>

        <div class="mb-16 text-lg sm:text-lg">
        </div>
      </div>
    </div> <!-- end contact-me -->
  </div>

  </Layout>
</template>

<script>
export default {
  metaInfo: {
    title: 'Home'
  },
  data() {
    return {
      email : '',
      formData: {},
    }
  },
  methods: {
    encode(data) {
      return Object.keys(data)
        .map(key => encodeURIComponent(key) + '=' + encodeURIComponent(data[key]))
        .join('&')
    },
    handleSubmit(e) {
      fetch('https://formspree.io/xoqkpakq', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/x-www-form-urlencoded',
          'Access-Control-Allow-Origin':'*'
        },
        body: this.encode({
          'form-name': e.target.getAttribute('name'),
          ...this.formData,
        }),
      })
        .then(() => this.$router.push('/success'))
        .catch(error => alert(error))
    }
  },

  mounted() {
    setTimeout(() => {
      this.email = 'eduardo@'
    }, 3000);
  },
}
</script>

