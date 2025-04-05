<script>
    import {
        Navbar,
        NavBrand,
        DarkMode,
        ToolbarButton,
        Tooltip,
        Footer,
        FooterCopyright,
    } from "flowbite-svelte";
    import { GithubSolid } from "flowbite-svelte-icons";
    import { base } from "$app/paths";
</script>

<Navbar class="px-2 sm:px-4 py-2.5 fixed w-full z-20 top-0 start-0 border-b">
    <NavBrand href={base}>
        <span
            class="self-center whitespace-nowrap text-xl font-semibold dark:text-white"
        >
            WAREC
        </span>
    </NavBrand>
    <div class="flex items-center ml-auto">
        <ToolbarButton
            size="lg"
            target="_blank"
            rel="noreferrer"
            href="https://github.com/juliendoutre/warec"
            class="dark:hover:text-white hover:text-gray-900"
        >
            <GithubSolid />
        </ToolbarButton>
        <Tooltip class="dark:bg-gray-900" placement="bottom"
            >View on GitHub</Tooltip
        >
        <DarkMode
            class="inline-block dark:hover:text-white hover:text-gray-900"
        />
        <Tooltip class="dark:bg-gray-900" placement="bottom"
            >Toogle dark mode</Tooltip
        >
    </div>
</Navbar>

<Footer footerType="logo">
    <hr class="my-6 border-gray-200 sm:mx-auto dark:border-gray-700 lg:my-8" />
    <FooterCopyright
        href="https://juliendoutre.github.io/warec"
        by="Made with ❤️ in Paris and hosted on GitHub Pages"
    />
</Footer>
