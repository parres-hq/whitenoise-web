<script lang="ts">
let { question, answer, open = false, onClick } = $props();
</script>

<div class="transition-all border-glitch-100 border-0 duration-200 {open ? 'bg-white border-glitch-100 border-1' : 'bg-glitch-50'}">
  <button
    class="w-full flex items-center justify-between py-6 px-4 text-left focus:outline-none transition-colors {open ? 'bg-white' : 'bg-glitch-50 hover:bg-glitch-100'}"
    onclick={onClick}
    aria-expanded={open}
    aria-controls={question}
  >
    <span class="text-xl font-semibold transition-colors duration-200 {open ? 'text-glitch-900 font-bold' : 'text-glitch-700 font-semibold'}">{question}</span>
    <svg
      class="w-6 h-6 text-glitch-400 transition-transform duration-200" style:transform={open ? 'rotate(180deg)' : 'rotate(0deg)'}
      fill="none"
      stroke="currentColor"
      viewBox="0 0 24 24"
      xmlns="http://www.w3.org/2000/svg"
    >
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
    </svg>
  </button>
  {#if open}
    <div class="px-4 pb-6 text-glitch-700 text-base animate-fade-in">
      {answer}
    </div>
  {/if}
</div>

<style>
  @keyframes fade-in {
    from { opacity: 0; transform: translateY(-8px); }
    to { opacity: 1; transform: translateY(0); }
  }
  .animate-fade-in {
    animation: fade-in 0.2s ease;
  }
</style>
