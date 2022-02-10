<script lang="ts">
  import './Tabbar.scss';

  import { Theme } from '../../styles';
  import { options } from '../App/App.svelte';
  export let blur = $options.theme === Theme.Tron;
  export let border = true;

  export let style = '';
</script>

<div
  class={`
    lucid-tabbar
    ${blur ? 'lucid-tabbar-blur' : ''}
    ${border ? 'lucid-tabbar-border' : ''}
  `}
  {style}
>
  <slot />
</div>