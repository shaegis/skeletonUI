<script lang="ts">
	import '../app.postcss';
	import { AppShell, AppBar } from '@skeletonlabs/skeleton';
    import { AppRail, AppRailTile, AppRailAnchor } from '@skeletonlabs/skeleton';

    import Home from '$lib/icons/home.svg';
    import Progress from '$lib/icons/progress.svg';
    import Scale from '$lib/icons/scale.svg';
    import Settings from '$lib/icons/settings.svg';

</script>

<style>
    .icon-container {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100%;
    }

    .icon-container img {
        width: 20px;
        height: 20px;
    }

    @media (min-width: 768px) {
        .icon-container img {
            width: 32px;
            height: 32px;
        }
    }

    @media (min-width: 1024px) {
        .icon-container img {
            width: 40px;
            height: 40px;
        }
    }
</style>

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
                <AppRailAnchor href="/" style="color: white;">
                    <div class="icon-container text-secondary">
                        <img src={Home} alt="Home" />
                    </div>
                </AppRailAnchor>
					
                <!-- --- -->
                <AppRailAnchor href="/progress" >
                    <div class="icon-container">
                        <img src={Progress} alt="Progress" />
                    </div>
                </AppRailAnchor>
                <AppRailAnchor href="/scale" >
                    <div class="icon-container">
                        <img src={Scale} alt="Scale" />
                    </div>
                </AppRailAnchor>
                <AppRailAnchor href="/settings" >
                    <div class="icon-container">
                        <img src={Settings} alt="Settings" />
                    </div>
                </AppRailAnchor>
            </svelte:fragment>
        </AppRail>
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
</AppShell>
