<script>
  import { createEventDispatcher } from "svelte";
  import { navigate } from "svelte-routing";

  import NIcon from "../../components/icon/icon.svelte";

  export let to = undefined;

  const dispatch = createEventDispatcher();
  const onClick = event => {
    if (to) {
      navigate(to);
    } else {
      history.back();
    }
    dispatch("click", event);
  };
</script>

<style>
  button {
    margin-left: -4px;
  }
</style>

<button class="btn tap-icon" on:click={onClick}>
  <NIcon name="arrowBack" />
</button>
