<script>
  import { page } from "$app/stores";
  import { onMount } from "svelte";
  import Moon from "./icons/moon.svelte";
  import Sun from "./icons/sun.svelte";

  const navs = [
    {
      title: "메인",
      href: "/",
    },
    {
      title: "수상실적",
      href: "/about",
    },
    {
      title: "커리큘럼",
      href: "/services",
    },
    {
      title: "동아리 신청",
      href: "/contact",
    },
    {
      title: "블로그",
      href: "/blog",
    },
  ];

  let currentTheme = "";

  onMount(() => {
    const userPrefersDarkMode = window.matchMedia(
      "(prefers-color-scheme: dark)"
    ).matches;

    const hasUserSetDarkModeManually =
      document.documentElement.dataset.theme == "dark";

    if (!hasUserSetDarkModeManually) {
      setTheme(userPrefersDarkMode ? "dark" : "light");
    }
  });

  const setTheme = (/** @type {string | undefined} */ theme) => {
    document.documentElement.dataset.theme = theme;
    document.cookie = `siteTheme=${theme};max-age=31536000;path="/"`;
    // @ts-ignore
    currentTheme = theme;
  };

  $: url = $page.url.href;
  $: routeId = $page.url.pathname;
</script>

<nav>
  <div class="container">
    <a class="logo" href="/">
      <h1>SSR</h1>
    </a>
    <ul>
      {#each navs as { title, href }}
        <li>
          <a
            {href}
            class:active={href === "/" ? routeId === "/" : url.includes(href)}
            {title}>{title}</a
          >
        </li>
      {/each}
      <li class="relative">
        {#if currentTheme == "light"}
          <a class="moon" href={"#"} on:click={() => setTheme("dark")}>
            <Moon />
          </a>
        {:else}
          <a class="sun" href={"#"} on:click={() => setTheme("light")}>
            <Sun />
          </a>
        {/if}
      </li>
    </ul>
  </div>
</nav>

<style>
  nav {
    padding: 0.5em;
    background-color: #343a40;
    color: white;
  }

  .container {
    display: flex;
    align-items: center;
  }

  ul {
    display: flex;
    margin: 0;
    margin-left: auto;
    list-style: none;
    font-size: 1em;
  }
  li {
    margin-right: 20px;
  }
  h1 {
    margin: 0;
    font-size: 1.3em;
    font-weight: normal;
  }
  a {
    text-decoration: none;
    color: #aaa;
  }
  .logo {
    color: white;
  }
  .active {
    color: white;
  }
</style>
