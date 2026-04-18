<script lang="ts">
  import { Infinity } from '@lucide/svelte';
  
  let { class: className = '' } = $props();
</script>

<div class="flex flex-col items-center justify-center group {className} cursor-pointer transition-transform active:scale-95">
  <!-- Elegan Sonsuzluk İşareti -->
  <div class="text-amber-600/80 dark:text-amber-400/80 group-hover:text-amber-500 transition-colors duration-500 transform group-hover:scale-110 mb-[-4px] relative z-10">
    <Infinity class="w-8 h-8" strokeWidth={1} />
  </div>

  <!-- İnce, İtalik "e davet" Metni -->
  <div class="flex items-baseline relative z-0">
    <span class="font-serif italic font-light text-2xl lg:text-3xl tracking-[0.08em] text-base-content group-hover:text-amber-600 dark:group-hover:text-amber-400 transition-colors duration-500">
      e davet
    </span>
    <span class="font-serif italic font-thin text-base lg:text-lg tracking-widest text-base-content/50 ml-1">
      .org
    </span>
  </div>
</div>
