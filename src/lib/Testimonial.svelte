<script lang="ts">
  export let colorScheme: "purple" | "grey" | "white" | "black";
  export let wide: boolean;
  export let tall: boolean;
  export let avatar: string;
  export let name: string;
  export let title: string;
  export let heading: string;
</script>

<article class="card color-{colorScheme}" class:wide class:tall>
  <div class="author">
    <img class="author-avatar" src={avatar} alt={name} />
    <div class="author-name">{name}</div>
    <div class="author-title">{title}</div>
  </div>
  <strong class="heading">{heading}</strong>
  <p class="content">
    <slot />
  </p>
</article>

<style>
  .card {
    border-radius: 0.5rem;
    overflow: hidden;
    padding: 1rem;

    display: flex;
    flex-direction: column;
    gap: 1rem;
  }
  .author {
    display: grid;
    grid-template-columns: auto 1fr;
    grid-auto-flow: row dense;
    row-gap: 0.5rem;
    column-gap: 1rem;
  }
  .author-avatar {
    grid-row: span 2;
    border-radius: 50%;
    border: 2px solid hotpink;
    height: 3rem;
    width: 3rem;
  }
  .content {
    margin: 0;
  }
  .color-purple {
    background-color: rebeccapurple;
    color: white;
  }
  .color-grey {
    background-color: grey;
    color: white;
  }
  .color-white {
    background-color: white;
    color: #333;
  }
  .color-black {
    background-color: black;
    color: white;
  }

  @media (min-width: 690px) {
    .wide {
      grid-column: span 2;
    }
    .tall {
      grid-row: span 2;
    }
  }
</style>
