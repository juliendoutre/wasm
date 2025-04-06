<script>
    import {
        Navbar,
        NavBrand,
        DarkMode,
        ToolbarButton,
        Tooltip,
        Footer,
        FooterCopyright,
        Sidebar,
        SidebarGroup,
        SidebarItem,
        SidebarWrapper,
    } from "flowbite-svelte";
    import { GithubSolid } from "flowbite-svelte-icons";
    import { page } from "$app/state";
    import { base } from "$app/paths";
    import "../app.css";

    let { children } = $props();
    let activeUrl = $derived(page.url.pathname);
</script>

<Navbar class="px-2 sm:px-4 py-2.5 w-full z-20 top-0 start-0 border-b fixed">
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

<div class="overflow-scroll pb-16 mt-20">
    <div class="flex px-4 mx-auto w-full">
        <Sidebar {activeUrl} asideClass="w-54 fixed">
            <SidebarWrapper
                divClass="overflow-y-auto py-4 px-3 rounded dark:bg-gray-800"
            >
                <SidebarGroup>
                    <SidebarItem label="Welcome" href={base}></SidebarItem>
                    <SidebarItem label="Level 1" href={`${base}/level1`}
                    ></SidebarItem>
                </SidebarGroup>
            </SidebarWrapper>
        </Sidebar>

        <main class="ml-52 w-full mx-auto mr-10">
            {@render children?.()}
        </main>
    </div>
</div>

<Footer footerType="logo">
    <hr class="my-6 border-gray-200 sm:mx-auto dark:border-gray-700 lg:my-8" />
    <FooterCopyright
        href="https://juliendoutre.github.io/warec"
        by="Made with ❤️ in Paris and hosted on GitHub Pages"
    />
</Footer>
