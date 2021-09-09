<template>
  <div class="mikel-mif">
    <LazyHydrate never>
      <header class="has-text-white flex-center-center">
        <div class="wrapper pt-20">
          <div class="has-text-right pr-15">
            <nuxt-link
              class="has-text-white"
              :to="switchLocalePath('es')"
            >
              ES
            </nuxt-link> /
            <nuxt-link
              class="has-text-white"
              :to="switchLocalePath('en')"
            >
              EN
            </nuxt-link>
          </div>
          <div class="header-content">
            <div class="column">
              <h2 class="title"> {{ $t('home.title_job') }} </h2>
              <p class="mb-35"> {{ $t('home.mikel_description')}} </p>
              <div class="pl-5">
                <a
                  href="mailto:mikelmif@gmail.com"
                  class="cta"
                >
                  {{ $t('home.cta_text')}}
                </a>
              </div>
            </div>
            <div class="column flex flex-center-center">
              <div class="blob"></div>
            </div>
          </div>
        </div>
      </header>
    </LazyHydrate>
    <LazyHydrate never>
      <wave />
    </LazyHydrate>
    <main>
      <section class="wrapper pb-50 pt-20 pl-10 pr-10">
        <h2 class="title pb-15"> {{ $t('home.technologies_title')}} </h2>
        <p class="pb-15"> {{ $t('home.technologies_subtitle')}} </p>
        <client-only>
          <div
            class="technologies"
            v-for="(technology,index) in technologies"
            :key="'technology'+index"
          >
            <p class="technology-name">{{technology.name}}</p>
            <div
              :id="technology.name+'_'+technology.skill"
              :style="{'background-color':technology.color}"
            />
          </div>
        </client-only>
      </section>
      <section class="is-relative">
        <div class="wrapper particles-content padding-md">
          <div class="content-fade">
            <h2 class="title"> {{ $t('home.title_about_me')}} </h2>
            <div class="flex flex-center flex-wrap">
              <article class="box">
                <div class="has-text-centered pb-10">
                  <fa
                    icon="graduation-cap"
                    size="3x"
                    class="has-text-dark-blue"
                  />
                  <h3> {{ $t('home.background_title')}} </h3>
                </div>
                <div class="has-text-centered">
                  <p>
                    {{$t('home.background_content[0]')}}
                  </p>
                  <p>
                    {{$t('home.background_content[1]')}}
                  </p>
                  <span> ---------- </span>
                </div>
                <div class="has-text-centered">
                  <p> {{$t('home.background_content[2]')}} </p>
                </div>
              </article>
              <article class="box">
                <div class="has-text-centered pb-10">
                  <fa
                    icon="handshake"
                    size="3x"
                    class="has-text-dark-blue"
                  />
                  <h3> {{ $t('home.clients_title')}} </h3>
                </div>
                <div class="has-text-centered">
                  <p> {{$t('home.clients_content[0]')}} </p>
                  <p v-html="$t('home.clients_content[1]')" />
                </div>
              </article>
              <article class="box">
                <div class="has-text-centered pb-10">
                  <fa
                    icon="briefcase"
                    size="3x"
                    class="has-text-dark-blue"
                  />
                  <h3> {{ $t('home.entrepreneur_title')}} </h3>
                  <p> {{$t('home.enterpreneur_content')}} </p>
                </div>
              </article>
            </div>
          </div>
        </div>
        <client-only>
          <LazyHydrate when-visible>
            <particles-bg
              type="cobweb"
              :canvas="{backgroundColor:'#0d324d'}"
              color="#FFFAFA"
              :bg="true"
            />
          </LazyHydrate>
        </client-only>
      </section>
      <LazyHydrate never>
        <section class="wrapper content-fade padding-md">
          <h2 class="title"> {{ $t('home.project_title') }} </h2>
          <p> {{ $t('home.project_content[0]') }} </p>
          <p> {{ $t('home.project_content[1]') }} </p>
          <div class="has-text-centered pt-50 pb-50">
            <a
              href="mailto:mikelmif@gmail.com"
              class="cta"
            >
              {{ $t('home.cta_text')}}
            </a>
          </div>
        </section>
      </LazyHydrate>
      <LazyHydrate never>
        <social-media
          title="Mikel Illán - Web Developer"
          :description="$t('home.mikel_description')"
          image-src="https://www.mikeli.dev/mikel-media.webp"
          :image-alt="$t('home.mikel_alt')"
        />
      </LazyHydrate>
    </main>
    <footer
      class="has-text-centered"
      style="background-color:black;"
    >
      <span class="has-text-white small-text-touch"> {{ $t('home.web_design') }} </span>
    </footer>
  </div>
</template>

<script>
import Wave from "@/components/Wave.vue";
import SocialMedia from "@/components/SocialMedia.vue"
import LazyHydrate from 'vue-lazy-hydration'

export default {
  name: "Mikel-Illán",
  components: { Wave, SocialMedia, LazyHydrate },
  data () {
    return {
      technologies: [
        { name: "html", color: "orange", skill: 90 },
        { name: "css/Sass", color: "#016afb", skill: 90 },
        { name: "JavaScript", color: "#fcdf03", skill: 90 },
        { name: "Vue", color: "#59b57e", skill: 80 },
        { name: "Nuxt", color: "#316345", skill: 80 },
        { name: "PHP", color: "#1f51c4", skill: 60 },
        { name: "Laravel", color: "red", skill: 55 },
        { name: "PostgreSQL", color: "#396387", skill: 65 },
        { name: "MySQL", color: "#1f51c4", skill: 70 },
        { name: "Wordpress", color: "#070d12", skill: 90 }
      ]
    };
  },
  head () {
    return {
      title: "Mikel Illán - Web Developer",
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: this.$t('home.mikel_description')
        },
        {
          hid: 'keywords',
          name: 'keywords',
          content: 'web developer, desarrollador web, desarrollo web, web design, web, crear página web'
        }
      ]
    }
  },
  mounted () {
    this.addClassesOnScroll();
  },
  methods: {
    addClassesOnScroll () {
      const loadContent = entries => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            entry.target.classList.add("fade");
          }
        });
      };
      const options = {};
      const contentFadeObserver = new IntersectionObserver(loadContent, options);
      const contentFade = document.querySelectorAll(".content-fade>*");
      contentFade.forEach(content => {
        contentFadeObserver.observe(content);
      });

      const loadProgressBar = entries => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            const skill = entry.target.id.replace(/\D/g, "");
            entry.target.classList.add("progress-bar-" + skill);
          }
        });
      };
      const observeProgressBar = new IntersectionObserver(loadProgressBar, options);
      setTimeout(() => {
        for (const technology of this.technologies) {
          const technologySkill = technology.name + "_" + technology.skill;
          const ref = document.getElementById(technologySkill);
          observeProgressBar.observe(ref);
        }
      }, 50);
    }
  }
};
</script>

<style lang="scss">
header {
  background-color: #7f5a83;
  background-image: linear-gradient(#030203 0%, #0d324d 74%);
  @media (min-width: 1001px) {
    height: 75vh;
  }
  @media (min-width: 501px) and (max-width: 1000px) {
    height: 90vh;
  }
  @media (max-width: 500px) {
    padding-bottom: 1.75rem;
  }
}

.title {
  font-size: 45px;
  padding-bottom: 18px;
  @media (max-width: 500px) {
    font-size: 23px;
  }
  @media (max-width: 1000px) {
    font-size: 35px;
  }
}

.header-content {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 100px 50px 0px 50px;
  .column {
    width: 50%;
  }
  @media (max-width: 1000px) {
    flex-direction: column-reverse;
    padding: 25px 12px 0px 12px;
    .column {
      width: 100%;
      padding: 25px 0;
      text-align: center;
    }
  }
  @media (max-width: 400px) {
    padding: 0 12px;
    .column {
      padding-bottom: 0;
    }
  }
}

.cta {
  z-index: 50;
  font-size: 35px;
  color: azure;
  background-color: #0d324d;
  cursor: pointer;
  text-decoration: none;
  padding: 0.8rem 1.6rem;
  border-radius: 5px;
  box-shadow: 1px 1px 4px 4px #3299a8;
  &:hover {
    color: rgb(17, 158, 200);
    border-color: rgb(17, 158, 200);
    background-color: azure;
  }
  @media (max-width: 900px) {
    font-size: 20px;
  }
  @media (max-width: 360px) {
    display: block;
    width: 80%;
    margin: auto;
  }
}

/* BLOB CSS */
:root {
  --radius-1: 70%;
  --radius-2: 30%;
  --radius-3: 30%;
  --radius-4: 70%;
  --radius-5: 60%;
  --radius-6: 40%;
  --radius-7: 60%;
  --radius-8: 40%;
}

.blob {
  width: 400px;
  height: 400px;
  border-radius: var(--radius-1) var(--radius-2) var(--radius-3) var(--radius-4) /
    var(--radius-5) var(--radius-6) var(--radius-7) var(--radius-8);
  background-color: #0d324d;
  background-image: url("../static/mikel.webp");
  background-repeat: no-repeat;
  background-size: cover;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
  @media (max-width: 1600px) {
    width: 300px;
    height: 300px;
  }
  @media (max-width: 800px) {
    width: 250px;
    height: 250px;
  }
  @media (max-width: 400px) {
    width: 180px;
    height: 180px;
  }
}

/* TECHNOLOGIES CSS */
.technologies {
  width: 70%;
  @media (max-width: 768px) {
    width: 100%;
  }
}

.technology-name {
  font-size: 22px;
  font-weight: 600;
}

$sizes: 10, 20, 30, 40, 50, 55, 60, 65, 70, 80, 90, 100;

$sizes: 10, 20, 30, 40, 50, 55, 60, 65, 70, 80, 90, 100;

@each $size in $sizes {
  .progress-bar-#{$size} {
    width: 0px;
    height: 15px;
    border-radius: 15px;
    background: black;
    animation: progress-#{$size} 3s;
    animation-fill-mode: forwards;

    @keyframes progress-#{$size} {
      from {
        width: 0px;
      }
      to {
        width: percentage($size / 100);
      }
    }
  }
}
.particles-content {
  color: white;
}
</style>
