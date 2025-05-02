<script lang="ts">
import "../app.css";
import Footer from "$lib/components/Footer.svelte";
import Header from "$lib/components/Header.svelte";

const { children } = $props();
</script>


<Header />
{@render children()}
<Footer />
