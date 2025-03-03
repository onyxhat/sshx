<script lang="ts">
  import {
    CastIcon,
    HardDriveIcon,
    ImageIcon,
    LockIcon,
    RefreshCwIcon,
    Share2Icon,
  } from "svelte-feather-icons";
  import logotypeDark from "$lib/assets/logotype-dark.svg";
  import landingGraphic from "$lib/assets/landing-graphic.svg";
  import landingBackground from "$lib/assets/landing-background.svg";
  import TeaserImage from "$lib/ui/TeaserImage.svelte";
  import { onMount } from "svelte";

  let installationEl: HTMLDivElement;

  const installs = [
    {
      title: "macOS / Linux",
      steps: `curl -sSf https://sshx.io/get | sh`,
    },
    {
      title: "Rust (from source)",
      steps: `cargo install sshx`,
    },
  ];

  const socials = [
    {
      title: "🤖\xa0 GitHub",
      href: "https://github.com/ekzhang/sshx",
    },
    {
      title: "🌸\xa0 Twitter",
      href: "https://twitter.com/ekzhang1",
    },
    {
      title: "💌\xa0 Email",
      href: "mailto:ekzhang1@gmail.com",
    },
    {
      title: "🌎\xa0 Website",
      href: "https://www.ekzhang.com",
    },
  ];

  let selectedInstall = installs[0];
  let url = ``;

  function scrollToInstallation() {
    installationEl.scrollIntoView({ behavior: "smooth" });
  }

  onMount(() => url = window.location.href);
</script>

<div class="overflow-x-hidden absolute inset-0">
  <main class="max-w-screen-xl mx-auto px-4 md:px-8 lg:px-16">
    <header class="my-12">
      <img class="h-16 -mx-1" src={logotypeDark} alt="sshx logo" />
    </header>
    <h1>
      A secure web-based,
      <span class="title-gradient">collaborative</span> terminal
    </h1>

    <div class="relative">
      <div
        class="absolute scale-150 md:scale-100 md:left-[180px] md:top-[-200px] md:w-[1000px] -z-10"
      >
        <img class="select-none" src={landingBackground} alt="" />
      </div>
      <div class="md:absolute md:left-[500px] md:w-[1000px]">
        <img
          class="mt-5 mb-8 w-[720px]"
          width={813}
          height={623}
          src={landingGraphic}
          alt="two terminal windows running sshx and three live cursors"
        />
      </div>
    </div>

    <section class="my-12 space-y-6 text-lg md:max-w-[460px] text-zinc-400">
      <p>
        <code>sshx</code> lets you share your terminal with anyone by link, on a
        <b>multiplayer infinite canvas</b>.
      </p>
      <p>
        It has <b>real-time collaboration</b>, with remote cursors and chat.
        It's also <b>fast</b> and <b>end-to-end encrypted</b>, with a
        lightweight server written in Rust.
      </p>
      <p>
        Install <code>sshx</code> with a single command. Use it for teaching, debugging,
        or cloud access.
      </p>
    </section>

    <div class="pb-12 md:pb-36">
      <button
        class="bg-pink-700 hover:bg-pink-600 active:ring-4 active:ring-pink-500/50 text-lg font-semibold px-8 py-2 rounded-full"
        on:click={scrollToInstallation}
      >
        Get Started
      </button>
    </div>

    <div
      class="mt-8 md:mt-32 grid md:grid-cols-2 xl:grid-cols-3 gap-4 md:gap-6"
    >
      <div class="feature-block">
        <div class="feature-icon">
          <CastIcon size="14" />
        </div>
        <h3>Collaborative</h3>
        <p>Invite people by sharing a secure, unique browser link.</p>
      </div>
      <div class="feature-block">
        <div class="feature-icon">
          <HardDriveIcon size="14" />
        </div>
        <h3>Cross-platform</h3>
        <p>Install the client in under a second, on macOS and Linux.</p>
      </div>
      <div class="feature-block">
        <div class="feature-icon">
          <ImageIcon size="14" />
        </div>
        <h3>Infinite canvas</h3>
        <p>
          Create several terminals, then arrange and resize them in real time.
        </p>
      </div>
      <div class="feature-block">
        <div class="feature-icon">
          <RefreshCwIcon size="14" />
        </div>
        <h3>Live presence</h3>
        <p>See other people's names and cursors while they're connected.</p>
      </div>
      <div class="feature-block">
        <div class="feature-icon">
          <LockIcon size="14" />
        </div>
        <h3>End-to-end encrypted</h3>
        <p>
          Send terminal data securely; the server never sees what you're typing.
        </p>
      </div>
      <div class="feature-block">
        <div class="feature-icon">
          <Share2Icon size="14" />
        </div>
        <h3>Ultra-fast mesh networking</h3>
        <p>
          Connect from anywhere to the nearest distributed peer in a global
          network.
        </p>
      </div>
    </div>

    <div class="my-48 hidden md:block">
      <TeaserImage />
    </div>

    <h2 bind:this={installationEl} class="mt-40 mb-16">
      Get started in <span class="title-gradient">two quick steps</span>
    </h2>

    <div
      class="mx-auto max-w-screen-lg grid lg:grid-cols-2 gap-16 lg:text-center mb-12 text-lg text-zinc-300"
    >
      <div class="space-y-6">
        <h3 class="step-heading">
          <span class="pill mr-3">1</span> Install the CLI
        </h3>
        <p class="text-zinc-400">
          Get <code>sshx</code> by running this command. It's tiny and downloads
          in seconds (3 MB).
        </p>
        <div class="flex flex-col items-start text-base">
          <div class="flex rounded-t text-sm bg-zinc-900">
<!--
            {#each installs as method}
              <button
                class="px-2 py-1 border-l border-t last:border-r border-zinc-500 first:rounded-tl last:rounded-tr"
                class:bg-zinc-700={selectedInstall === method}
                on:click={() => (selectedInstall = method)}
              >
                {method.title}
              </button>
            {/each}
            -->
            <button
            class="px-2 py-1 border-l border-t last:border-r border-zinc-500 first:rounded-tl last:rounded-tr"
          >
            macOS / Linux
          </button>

          </div>
          <pre class="rounded-b rounded-r w-full">curl -sSf {url}get | sh</pre>
        </div>

        <p class="text-zinc-400">
          You can also build it <a
            target="_blank"
            rel="noreferrer"
            class="underline underline-offset-2 text-zinc-300"
            href="https://github.com/ekzhang/sshx">from source</a
          >, if you'd like.
        </p>
      </div>
      <div class="space-y-6">
        <h3 class="step-heading">
          <span class="pill mr-3">2</span> Share your terminal
        </h3>

        <p class="text-zinc-400">Run this command in your favorite terminal.</p>

        <pre class="rounded">sshx</pre>

        <p class="text-zinc-400">
          This kicks off a live, encrypted session. Open the link in your web
          browser to join.
        </p>
      </div>
    </div>

    <hr class="mt-40 mb-12" />

    <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-4 md:gap-6 mb-6">
      {#each socials as social}
        <a
          target="_blank"
          rel="noreferrer"
          href={social.href}
          class="border border-zinc-700 hover:bg-zinc-900 transition-colors p-4 text-center text-lg font-medium rounded-lg"
        >
          {social.title}
        </a>
      {/each}
    </div>

    <p class="mb-12 text-center text-zinc-400">
      open source, &copy; Eric Zhang 2023
    </p>
  </main>
</div>

<style lang="postcss">
  h1 {
    @apply font-bold text-4xl sm:text-5xl max-w-[26ch] py-2;
    line-height: 1.15;
  }

  h2 {
    @apply font-bold text-3xl sm:text-4xl md:text-center scroll-mt-16;
  }

  b {
    @apply text-zinc-300 font-semibold;
  }

  code {
    @apply text-[0.9em] text-zinc-200 font-medium bg-zinc-700 px-1 py-0.5 rounded;
  }

  pre {
    @apply bg-zinc-900 p-3 whitespace-pre-wrap border border-zinc-500;
  }

  hr {
    @apply mx-auto md:w-1/2 border-zinc-800;
  }

  .title-gradient {
    @apply text-transparent bg-clip-text bg-gradient-to-r from-fuchsia-400 to-blue-500;
  }

  .feature-block {
    @apply relative border rounded-lg border-transparent p-6 sm:p-8;
    background: #111111 padding-box;
  }

  .feature-block::before {
    content: "";
    @apply absolute inset-0;
    z-index: -1;
    margin: -1px;
    border-radius: inherit;
    background: linear-gradient(
      160deg,
      rgba(255, 255, 255, 0.36) 5%,
      rgba(255, 255, 255, 0.08) 25%,
      rgba(255, 255, 255, 0.24) 50%,
      rgba(255, 255, 255, 0.08) 75%,
      rgba(255, 255, 255, 0.28) 95%
    );
    opacity: 0.5;
    transition: opacity 200ms;
  }

  .feature-block:hover::before {
    opacity: 1;
  }

  .feature-block h3 {
    @apply font-semibold mb-2;
  }

  .feature-block p {
    @apply text-zinc-400;
  }

  .feature-icon {
    @apply inline-block p-3 rounded-full mb-3 shadow-md border border-zinc-600;
  }

  .step-heading {
    @apply text-2xl text-zinc-200 font-semibold flex items-center md:justify-center;
  }

  .pill {
    @apply flex justify-center items-center w-7 h-7 rounded-full;
    @apply text-base font-normal border border-current;
  }
</style>
