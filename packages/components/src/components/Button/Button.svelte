<script lang="ts">
  import { options } from '../App/App.svelte';

  import './Button.scss';
  import { onMount } from 'svelte';

  import { Color, Theme } from '../../styles';

  export let type: 'pill' | 'icon' = 'pill';
  export let appearance: 'solid' | 'tint' | 'fill' | 'plain' = $options.theme === Theme.Tron ? 'solid' : 'fill';
  export let color: Color | undefined = appearance !== 'solid' ? $options.color : undefined;
  export let rounded = false;

  export let size: 'small' | 'medium' | 'large' = 'medium';

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
    ${appearance ? `lucid-button-${appearance}` : ''}
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
  <slot props={$$props} />
</a>
