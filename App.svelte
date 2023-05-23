<script>
  import RotatingRing from "./RotatingRing.svelte";
  import ContentArea from "./ContentArea.svelte";
</script>

<style>
  .portfolio-component {
    position: relative;
    width: 600px;
    height: 600px;
    margin: 0 auto;
    background: #f5f5f5;
    border-radius: 50%;
    overflow: hidden;
    box-shadow: 10px 10px 15px #aaa, -10px -10px 15px #fff;
  }
</style>

<div class="portfolio-component">
  <RotatingRing />
  <ContentArea />
</div>
