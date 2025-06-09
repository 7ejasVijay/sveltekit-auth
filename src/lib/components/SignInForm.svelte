<script>
  import Input from "$lib/components/Input.svelte";
  import Button from "$lib/components/Button.svelte";

  let email = "";
  let password = "";
</script>

<form method="POST" class="space-y-5 {$$props.class}">
  <Input label="Email" id="email" type="email" bind:value={email} required />
  <Input label="Password" id="password" type="password" bind:value={password} required />
  <Button type="submit">Sign In</Button>
</form>
