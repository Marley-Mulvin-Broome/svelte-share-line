<script lang="ts">
	/**
	 * The url to share
	 */
	export let url: string;

	/**
	 * Accessibility label that will be shown on the parent <a> tag.
	 */
	export let ariaLabel = 'Share on Line';

	/**
	 * Whether to display the icon
	 */
	export let showIcon = true;

	/**
	 * Whether to fill the icon or not.
	 */
	export let fill = true;

	let classes = '';

	export { classes as class };

	$: href = encodeURI(`https://social-plugins.line.me/lineit/share?url=${url}`);
	$: fillClass = fill ? 'share-line__icon--fill' : 'share-line__icon--outline';
</script>

<a class="share-line__link" {href} target="_black" rel="noopener noreferrer" aria-label={ariaLabel}>
	<div class="share-line__button {classes}">
		{#if showIcon}
			<div class="share-line__icon {fillClass}" aria-hidden="true">
				<svg aria-label="LINE" viewBox="0 0 512 512" xmlns="http://www.w3.org/2000/svg">
					<path
						d="M512.017 227.437c-2.734 61.513-28.706 103.889-69.715 140.796-72.448 64.247-187.272 143.53-202.308 131.227-15.037-19.137 28.706-64.246-27.34-71.08C92.365 411.975.778 327.224.778 227.436c0-112.09 116.191-205.042 256.987-205.042 140.796 0 258.354 92.953 254.253 205.042z"
						fill="#fff"
						style="stroke-width:1.36695"
						transform="translate(0 -5.565)"
					/><path
						d="M413.596 223.24H367.12m46.476-49.21h-49.21v98.42h49.21m-168.135 0v-98.42l73.816 98.42v-98.42m-121.659 98.42v-98.42m-90.218 0v98.42h50.577"
						fill="none"
						stroke="#00b900"
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="24.25"
					/>
				</svg>
			</div>
		{/if}
		<slot />
	</div>
</a>

<style>
	.share-line__link {
		display: var(--share-link-display, inline-block);
		text-decoration: var(--share-link-text-decoration, none);
		color: var(--share-link-color, #fff);
	}

	.share-line__button {
		display: flex;
		flex-direction: row;
		justify-content: var(--share-button-justify-content, space-between);
		align-items: center;

		gap: var(--share-button-gap, 0.5em);

		padding: var(--share-padding, 0.75em);
		background-color: var(--share-button-background-color, #00b900);
	}

	.share-line__button:active,
	.share-line__button:hover {
		background-color: var(--share-button-hover-color, #00b900);
	}

	.share-line__icon svg {
		width: var(--share-icon-width, 2em);
		height: var(--share-icon-height, 2em);
		margin: 0;
		padding: 0;
		vertical-align: middle;
	}

	.share-line__icon--fill {
		fill: var(--share-icon-color, #fff);
		stroke: none;
	}

	.share-line__icon--outline {
		fill: none;
		stroke: var(--share-icon-color, #fff);
	}
</style>
