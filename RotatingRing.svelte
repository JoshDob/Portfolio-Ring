<script>
  import { onMount } from "svelte";
  import { activeSection } from "./store.js";

  let sections = [
    { id: 1, title: "Section 1", content: "Content for section 1" },
    { id: 2, title: "Section 2", content: "Content for section 2" },
    { id: 3, title: "Section 3", content: "Content for section 3" },
    { id: 4, title: "Section 4", content: "Content for section 4" }
  ];

  let angle = 0;
  let rotationSpeed = 2;

  onMount(() => {
    const interval = setInterval(() => {
      angle = (angle + rotationSpeed) % 360;
      activeSection.set(sections[Math.floor(angle / (360 / sections.length))]);
    }, 100);

    return () => {
      clearInterval(interval);
    };
  });
</script>

<style>
  .rotating-ring {
    position: absolute;
    width: 100%;
    height: 100%;
    border-radius: 50%;
    background: #ccc;
  }

  .ring-section {
    position: absolute;
    width: 100%;
    height: 100%;
    border-radius: 50%;
    background: #ccc;
  }

  .ring-section.active {
    box-shadow: 0 0 10px #ff0, 0 0 20px #ff0, 0 0 30px #ff0, 0 0 40px #ff0;
  }
</style>

<div class="rotating-ring">
  {#each sections as section (section.id)}
    <div class="ring-section" class:active={$activeSection.id === section.id}>
      {section.title}
    </div>
  {/each}
</div>
