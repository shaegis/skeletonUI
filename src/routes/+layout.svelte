<script lang="ts">
	import '../app.postcss';
	import { AppShell, AppBar } from '@skeletonlabs/skeleton';
    import { AppRail, AppRailTile, AppRailAnchor } from '@skeletonlabs/skeleton';
    import { Home, Pencil as Progress, Ruler as Scale, Settings, MoveLeft } from 'lucide-svelte';
    import { page } from '$app/stores';

    export let title = 'Cranking - Let\'s Crank Out!';

    let showBackButton = false;

    $: {
        const currentPath = $page.url.pathname;
        showBackButton = currentPath !== '/';
    }
</script>

<header>
    <AppBar>
        <svelte:fragment slot="lead">
            {#if showBackButton}
                <button 
                    type="button"
                    on:click={() => window.history.back()}
                    on:keydown={(e) => { if (e.key === 'Enter' || e.key === ' ') window.history.back(); }}
                    aria-label="Go Back"
                >
                    <!-- MoveLeft 아이콘 -->
                    <MoveLeft />
                </button>
            {/if}
            <span>{title}</span>
        </svelte:fragment>
        <svelte:fragment slot="trail">
            <a
                class="btn btn-sm variant-ghost-surface"
                href="https://discord.gg/EXqV7W8MtY"
                target="_blank"
                rel="noreferrer"
            >
                Discord
            </a>
            <a
                class="btn btn-sm variant-ghost-surface"
                href="https://twitter.com/SkeletonUI"
                target="_blank"
                rel="noreferrer"
            >
                Twitter
            </a>
            <a
                class="btn btn-sm variant-ghost-surface"
                href="https://github.com/skeletonlabs/skeleton"
                target="_blank"
                rel="noreferrer"
            >
                GitHub
            </a>
        </svelte:fragment>
    </AppBar>
</header>

<AppRail>
    <svelte:fragment slot="lead">
        <AppRailAnchor href="/">
                <Home />
        </AppRailAnchor>
        <AppRailAnchor href="/progress">
                <Progress />
        </AppRailAnchor>
        <AppRailAnchor href="/scale">
                <Scale />
        </AppRailAnchor>
        <AppRailAnchor href="/settings"> 
                <Settings />
        </AppRailAnchor>
    </svelte:fragment>
</AppRail>

<!-- Page Route Content -->
<main>
    <slot />
</main>
