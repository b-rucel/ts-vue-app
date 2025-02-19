<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue'
import { Button } from '@/components/ui/button'
import { Card, CardHeader, CardTitle, CardDescription, CardContent, CardFooter } from "@/components/ui/card"
import { GithubIcon, CodeIcon, BookOpenIcon, RocketIcon, SunIcon, MoonIcon } from 'lucide-vue-next'
import { useDark, useToggle } from '@vueuse/core'

const isDark = useDark()
const toggleDark = useToggle(isDark)
</script>

<template>
  <main class="min-h-screen bg-background p-8 md:p-12">
    <div class="container mx-auto max-w-6xl space-y-8">
      <!-- Theme Toggle -->
      <div class="flex justify-end">
        <Button 
          variant="ghost" 
          size="icon" 
          @click="toggleDark()"
        >
          <SunIcon v-if="isDark" class="h-5 w-5" />
          <MoonIcon v-else class="h-5 w-5" />
          <span class="sr-only">Toggle theme</span>
        </Button>
      </div>

      <!-- Hero Section -->
      <div class="text-center space-y-4 mb-12">
        <div class="flex justify-center gap-6 mb-6">
          <a href="https://vite.dev" target="_blank">
            <img src="/vite.svg" class="logo h-16" alt="Vite logo" />
          </a>
          <a href="https://vuejs.org/" target="_blank">
            <img src="./assets/vue.svg" class="logo h-16" alt="Vue logo" />
          </a>
        </div>
        <h1 class="text-4xl font-bold tracking-tight">Welcome to Vue + Vite</h1>
        <p class="text-muted-foreground text-lg">Get started by editing your components</p>
      </div>

      <!-- Features Grid -->
      <div class="grid md:grid-cols-2 gap-6">
        <Card>
          <CardHeader>
            <CardTitle class="flex items-center gap-2">
              <RocketIcon class="h-5 w-5" />
              Quick Start
            </CardTitle>
            <CardDescription>
              Get your Vue project up and running in seconds
            </CardDescription>
          </CardHeader>
          <CardContent>
            Experience lightning-fast HMR and build times with Vite's modern development server.
          </CardContent>
          <CardFooter>
            <Button variant="secondary" class="w-full">
              <CodeIcon class="mr-2 h-4 w-4" />
              View Documentation
            </Button>
          </CardFooter>
        </Card>

        <Card>
          <CardHeader>
            <CardTitle class="flex items-center gap-2">
              <BookOpenIcon class="h-5 w-5" />
              Learn Vue
            </CardTitle>
            <CardDescription>
              Comprehensive guides and tutorials
            </CardDescription>
          </CardHeader>
          <CardContent>
            Master Vue.js with official documentation, examples, and best practices.
          </CardContent>
          <CardFooter>
            <Button variant="secondary" class="w-full">
              <BookOpenIcon class="mr-2 h-4 w-4" />
              Start Learning
            </Button>
          </CardFooter>
        </Card>
      </div>

      <Card class="mt-8">
        <CardHeader>
          <CardTitle>Ready to Use</CardTitle>
          <CardDescription>
            Use this repo as a starting point
          </CardDescription>
        </CardHeader>
        <CardContent class="bg-muted p-4 px-6 rounded-md font-mono text-sm">
          <pre>npx degit https://github.com/b-rucel/js-vue-app new-project

cd new-project
npm install
npm run dev</pre>
        </CardContent>
        <CardFooter class="text-muted-foreground text-sm mt-4">
          Simple installation process, extensive component library included
        </CardFooter>
      </Card>

      <!-- GitHub Section -->
      <div class="text-center mt-12">
        <Button variant="outline" asChild>
          <a href="https://github.com/vuejs/vue" target="_blank" class="flex items-center">
            <GithubIcon class="mr-2 h-4 w-4" />
            Star us on GitHub
          </a>
        </Button>
      </div>
    </div>
  </main>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
