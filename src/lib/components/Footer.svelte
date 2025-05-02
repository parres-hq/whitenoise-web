<script lang="ts">
import DownloadButton from "./DownloadButton.svelte";
</script>

<footer class="bg-glitch-50 text-glitch-950 flex flex-row items-center py-6 gap-x-10 px-12 justify-between">
  <div class="flex flex-col items-start">
    <div class="mb-2">
      <DownloadButton size={24} />
    </div>
  </div>
  <div class="flex flex-col items-end gap-2 text-right text-base">
    <a href="/privacy-matters" class="hover:underline">Privacy Matters</a>
    <a href="#faqs" class="hover:underline">FAQs</a>
    <a href="https://habla.news/u/_@jeffg.fyi" class="hover:underline">Updates</a>
    <a href="https://github.com/parres-hq/whitenoise?tab=readme-ov-file#contributing" class="hover:underline">Developers</a>
    <span class="text-xs text-glitch-400 mt-2">©2025 White Noise</span>
  </div>
</footer>
