<script>
    import Input from '$lib/components/Input.svelte';
    import Button from '$lib/components/Button.svelte';
    let email = '';
    let password = '';
    let confirmPassword = '';

    let error;

    function validatePassword(password, confirmPassword) {
        return confirmPassword !== password 
    }
</script>
<form method="POST" class="space-y-5 {$$props.class}">
    <Input label="Email" id="email" name="email" type="email" bind:value={email} required />
    <Input label="Password" id="password" name="password" type="password" bind:value={password} required />
    <Input
        label="Confirm Password"
        id="confirm-password"
        name="confirm-password"
        type="password"
        bind:value={confirmPassword}
        required
    />
    {#if confirmPassword !== "" && confirmPassword !== password}
        <p class="text-red-600 text-sm font-semibold">Password not match</p>
    {/if}
    <Button type="submit" disabled="{validatePassword(password, confirmPassword)}">Sign Up</Button>
</form>
