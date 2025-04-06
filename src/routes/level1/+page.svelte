<script>
    import { Heading, P, A, Alert } from "flowbite-svelte";
    import { hash } from "$lib/levels/level1";
</script>

<Heading class="p-8" tag="h1">Level 1</Heading>

<P class="px-8 py-4"
    >This is a warm-up. The <A href="https://github.com/WebAssembly/wabt"
        >WebAssembly Binary Toolkit</A
    > should contain intereting tools for you to use.</P
>

<Alert color="blue">
    This level's hash is: <code>{hash()}</code>
</Alert>
