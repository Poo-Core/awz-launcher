<script lang="ts">
  import { appWindow } from '@tauri-apps/api/window';
  import Greet from './lib/Greet.svelte'
  import { onMount } from 'svelte';
    import Sidebar from './lib/Sidebar.svelte';
  //appWindow.setClosable(false);
  
  onMount(() => {
    document?.getElementById('titlebar-minimize')?.addEventListener('click', () => appWindow.minimize());
    document?.getElementById('titlebar-close')?.addEventListener('click', () => appWindow.close())
  });
</script>

<div data-tauri-drag-region class="titlebar">
  <div class="titlebar-button" id="titlebar-minimize">
    <img
      src="https://api.iconify.design/mdi:window-minimize.svg"
      alt="minimize"
    />
  </div>
  <div class="titlebar-button" id="titlebar-close">
    <img src="https://api.iconify.design/mdi:close.svg" alt="close" />
  </div>
</div>
<main class="container">
  <div style="display: flex; flex-direction:row; height: 570px">
    <Sidebar/>
    <div style="display: flex; flex-direction:column; align-items: center; justify-content: center; width:calc(800px - 4rem);">
      <h1>Welcome to Tauri!</h1>
    
      <div class="row">
        <a href="https://vitejs.dev" target="_blank">
          <img src="/vite.svg" class="logo vite" alt="Vite Logo" />
        </a>
        <a href="https://tauri.app" target="_blank">
          <img src="/tauri.svg" class="logo tauri" alt="Tauri Logo" />
        </a>
        <a href="fivem://connect/localhost" target="_blank">
          <img src="/svelte.svg" class="logo svelte" alt="Svelte Logo" />
        </a>
      </div>
    
      <p>
        Click on the Tauri, Vite, and Svelte logos to learn more.
      </p>
    
      <div class="row">
        <Greet />
      </div>
    </div>
  </div>



</main>

<style>
  .logo.vite:hover {
    filter: drop-shadow(0 0 2em #747bff);
  }

  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00);
  }
</style>