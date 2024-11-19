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

<!-- App Shell -->
<AppShell>
	<svelte:fragment slot="header">
		<!-- App Bar -->
		<AppBar>
			<svelte:fragment slot="lead">
                <div class="flex items-center gap-2">
                    {#if showBackButton}
                        <button 
                            type="button"
                            class="variant-soft-primary flex items-center justify-center w-10 h-10 sm:w-12 sm:h-12 lg:w-14 lg:h-14 cursor-pointer"
                            on:click={() => window.history.back()}
                            on:keydown={(e) => { if (e.key === 'Enter' || e.key === ' ') window.history.back(); }}
                            aria-label="Go Back"
                        >
                            <!-- MoveLeft 아이콘 -->
                            <MoveLeft class="w-6 h-6 sm:w-8 sm:h-8 lg:w-10 lg:h-10" />
                        </button>
                    {/if}
                    <span class="text-primary font-bold text-lg sm:text-xl uppercase">{title}</span>
                </div>
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
        <AppRail>
            <svelte:fragment slot="lead">
                <AppRailAnchor href="/" class="variant-soft-primary flex items-center justify-center text-center w-12 h-12 sm:w-14 sm:h-14 lg:w-16 lg:h-16">
                        <Home class="w-6 h-6 sm:w-8 sm:h-8 lg:w-10 lg:h-10" />
                </AppRailAnchor>
					
                <!-- --- -->
                <AppRailAnchor href="/progress" class="variant-soft-primary flex items-center justify-center w-12 h-12 sm:w-14 sm:h-14 lg:w-16 lg:h-16">
                        <Progress class="w-6 h-6 sm:w-8 sm:h-8 lg:w-10 lg:h-10" />
                </AppRailAnchor>
                <AppRailAnchor href="/scale" class="variant-soft-primary flex items-center justify-center w-12 h-12 sm:w-14 sm:h-14 lg:w-16 lg:h-16">
                        <Scale class="w-6 h-6 sm:w-8 sm:h-8 lg:w-10 lg:h-10" />
                </AppRailAnchor>
                <AppRailAnchor href="/settings" class="variant-soft-primary flex items-center justify-center w-12 h-12 sm:w-14 sm:h-14 lg:w-16 lg:h-16">
                        <Settings class="w-6 h-6 sm:w-8 sm:h-8 lg:w-10 lg:h-10" />
                </AppRailAnchor>
            </svelte:fragment>
        </AppRail>
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
</AppShell>
