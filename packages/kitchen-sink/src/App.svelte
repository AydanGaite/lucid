<script lang="ts">
  import {
    App,
    Button,
    ButtonType,
    Label,
    Page,
    Tabbar,
  } from '@lucid/components/src';
  import { Color, Size, Surface } from '@lucid/components/src/styles';
  import {
    CameraFill,
    EllipsisCircleFill,
    RocketFill,
    PencilOutline,
  } from 'framework7-icons/svelte/framework7-icons-svelte';

  export let toggle = false;
</script>

<style lang="scss">
  .container {
    display: flex;
    & > :global(*) {
      margin-right: 8px;
    }
  }
</style>

<App>
  <Page>
    <div style="padding: 25px">
      <h2>Kitchen Sink</h2>
      <br />
      <h5>Buttons</h5>
      <div class="container">
        <Button surface={Surface.None}>Button</Button>
        <Button surface={Surface.Solid}>Button</Button>
        <Button surface={Surface.Filled}>Button</Button>
        <Button surface={Surface.Tinted} color={Color.Blue}>Button</Button>
      </div>
      <br />
      <h5>Icon Buttons</h5>
      <div class="container">
        <Button type={ButtonType.Icon} surface={Surface.None}>
          <CameraFill slot="media" />
        </Button>
        <Button type={ButtonType.Icon} surface={Surface.Solid} color={Color.Blue}>
          <CameraFill slot="media" />
        </Button>
        <Button type={ButtonType.Icon} surface={Surface.Filled}>
          <CameraFill slot="media" />
        </Button>
        <Button type={ButtonType.Icon} surface={Surface.Tinted} color={Color.Blue}>
          <CameraFill slot="media" />
        </Button>
      </div>
      <br />
      <h5>Icon Buttons (With Labels)</h5>
      <div class="container">
        <Button
          type={ButtonType.Icon}
          surface={Surface.None}
        >
          <CameraFill slot="media" />
          Camera
        </Button>
        <Button
          type={ButtonType.Icon}
          surface={Surface.Solid}
          color={Color.Blue}
        >
          <CameraFill slot="media" />
          Camera  
        </Button>
        <Button type={ButtonType.Icon} surface={Surface.Filled}>
          <CameraFill slot="media" />
          Camera 
        </Button>
        <Button type={ButtonType.Icon} surface={Surface.Tinted}>
          <CameraFill slot="media" />
          Camera 
        </Button>
      </div>
      <br />
      <h5>Buttons (Mix)</h5>
      <div class="container">
        <Button surface={Surface.Tinted} color={Color.Red} style="width: 130px">New Event</Button>
        <Button type={ButtonType.Icon} color={Color.Red}><EllipsisCircleFill slot="media" /></Button>
      </div>
      <br />
      <h5>Buttons (Small)</h5>
      <div class="container">
        <Button surface={Surface.None} size={Size.Small}>Button</Button>
        <Button surface={Surface.Solid} size={Size.Small}>Button</Button>
        <Button surface={Surface.Filled} size={Size.Small}>Button</Button>
        <Button surface={Surface.Tinted} size={Size.Small}>Button</Button>
      </div>
      <br />
      <h5>Toggled (Buttons)</h5>
      <Button surface={toggle ? Surface.Solid : Surface.Filled} on:click={() => (toggle = !toggle)}>Button</Button>
    </div>
  </Page>
  <Tabbar slot="bottom-navigation" border={false}>
    <Button type={ButtonType.Icon} surface={Surface.Tinted}>
      <RocketFill slot="media" style="font-size: 25px" />
      Kitchen Sink
    </Button>
  </Tabbar>
</App>