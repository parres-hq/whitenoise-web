<script lang="ts">
import FeatureSection from "$lib/components/FeatureSection.svelte";
import type { FeatureCard } from "$lib/types";
import Download from "carbon-icons-svelte/lib/Download.svelte";

const featureCards: FeatureCard[] = [
    {
        imagePosition: "left",
        color: "light",
        imageUrl: "/images/mask-man.webp",
        title: "Privacy & Security",
        description:
            "White Noise protects your conversations with unbreakable cryptography, ensuring complete privacy through end-to-end encryption. Forward secrecy and post-compromise security guarantee that even if your keys are compromised, past and future conversations remain invisible to anyone who gains control.",
    },
    {
        imagePosition: "right",
        color: "dark",
        imageUrl: "/images/balloon-girl.webp",
        title: "Identity Freedom",
        description:
            "Communicate securely without revealing personal details like phone numbers or emails. You have complete freedom to control your online identity—choose to remain fully anonymous, use a pseudonym, or your real name. Your identity, your choice.",
    },
    {
        imagePosition: "left",
        color: "light",
        imageUrl: "/images/hands.webp",
        title: "Open & Decentralized",
        description:
            "Built on open standards (Nostr and MLS), White Noise allows your identity, data, and connections to be portable across multiple apps. This open architecture means protocols are freely available for any app to utilize, giving you the flexibility to switch to the most secure or user-friendly option without losing your identity or contacts.",
    },
    {
        imagePosition: "right",
        color: "dark",
        imageUrl: "/images/smoke.webp",
        title: "Distributed & Unscensorable",
        description:
            "White Noise's decentralized network relies on thousands of independent relays worldwide, preventing any single point of failure or censorship. You can easily run your own relay on a home computer with just a few clicks, ensuring you communicate through your own infrastructure rather than depending on corporate-owned servers.",
    },
    {
        imagePosition: "left",
        color: "light",
        imageUrl: "/images/race-car.webp",
        title: "Fast, Reliable, & Scalable",
        description:
            "White Noise is meticulously engineered for uncompromising speed, stability, and reliability. It delivers blazing-fast performance and real-time responsiveness, designed to handle everything from direct messages to large group conversations effortlessly.",
    },
    {
        imagePosition: "right",
        color: "dark",
        imageUrl: "/images/kids.webp",
        title: "Non-Profit & Community-Driven",
        description:
            "White Noise is a non-profit, community-driven project. We are not funded by any corporation, and we are not beholden to any government or organization. We are a group of volunteers who are passionate about privacy and security.",
    },
];
</script>

<div class="hero flex flex-col md:flex-row items-center justify-between px-0 bg-glitch-950 bg-[url('/images/blocks-background.webp')] bg-no-repeat bg-center-bottom md:bg-right bg-cover">
    <div class="flex flex-col gap-4 max-w-xl flex-1 px-16 justify-center text-center md:text-left items-center md:items-start">
        <h1 class="text-6xl font-bold text-glitch-50">White Noise</h1>
        <p class="text-xl text-glitch-200 font-medium">A truly secure and private messenger that's lightning fast, infinitely scalable, and identity-free.</p>
        <a href="https://github.com/parres-hq/white-noise/releases" target="_blank" class="bg-cyan-300 text-glitch-950 px-6 py-2 text-xl flex flex-row gap-3 items-center font-medium mt-4">
            Download
            <Download size={20} class="w-5 h-5" />
        </a>
    </div>
    <div>
        <img src="/images/lady-noise.webp" alt="Lady Noise Statue" class="relative max-h-[95%] max-w-[520px] object-contain drop-shadow-2xl top-8" />
    </div>
</div>

<div class="flex flex-col gap-8 md:gap-12 px-4 md:px-12 py-8 md:py-12 justify-center text-center md:text-left items-center md:items-start">
    {#each featureCards as card}
        <FeatureSection featureCard={card} />
    {/each}
</div>
