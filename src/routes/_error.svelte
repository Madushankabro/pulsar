<script lang="ts">
  export let status: number
  export let error: Error

  const dev = process.env.NODE_ENV === 'development'
</script>

<style>
  h1, p {
    margin: 0 auto;
  }

  h1 {
    font-size: 2.8em;
    font-weight: 700;
    margin: 0;
  }

  a {
    color: #91AADF;
  }

  p {
    margin: 1em auto;
  }

  @media (min-width: 480px) {
    h1 {
      font-size: 4em;
    }
  }
</style>

<main>
  <h1>Error {status}</h1>

  <p>{error.message}</p>

  {#if dev && error.stack}
    <pre>{error.stack}</pre>
  {/if}

  <h3>
    Get help for this error in
      <a href="https://discord.gg/zsxwgYc">Discord</a> or report it on
      <a href="https://github.com/spacebin-org/pulsar">Github</a>.
  </h3>
</main>
