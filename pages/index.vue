<template>
  <div>
    <div v-if="step === 0" class="hero is-black is-fullheight hero-bold">
      <div class="hero-body">
        <div class="container">
          <h1 class="title has-text-centered">
            ¿Problemas? ¡Tenemos la solución!
          </h1>
          <div class="columns is-centered">
            <div class="column is-5 is-12-mobile" style="padding: 20pt">
              <p class="has-text-centered">
                Sé que tienes problemas, todos tenemos problemas, los países
                tienen problemas, la humanidad tiene problemas. Pero tenemos la
                solución.
              </p>
              <p class="has-text-centered" style="margin-top: 10pt">
                Escribe tu nombre para descubrirla.
              </p>
            </div>
          </div>
          <div class="columns is-centered">
            <div class="column is-6 is-12 mobile" style="padding: 20pt">
              <b-field>
                <b-input
                  v-model="name"
                  type="is-danger"
                  size="is-large"
                  placeholder="Tu nombre"
                  rounded
                ></b-input>
              </b-field>
              <b-field>
                <b-button
                  type="is-danger"
                  size="is-large"
                  rounded
                  expanded
                  :disabled="!name"
                  @click="solution()"
                >
                  Dime la solución a TODO
                </b-button>
              </b-field>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div
      v-if="step === 1"
      class="hero is-success is-fullheight hero-bold"
      style="background: url('/bg.webp'); background-size: cover"
    >
      <div class="hero-body">
        <div class="container">
          <div
            style="background: rgba(255, 255, 255, 0.95); border-radius: 15pt; padding: 20pt"
          >
            <h1 class="title has-text-black has-text-centered">
              {{ name }}, la solución a todo es:
            </h1>
            <div class="has-text-centered">
              <img
                src="/limonade.png"
                alt=""
                width="250pt"
                class="has-text-centered"
              />
            </div>
            <h2 class="subtitle has-text-centered">
              <a
                href="https://twitter.com/hashtag/LaLimonadaEsLaBaseDeTodo"
                class="has-text-info"
              >
                #LaLimonadaEsLaBaseDeTodo
              </a>
            </h2>
            <div class="has-text-centered">
              <a
                href="https://twitter.com/intent/tweet?url=solution.lugodev.com&text=Descubre la solución a tus problemas y los de la humanidad vía @lugodev"
                target="_blank"
              >
                <b-button
                  type="is-info"
                  icon-right="twitter"
                  size="is-medium"
                  rounded
                >
                  Compartir
                </b-button>
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: null,
      step: 0
    }
  },

  methods: {
    solution() {
      this.step = 1
    }
  }
}
</script>
