<script>
	let { label, variant = 'primary' } = $props();
</script>

<button class="btn" class:secondary={variant === 'secondary'}>
	{label}
</button>

<style lang="scss">
	@use 'src/lib/styles/_variables' as v;
	@use 'src/lib/styles/_mixins' as m;

	.btn {
		@include m.button-base;
		@include m.rounded;
		@include m.flex-center;

		background: v.$primary;
		color: white;

		&:hover {
			background: v.$primary-hover;
			transform: translateY(-1px);
		}

		&:active {
			transform: translateY(0);
		}

		&.secondary {
			background: transparent;
			color: v.$primary;
			border: 2px solid v.$primary;

			&:hover {
				background: v.$primary;
				color: white;
			}
		}
	}
</style>
