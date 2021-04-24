<template>
    <div
    class="fixed top-0 left-0 right-0 z-10 py-6 bg-pink-700 text-coolGray-300"
  >
  <div class="container flex items-center justify-between mx-auto">
    <div class="flex space-x-2 text-3xl brand">          <flat-ui:responsive class="text-green-900" />
          <h1 class="font-thin">
            Chit<span class="font-bold text-blue-400">Chat</span>
          </h1>
        </div>
        <div class="menu">
          <div v-if="!isAuthenticated">
            <button
            class="px-4 py-2 text-white bg-blue-400 rounded-full hover:bg-blue-900 focus:outline-none focus:ring-4 focus:ring-green-500"
              @click="googlePopup"
            >
              Login
            </button>
          </div>
          <div v-else class="flex items-center space-x-8">
            <p>Welcome {{ user?.displayName }}</p>
            <button
            class="px-4 py-2 text-white bg-indigo-600 rounded-full hover:bg-indigo-900 focus:outline-none focus:ring-4 focus:ring-red-500"
              @click="signOut"
            >
              Logout
            </button>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { authentication } from '~/helpers/useFirebase'
  
  import { shallowRef } from 'vue'

const { isAuthenticated, user, googlePopup, signOut } = authentication()  </script>