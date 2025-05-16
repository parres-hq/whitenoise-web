<script lang="ts">
import Accordion from "$lib/components/Accordion.svelte";
import DownloadButton from "$lib/components/DownloadButton.svelte";
import FeatureSection from "$lib/components/FeatureSection.svelte";
import type { FeatureCard } from "$lib/types";

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

const faqs = [
    {
        question: "What makes White Noise different from other encrypted chat apps?",
        answer: "White Noise combines Nostr's decentralized architecture with the Messaging Layer Security (MLS) protocol, enabling end-to-end encrypted group chats at scale. Unlike centralized apps, there's no single point of failure, and MLS ensures even large groups (1000+ users) stay secure.",
    },
    {
        question: "How does encryption work in White Noise?",
        answer: "MLS provides *post-compromise security*: even if a device is compromised, future messages remain secure. Keys are dynamically rotated, and encryption is applied before messages hit Nostr relays, ensuring only group members can decrypt content.",
    },
    {
        question: "Can governments or ISPs block White Noise?",
        answer: "Nostr's decentralized design makes blocking nearly impossible. Users connect via independent relays (servers), which can be self-hosted or swapped freely. Combined with MLS encryption, this makes censorship exceptionally difficult.",
    },
    {
        question: "How does White Noise handle large groups without lag?",
        answer: "MLS optimizes key distribution efficiency, reducing overhead as groups grow. Nostr relays handle message routing, allowing horizontal scaling. Tests show groups with 1,000+ members perform smoothly.",
    },
    {
        question: "Where is my chat data stored?",
        answer: "Messages are encrypted and distributed across Nostr relays, but *never stored permanently*. Relays can't read your data, and you can prioritize privacy-focused relays or run your own.",
    },
    {
        question: "What happens if a relay goes offline?",
        answer: "Nostr's redundancy lets users connect to multiple relays simultaneously. If one fails, others ensure message delivery. Groups remain active as long as at least one relay is operational.",
    },
    {
        question: "Can admins remove or censor users in a group?",
        answer: "Yes. MLS allows admins to <strong>cryptographically evict</strong> users, revoking their access to future messages. Removed users can't rejoin without an invite, and past messages remain secure.",
    },
    {
        question: "Is White Noise open source?",
        answer: "Yes! Like most Nostr projects, White Noise is open source, allowing audits of its MLS implementation and fostering trust in its encryption claims.",
    },
    {
        question: "Can I use White Noise on multiple devices?",
        answer: "Absolutely. MLS supports 'leaf nodes' for each device, letting you join groups from phones, laptops, or tablets. Keys are securely stored on your device which allows each device to join the same groups.",
    },
    {
        question: "How does White Noise ensure long-term security as technology evolves?",
        answer: "White Noise leverages MLS's protocol agility, allowing seamless upgrades to quantum-resistant algorithms (e.g., CRYSTALS-Kyber) when standardized. Combined with Nostr's decentralized relay network—which can adopt new cryptographic primitives without central coordination—the system future-proofs itself against both computational advances and institutional interference.",
    },
];

let openFaqIndex: number | null = null;
</script>

<div class="hero flex flex-col md:flex-row items-center justify-between px-0 bg-glitch-950 bg-[url('/images/blocks-background.webp')] bg-no-repeat bg-center-bottom md:bg-right bg-cover">
    <div class="max-w-7xl mx-auto w-full flex flex-col md:flex-row items-center justify-between px-6 md:px-12">
        <div class="flex flex-col gap-4 max-w-xl flex-1 justify-center text-center md:text-left items-center md:items-start shrink-0">
            <h1 class="text-6xl font-bold text-glitch-50">White Noise</h1>
            <p class="text-xl text-glitch-200 font-medium">A truly secure and private messenger that's lightning fast, infinitely scalable, and identity-free.</p>
            <DownloadButton />
        </div>
        <div class="max-w-3xl shrink">
            <img src="/images/lady-noise.webp" alt="Lady Noise Statue" class="relative object-contain drop-shadow-2xl top-8" />
        </div>
    </div>
</div>

<div class="max-w-7xl mx-auto w-full px-6 md:px-12 my-8 flex flex-col gap-4 items-center">
    <h2 class="text-2xl font-medium text-glitch-800">Supported By</h2>
    <div class="flex flex-col md:flex-row gap-4 md:gap-x-8 my-4">
        <a href="https://opensats.org" target="_blank" class="py-4 px-8 md:py-6 md:px-12 bg-glitch-950 flex items-center justify-center w-64 hover:bg-glitch-800 transition-colors">
            <img src="/images/opensats.svg" alt="OpenSats Logo" class="max-w-48 w-40 bg-transparent" />
        </a>
        <a href="https://hrf.org" target="_blank" class="py-4 px-8 md:py-6 md:px-12 bg-glitch-950 flex items-center justify-center w-64 hover:bg-glitch-800 transition-colors">
            <img src="/images/hrf.svg" alt="Human Rights Foundation Logo" class="max-w-64" />
        </a>
    </div>
</div>

<div class="max-w-7xl mx-auto w-full">
    <div class="flex flex-col gap-8 md:gap-12 px-6 md:px-12 py-8 md:py-12 justify-center text-center md:text-left items-center md:items-start">
        {#each featureCards as card}
            <FeatureSection featureCard={card} />
        {/each}
    </div>
</div>

<!-- FAQ Section -->
<div class="max-w-3xl mx-auto w-full mt-8 mb-16 flex flex-col gap-2">
    {#each faqs as faq, i}
        <Accordion
            question={faq.question}
            answer={faq.answer}
            open={openFaqIndex === i}
            onClick={() => openFaqIndex = openFaqIndex === i ? null : i}
        />
    {/each}
</div>
