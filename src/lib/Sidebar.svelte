<script lang="ts">
    import { invoke } from "@tauri-apps/api/tauri"
    import ProfileButton from "./ProfileButton.svelte";
  
    let name = "";
    let greetMsg = ""
  
    async function greet(){
      // Learn more about Tauri commands at https://tauri.app/v1/guides/features/command
      greetMsg = await invoke("greet", { name })
    }
</script>

<aside style="display:flex; flex-direction:column; justify-content:space-between">
    <div class="sidebar">
        <div class="button_container">
            <a class="button" href="#">
                <svg class="svg" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5.121 17.804A13.937 13.937 0 0112 16c2.5 0 4.847.655 6.879 1.804M15 10a3 3 0 11-6 0 3 3 0 016 0zm6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
                </svg>
            </a>
            <a class="button" href="#">
                <svg class="svg" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5.121 17.804A13.937 13.937 0 0112 16c2.5 0 4.847.655 6.879 1.804M15 10a3 3 0 11-6 0 3 3 0 016 0zm6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
                </svg>
            </a>
        </div>
    </div>
    <ProfileButton />
</aside>

<style>
.sidebar {
    display: flex;
    flex-direction: column;
    width: 4rem;
    align-items: center;
    overflow: hidden;
    background-color: #202020ab;
    color: #575353;
}

.button_container {
    display: flex;
    flex-direction: column;
    align-items: center;
    border-top: #747373;
}
.button {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 4rem;
    height: 4rem;
    margin-top: auto;
    background-color: #414141de;
}
.button:hover {
    background-color: #686868de;
    color: #e6e4e4;
}

.svg {
    width: 1.5rem;
    height: 1.5rem;
    stroke: currentColor;
}
</style>