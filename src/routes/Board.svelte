<script lang="ts">
  // This is done in a single file for clarity. A more factored version here: https://svelte.dev/repl/288f827275db4054b23c437a572234f6?version=3.38.2
  import { flip } from 'svelte/animate';
  import { dndzone } from 'svelte-dnd-action';
  export let songs: any;
  const flipDurationMs = 200;

  function handleDndConsiderCards(e) {
    songs = e.detail.items;
    songs = [...songs];
  }

  function handleDndFinalizeCards(e) {
    songs = e.detail.items;
    songs = [...songs]; // ?
  }

  function removeItem(item_id) {
    console.log(songs);
    songs = songs.filter(({ id }) => id != item_id);
  }
</script>

<section class="w-1/2">
  <div class="py-4">
    <div
      class="flex flex-col gap-2 p-2"
      use:dndzone={{ items: songs, flipDurationMs }}
      on:consider={handleDndConsiderCards}
      on:finalize={handleDndFinalizeCards}
    >
      {#each songs as item (item.id)}
        <div class="bg-zinc-200 p-2 relative" animate:flip={{ duration: flipDurationMs }}>
          {#if item.video_visible}
            <iframe
              width="248"
              height="140"
              src={`${item.url}&modestbranding=1`}
              title="YouTube video player"
              frameborder="0"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
              allowfullscreen
            />
          {/if}
          <button on:click={() => removeItem(item.id)} class="absolute top-2 right-2">🞫</button>
        </div>
      {/each}
    </div>
  </div>
</section>
