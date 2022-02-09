<script lang="ts">
  import './Label.scss';

  import { Color } from '../../styles';

  export let color: Color | undefined = undefined;
  export let text: string;
</script>

<div class="lucid-label">
  <slot props={$$props} />
  <span
    class={`
      lucid-label-text
      ${color ? `lucid-color-${color}` : ''}
    `}
  >
    {text}
  </span>
</div>