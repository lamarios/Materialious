<script lang="ts">
	import type { PlaylistPageVideo, Video, VideoBase } from './Api/model';
	import Thumbnail from './Thumbnail.svelte';

	export let videos: VideoBase[] | Video[] | Notification[] | PlaylistPageVideo[] = [];
	export let oneItemPerRow: boolean = false;
	export let playlistId: string = '';
</script>

<div class="page right active">
	<div class="space"></div>
	<div class="grid">
		{#each videos as video}
			<div class={`s12 m${oneItemPerRow ? '12' : '6'} l${oneItemPerRow ? '12' : '2'}`}>
				<article class="no-padding" style="height: 100%;">
					<Thumbnail {video} {playlistId} />
				</article>
			</div>
		{/each}
	</div>
</div>
