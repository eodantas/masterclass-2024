<script setup lang="ts">
import { ref } from 'vue'
import { supabase } from '@/lib/supabaseClient'

const teste = ref<string>('teste')

(async () => {
  const { data, error } = await supabase.from('projects').select()
  if (error) {
    console.log(error)
  }
  console.log(data)
})()
</script>

<template>
  <div>
    <h1>Projects Page</h1>
    <RouterLink to="/">Home</RouterLink>
    {{ teste }}
  </div>
</template>
