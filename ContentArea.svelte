<script>
  import { onMount } from "svelte";
  import { activeSection } from "./store.js";

  let sectionContent;

  onMount(() => {
    $activeSection.subscribe(value => {
      sectionContent = value.content;
    });
  });
</script>

<style>
  .content-area {
    position: absolute;
    width: 80%;
    height: 80%;
    left: 10%;
    top: 10%;
    border-radius: 50%;
    background: #e0e0e0;
    box-shadow: inset -5px -5px 10px #d0d0d0, inset 5px 5px 10px #f0f0f0;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 2rem;
    box-sizing: border-box;
    font-size: 1.2rem;
    color: #333;
  }
</style>

<div class="content-area">
  {sectionContent}
</div>
