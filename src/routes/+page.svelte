<script lang="ts">
    import { Command } from '@tauri-apps/api/shell'
	import { onMount } from 'svelte';

    let string = "";

    onMount(async () => {
        const command = Command.sidecar('bin/python/test')
        const output = await command.execute()
        const { stdout, stderr } = output;
        string = stdout;
    });
</script>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
<p>Output from python: {string}</p>