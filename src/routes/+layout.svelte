<script lang="ts">
	import '../app.postcss';
	import { AppShell, AppBar } from '@skeletonlabs/skeleton';
    import { AppRail, AppRailTile, AppRailAnchor } from '@skeletonlabs/skeleton';

    import { Home } from 'lucide-svelte/icons/house';
    import { NotePen } from 'lucide-svelte/icons/notebook-pen';
    import { Ruler } from 'lucide-svelte/icons/ruler';
    import { Settings } from 'lucide-svelte/icons/settings';

    let currentTitle: number = 0;
</script>

<!-- App Shell -->
<AppShell>
	<svelte:fragment slot="header">
		<!-- App Bar -->
		<AppBar>
			<svelte:fragment slot="lead">
				<strong class="text-xl uppercase">Skeleton</strong>
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
                <AppRailAnchor href="/" >
                    <Home class="w-6 h-6 text-gray-500" />
                </AppRailAnchor>
            </svelte:fragment>
            <!-- --- -->
            <AppRailTile bind:group={currentTitle} name="Progress" value={0} title="Progress">
                <svelte:fragment slot="lead">
                    <NotePen class="w-6 h-6 text-gray-500" />
                    <span>Progress</span>
                </svelte:fragment>
            </AppRailTile>
            <AppRailTile bind:group={currentTitle} name="Scale" value={0} title="Scale">
                <svelte:fragment slot="lead">
                    <Ruler class="w-6 h-6 text-gray-500" />
                    <span>Scale</span>
                </svelte:fragment>
            </AppRailTile>
            <AppRailTile bind:group={currentTitle} name="Settings" value={0} title="Settings">
                <svelte:fragment slot="lead">
                    <Settings class="w-6 h-6 text-gray-500" />
                    <span>Scale</span>
                </svelte:fragment>
            </AppRailTile>
        </AppRail>
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
</AppShell>
