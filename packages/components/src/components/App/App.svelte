<script lang="ts" context="module">
  import './App.scss';
  import { writable } from 'svelte/store';
  import { Color, Theme } from '../../styles';

  export const options = writable({
    theme: Theme.Tron,
    color: Color.Blue,
  });
</script>

<script lang="ts">
  export let theme: Theme = Theme.Tron;
  export let appearance: 'dark' | 'light' | undefined = undefined;
  export let color: Color = Color.Blue;

  const appearanceOverwritten = !!appearance;
  $: !appearanceOverwritten && (appearance = window.matchMedia('(prefers-color-scheme: dark)').matches ? 'dark' : 'light');

  $options.theme = theme;
  $options.color = color;
</script>

<div
  class={`
    lucid-app
    ${`lucid-theme-${theme}`}
    ${`lucid-appearance-${appearance}`}
  `}
>
  <div class="lucid-app-content">
    <slot />
  </div>
  {#if $$slots['bottom-navigation']}
    <div class="lucid-app-bottom-navigation">
      <slot name="bottom-navigation" />
    </div>
  {/if}
</div>