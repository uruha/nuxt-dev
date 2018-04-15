<template>
  <div>
      <ul>
          <li>
              Counter info: {{$store.state.counter}}
          </li>
          <li>
            <button @click="$store.commit('increment')">
              Increment
            </button>
          </li>
          <li>
            <button @click="$store.commit('decrement')">
              Decrement
            </button>
          </li>
          <li>
              <nuxt-link to="/">Go Home</nuxt-link>
          </li>
      </ul>
  </div>
</template>