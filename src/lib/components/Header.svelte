<script lang="ts">
import Close from "carbon-icons-svelte/lib/Close.svelte";
import Download from "carbon-icons-svelte/lib/Download.svelte";
import Menu from "carbon-icons-svelte/lib/Menu.svelte";

let isMenuOpen = $state(false);

function toggleMenu() {
    isMenuOpen = !isMenuOpen;
}
</script>

<header class="bg-glitch-950 text-glitch-50">
    <div class="max-w-7xl mx-auto flex flex-row items-center justify-between py-6 px-6 md:px-12">
        <a href="/" class="logo-container flex items-center" style="min-height:40px">
            <img src="/images/logomark.svg" alt="White Noise" class="logo-img h-10 w-auto" />
        </a>

        <!-- Mobile menu button -->
        <button
            class="md:hidden text-glitch-200 hover:text-cyan-300"
            onclick={toggleMenu}
            aria-label="Toggle menu"
        >
            {#if isMenuOpen}
                <Close size={24} />
            {:else}
                <Menu size={24} />
            {/if}
        </button>

        <!-- Navigation -->
        <nav class="hidden md:flex flex-row items-center gap-x-2 text-glitch-200 text-lg leading-snug font-medium">
            <a href="/privacy-matters" class="px-4 py-2 hover:text-cyan-300">Privacy Matters</a>
            <a href="/#faqs" class="px-4 py-2 hover:text-cyan-300">FAQs</a>
            <a href="https://habla.news/u/_@jeffg.fyi" class="px-4 py-2 hover:text-cyan-300">Updates</a>
            <a href="https://github.com/parres-hq/whitenoise?tab=readme-ov-file#contributing" class="px-4 py-2 hover:text-cyan-300">Developers</a>
            <a href="/" class="px-4 py-2 hover:text-cyan-300 border-1 border-glitch-800 hover:border-cyan-300 flex flex-row gap-2 items-center">
                Coming Soon
                <!-- <Download size={20} class="w-5 h-5" /> -->
            </a>
        </nav>
    </div>

    <!-- Mobile menu overlay -->
    {#if isMenuOpen}
        <div class="fixed inset-0 bg-glitch-950 z-50 md:hidden flex flex-col justify-between w-full h-full box-border overflow-hidden max-w-full max-h-full">
            <div class="flex flex-col h-full w-full box-border max-w-full max-h-full">
                <div class="flex flex-row justify-between items-center px-6 pt-6 w-full box-border max-w-full">
                    <a href="/" class="logo-container flex items-center" style="min-height:40px">
                        <img src="/images/logomark.svg" alt="White Noise" class="logo-img h-10 w-auto" />
                    </a>
                    <button class="text-glitch-50" onclick={toggleMenu} aria-label="Close menu">
                        <Close size={32} />
                    </button>
                </div>
                <div class="flex flex-col items-center justify-center flex-1 gap-y-10 text-2xl font-medium w-full px-4 overflow-y-auto box-border max-w-full">
                    <a href="/privacy-matters" class="px-4 py-2 hover:text-cyan-300" onclick={toggleMenu}>Privacy Matters</a>
                    <a href="/#faqs" class="px-4 py-2 hover:text-cyan-300" onclick={toggleMenu}>FAQs</a>
                    <a href="https://habla.news/u/_@jeffg.fyi" class="px-4 py-2 hover:text-cyan-300" onclick={toggleMenu}>Updates</a>
                    <a href="https://github.com/parres-hq/whitenoise?tab=readme-ov-file#contributing" class="px-4 py-2 hover:text-cyan-300" onclick={toggleMenu}>Developers</a>
                </div>
                <div class="flex flex-col items-center gap-y-2 pb-10 px-4 w-full box-border max-w-full">
                    <a href="/" class="w-full max-w-xs bg-cyan-400 text-glitch-950 text-lg font-medium px-4 py-2 flex flex-row gap-2 items-center justify-center hover:bg-cyan-300 transition-colors" onclick={toggleMenu}>
                        Coming Soon
                        <!-- <Download size={20} class="w-5 h-5" /> -->
                    </a>
                </div>
            </div>
        </div>
    {/if}
</header>
