<script lang='ts'>
  	import CustomAppBar from '../lib/CustomAppBar.svelte';
  	import CustomFooter from '../lib/CostumeFooter.svelte'

	// The ordering of these imports is critical to your app working properly
	import '@skeletonlabs/skeleton/themes/theme-modern.css';
	// If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
	import '@skeletonlabs/skeleton/styles/skeleton.css';
	// Most of your app wide CSS should be put in this file
	import '../app.postcss';
	import { AppShell, AppBar, Avatar } from '@skeletonlabs/skeleton';




	//For vercel analytics
	import { dev } from '$app/environment';
  	import { inject } from '@vercel/analytics';
  	inject({ mode: dev ? 'development' : 'production' });
	//For Vercel speed insights
	import WebVitals from '@rairulyle/svelte-web-vitals';
</script>

<WebVitals />
<!-- App Shell -->
<AppShell>
	<svelte:fragment slot="header">
		<!-- App Bar -->
		<CustomAppBar/>
		
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
	<CustomFooter/>
</AppShell>
