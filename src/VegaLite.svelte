<script lang="ts">
  import { onMount } from 'svelte'
  import embed from 'vega-embed'
  import type {Result, VisualizationSpec} from 'vega-embed'

  let element: HTMLElement | undefined = undefined
  export let spec: VisualizationSpec
  let graph: Result | undefined = undefined

  onMount(async () => {
    if (element) {
      graph = await embed(element, spec)
    }
  })
</script>

<div bind:this={element}></div>