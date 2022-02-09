<script lang="ts">
  import {
    App,
    Button,
    Label,
    Tabbar,
  } from '@lucid/components/src';
  import { Color } from '@lucid/components/src/styles';
  import {
    CameraFill,
    EllipsisCircleFill,
    HouseAltFill,
    Person2Fill,
    Search,
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

<App color={Color.Blue}>
  <div style="padding: 25px">
    <h2>Kitchen Sink</h2>
    <br />
    <h5>Buttons</h5>
    <div class="container">
      <Button appearance="plain">Button</Button>
      <Button appearance="solid">Button</Button>
      <Button appearance="fill">Button</Button>
      <Button appearance="tint" color={Color.Blue}>Button</Button>
    </div>
    <br />
    <h5>Buttons (Icons Only)</h5>
    <div class="container">
      <Button type="icon" appearance="plain"><CameraFill /></Button>
      <Button type="icon" appearance="solid" color={Color.Blue}><CameraFill /></Button>
      <Button type="icon" appearance="fill"><CameraFill /></Button>
      <Button type="icon" appearance="tint" color={Color.Blue}><CameraFill /></Button>
    </div>
    <br />
    <h5>Buttons (Mix)</h5>
    <div class="container">
      <Button appearance="tint" color={Color.Red} style="width: 130px">New Event</Button>
      <Button type="icon" color={Color.Red}><EllipsisCircleFill /></Button>
    </div>
    <br />
    <h5>Buttons (Small)</h5>
    <div class="container">
      <Button appearance="plain" size="small">Button</Button>
      <Button appearance="solid" size="small">Button</Button>
      <Button appearance="fill" size="small">Button</Button>
      <Button appearance="tint" color={Color.Blue} size="small">Button</Button>
    </div>
    <br />
    <h5>Labeled (Buttons - Icons Only)</h5>
    <div class="container">
      <Label text="Camera">
        <Button type="icon" appearance="plain"><CameraFill /></Button>
      </Label>
      <Label text="Camera">
        <Button type="icon" appearance="solid" color={Color.Blue}><CameraFill /></Button>
      </Label>
      <Label text="Camera">
        <Button type="icon" appearance="fill"><CameraFill /></Button>
      </Label>
      <Label text="Camera">
        <Button type="icon" appearance="tint" color={Color.Blue}><CameraFill /></Button>
      </Label>
    </div>
    <br />
    <h5>Toggled (Buttons)</h5>
    <Button appearance={toggle ? 'solid' : 'fill'} on:click={() => (toggle = !toggle)}>Button</Button>
  </div>
  <Tabbar border={false} slot="bottom-navigation">
    <Button type="icon" appearance="plain" color={Color.Gray} emphasis={false}>
      <HouseAltFill />
      Home
    </Button>
    <Button type="icon" appearance="plain" color={Color.Gray} emphasis={false}>
      <Person2Fill />
      Contacts
    </Button>
    <Button type="icon" appearance="tint" emphasis={false}>
      <Search />
      Search
    </Button>
  </Tabbar>
</App>