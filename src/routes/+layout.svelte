<script lang="ts">
	import '../app.postcss';
	import { AppShell, AppBar } from '@skeletonlabs/skeleton';
    import { AppRail, AppRailTile, AppRailAnchor } from '@skeletonlabs/skeleton';

    import { Home, Pencil as Progress, Ruler as Scale, Settings } from 'lucide-svelte';

</script>

<style>
    .icon-container {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100%;
        font-size: 1rem; /* 기본 아이콘 크기 설정 */
    }

    /* 화면 크기에 따라 동적으로 font-size 조정 */
    @media (min-width: 768px) {
        .icon-container {
            font-size: 1.5rem; /* 태블릿 */
        }
    }

    @media (min-width: 1024px) {
        .icon-container {
            font-size: 2rem; /* 데스크톱 */
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
                <AppRailAnchor href="/" >
                    <div class="icon-container text-secondary">
                        <Home />
                    </div>
                </AppRailAnchor>
					
                <!-- --- -->
                <AppRailAnchor href="/progress" >
                    <div class="icon-container text-secondary">
                        <Progress />
                    </div>
                </AppRailAnchor>
                <AppRailAnchor href="/scale" >
                    <div class="icon-container text-secondary">
                        <Scale />
                    </div>
                </AppRailAnchor>
                <AppRailAnchor href="/settings">
                    <div class="icon-container text-secondary">
                        <Settings />
                    </div>
                </AppRailAnchor>
            </svelte:fragment>
        </AppRail>
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
</AppShell>
