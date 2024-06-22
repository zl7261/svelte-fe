<script lang="ts">
    import { onMount } from 'svelte';

    let from = '';
    let to = '';
    let cc = '';
    let bcc = '';
    let subject = '';
    let body = '';

    const handleSubmit = (e) => {
        e.preventDefault();
        console.log({ from, to, cc, bcc, subject, body });
    }
</script>

<form on:submit={handleSubmit} class="space-y-4">
    <div>
        <label class="block">From:</label>
        <input type="email" bind:value={from} class="input" required />
    </div>
    <div>
        <label class="block">To:</label>
        <input type="email" bind:value={to} class="input" required />
    </div>
    <div>
        <label class="block">Cc:</label>
        <input type="email" bind:value={cc} class="input" />
    </div>
    <div>
        <label class="block">Bcc:</label>
        <input type="email" bind:value={bcc} class="input" />
    </div>
    <div>
        <label class="block">Subject:</label>
        <input type="text" bind:value={subject} class="input" required />
    </div>
    <div>
        <label class="block">Email Body:</label>
        <textarea bind:value={body} class="textarea" required></textarea>
    </div>
    <button type="submit" class="btn btn-primary">Send Email</button>
</form>

<style>
    .input, .textarea, .btn {
        @apply block w-full mt-1 p-2 border rounded;
    }
    .btn {
        @apply bg-blue-500 text-white;
    }
</style>
