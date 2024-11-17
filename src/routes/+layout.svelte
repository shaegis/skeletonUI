<script lang="ts">
	import '../app.postcss';
	import { AppShell, AppBar } from '@skeletonlabs/skeleton';
    import { AppRail, AppRailTile, AppRailAnchor } from '@skeletonlabs/skeleton';

    import Home from '$lib/icons/home.svg';
    import Progress from '$lib/icons/progress.svg';
    import Scale from '$lib/icons/scale.svg';
    import Settings from '$lib/icons/settings.svg';

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
                    <img src={Home} alt="Home" />
                    <span>Home</span>
                </AppRailAnchor>
            </svelte:fragment>
            <!-- --- -->
            <AppRailTile bind:group={currentTitle} name="Progress" value={0} title="Progress">
                <svelte:fragment slot="lead">
                    <img src={Progress} alt="Progress" />
                    <span>Progress</span>
                </svelte:fragment>
            </AppRailTile>
            <AppRailTile bind:group={currentTitle} name="Scale" value={0} title="Scale">
                <svelte:fragment slot="lead">
                    <img src={Scale} alt="Scale" />
                    <span>Scale</span>
                </svelte:fragment>
            </AppRailTile>
            <AppRailTile bind:group={currentTitle} name="Settings" value={0} title="Settings">
                <svelte:fragment slot="lead">
                    <img src={Settings} alt="Settings" />
                    <span>Settings</span>
                </svelte:fragment>
            </AppRailTile>
        </AppRail>
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
</AppShell>
