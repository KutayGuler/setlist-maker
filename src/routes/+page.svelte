<script lang="ts">
  import Board from './Board.svelte';

  let songs = [
    {
      id: 41,
      name: 'item41',
      url: 'https://www.youtube.com/embed/9_jk0sfOaCg?si=k9nmWXwrAGbTs2aB'
    },
    {
      id: 42,
      name: 'item42',
      url: 'https://www.youtube.com/embed/9_jk0sfOaCg?si=k9nmWXwrAGbTs2aB'
    },
    {
      id: 43,
      name: 'item43',
      url: 'https://www.youtube.com/embed/9_jk0sfOaCg?si=k9nmWXwrAGbTs2aB'
    },
    {
      id: 44,
      name: 'item44',
      url: 'https://www.youtube.com/embed/9_jk0sfOaCg?si=k9nmWXwrAGbTs2aB'
    },
    {
      id: 45,
      name: 'item45',
      url: 'https://www.youtube.com/embed/9_jk0sfOaCg?si=k9nmWXwrAGbTs2aB'
    },
    {
      id: 46,
      name: 'item46',
      url: 'https://www.youtube.com/embed/9_jk0sfOaCg?si=k9nmWXwrAGbTs2aB'
    },
    {
      id: 47,
      name: 'item47',
      url: 'https://www.youtube.com/embed/9_jk0sfOaCg?si=k9nmWXwrAGbTs2aB'
    },
    {
      id: 48,
      name: 'item48',
      url: 'https://www.youtube.com/embed/9_jk0sfOaCg?si=k9nmWXwrAGbTs2aB'
    },
    {
      id: 49,
      name: 'item49',
      url: 'https://www.youtube.com/embed/9_jk0sfOaCg?si=k9nmWXwrAGbTs2aB'
    }
  ];

  for (let song of songs) {
    song.video_visible = false;
  }
</script>

<main class="bg-zinc-800 w-full h-full flex flex-col items-center">
  <h1 class="text-white text-4xl font-bold text-center pt-4">Setlist</h1>
  <div class="max-w-5xl w-full flex flex-row gap-4">
    <Board {songs} />
    <div class="w-1/6">stats</div>
  </div>
</main>
