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
        answer: "White Noise offers true decentralization, identity freedom, and advanced cryptography, making it more private and censorship-resistant than traditional encrypted messengers.",
    },
    {
        question: "How does encryption work in White Noise?",
        answer: "All messages are end-to-end encrypted using the MLS protocol, ensuring only intended recipients can read your messages. Forward secrecy and post-compromise security are built in.",
    },
    {
        question: "Can governments or ISPs block White Noise?",
        answer: "Nostr's decentralized design makes blocking nearly impossible. Users connect via independent relays, which can be self-hosted or swapped freely (and can even be connected to via Tor). Combined with MLS encryption, this makes censorship exceptionally difficult.",
    },
    {
        question: "Where is my chat data stored?",
        answer: "Your data is stored on the relays you choose to use. You can run your own relay for maximum privacy, or use trusted community relays.",
    },
    {
        question: "What happens if a relay goes offline?",
        answer: "You can seamlessly switch to another relay, or run your own. Your identity and contacts are portable, so you're never locked in.",
    },
    {
        question: "Can admins remove or censor users in a group?",
        answer: "Within a group, the group admins can remove a user but while the user is in the group, they can't be censored. There isn't any way for White Noise or anyone else on the Nostr network to stop a user from using Nostr and creating their own groups.",
    },
    // {
    //     question: "Can I use White Noise on multiple devices?",
    //     answer: "Yes, you can use White Noise on multiple devices.",
    // },
    {
        question: "Is White Noise open source?",
        answer: "Yes, White Noise is open source. You can view the source code on GitHub.",
    },
    {
        question: "Is White Noise a non-profit?",
        answer: "Yes, White Noise is run by a non-profit called Parres. We are not funded by any corporation, and we are not beholden to any government or organization.",
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
