<script lang="ts">
import type { FeatureCard } from "$lib/types";

let { featureCard }: { featureCard: FeatureCard } = $props();
</script>

<div class="flex flex-col md:flex-row justify-between items-center gap-8 md:gap-12 w-full {featureCard.imagePosition === 'left' ? 'md:flex-row' : 'md:flex-row-reverse'}">
    <img class="w-full max-w-[460px] max-h-[460px] object-contain" src={featureCard.imageUrl} alt={featureCard.title} />
    <div class="w-full px-6 md:px-10 py-6 md:py-8 flex flex-col justify-start items-start gap-2 {featureCard.color === 'dark' ? 'bg-glitch-950 text-glitch-50' : 'bg-glitch-50 text-glitch-950'}">
        <div class="self-stretch justify-start text-3xl md:text-4xl font-bold leading-10">{featureCard.title}</div>
        <div class="self-stretch justify-start text-base">{featureCard.description}</div>
    </div>
</div>
