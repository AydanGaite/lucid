<script lang="ts">
  import { ButtonType } from './';
  import { options } from '../App/App.svelte';

  import './Button.scss';
  import { onMount } from 'svelte';

  import {
    Color,
    Size,
    Surface,
    Theme,
  } from '../../styles';

  export let type: ButtonType = ButtonType.Pill;
  export let surface: Surface = $options.theme === Theme.Tron ? Surface.Solid : Surface.Filled;
  export let color: Color | undefined = surface !== Surface.Solid ? $options.color : undefined;

  export let text = '';

  export let rounded = false;
  export let size: Size = Size.Medium;

  export let condensed = true;
  export let emphasis = true;

  export let href = '#';
  
  export let style = '';

  let ref: HTMLAnchorElement;

  onMount(() => ref.addEventListener('touchstart', () => undefined, false));
</script>

<a
  class={`
    lucid-button
    ${`lucid-button-type-${type}`}
    ${`lucid-button-size-${size}`}
    ${color ? `lucid-color-${color}` : ''}
    ${surface ? `lucid-button-${surface}` : ''}
    ${rounded ? 'lucid-button-rounded' : ''}
    ${condensed ? 'lucid-button-condensed' : ''}
    ${emphasis ? 'lucid-emphasis' : ''}
  `}
  {style}
  {href}
  role="button"
  bind:this={ref}
  on:click
>
  {#if $$slots.media}
    <div class="lucid-button-media">
      <slot name="media" props={$$props} />
    </div>
  {/if}
  <span class="lucid-button-text">
    {text}
    <slot props={$$props} />
  </span>
</a>
