<script>
  export let name;
  export let type;
  import { buttonValue } from "./store";
  $: extension = name.slice(name.lastIndexOf(".") + 1);
  let show = false;
  const handleDetailClick = () => {
    console.log("handleDetailClick", name);
    console.log("handleDetailClick", type);

    buttonValue.set(name);
  };
</script>

<button on:click={handleDetailClick}>
  <span style="background-image: url({extension}.svg)">{name}</span>
</button>

<style>
  span {
    padding: 0 0 0 1.5em;
    background: 0 0.1em no-repeat;
    background-size: 1em 1em;
  }
</style>
