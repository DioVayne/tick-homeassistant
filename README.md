# Tick for Home Assistant

Triggers from Home Assistant for [Tick](https://github.com/DioVayne/tick), a free, open-source to-do app.

In Home Assistant you make named triggers once, such as *Sam comes home*, *Sunset* or *Bathroom light on*. In Tick you pick a trigger on a task. The first time it goes off while the task is still open, Tick sends one notification, to you and to everyone the task is shared with. You can share triggers with your household in Tick, so only one person in the house needs Home Assistant.

Tick never connects to your Home Assistant. Home Assistant sends the trigger names and "this went off" to Tick over HTTPS, with a key you make in Tick.

## Install

[![Open your Home Assistant and show this repository in the Marketplace.](https://my.home-assistant.io/badges/hacs_repository.svg)](https://my.home-assistant.io/redirect/hacs_repository/?owner=DioVayne&repository=tick-homeassistant&category=integration)

**Home Assistant 2026.11 or newer (Marketplace):**

1. Press the button above, or go to Settings → Marketplace → **Add from link** and enter `DioVayne/tick-homeassistant`. The Marketplace asks you to connect GitHub the first time you add a link.
2. Open **Tick** and select **Install**.
3. Settings → Devices & services → **Add integration** → **Tick**.

**Older Home Assistant with HACS:** HACS → ⋮ → Custom repositories → `https://github.com/DioVayne/tick-homeassistant`, type *Integration* → download **Tick** → restart.

**By hand:** copy `custom_components/tick` into the `custom_components` folder of your Home Assistant configuration and restart.

## Set up

1. **In Tick:** ⚙ Settings → Advanced → **Keys** → **+ New key**, access **Full access**. The address of your Tick is shown there too.
2. **In Home Assistant:** add the integration **Tick** and paste the address and the key.
3. On the integration's page, choose **Add trigger**: a name as you want to read it in Tick, what to watch (a person, the sun, a light, a door…) and the state it changes to. Optional: *only after it stayed so for* and *only from / until*.
4. **In Tick:** open a task → **Notify on a Home Assistant trigger** → pick the trigger. Press **Fire now** in Home Assistant to test it.

Each trigger gets a **Fire now** button (also for your own automations) and a **Last fired** sensor. After Tick has handled a trigger, Home Assistant fires the event `tick_trigger_fired`.

The whole story, with sharing and limits: [Home Assistant triggers in the Tick guide](https://github.com/DioVayne/tick/blob/main/docs/home-assistant.md).

## Good to know

- Works with every Tick: the hosted [app.ticktodo.nl](https://app.ticktodo.nl) and self-hosted Ticks updated since 24 November 2026.
- A trigger only notifies about tasks you already have. To add tasks from Home Assistant, use the YAML package in the [Tick repository](https://github.com/DioVayne/tick/tree/main/home-assistant).
- Tested on Home Assistant 2026.11.

## Development

The code is developed in the [Tick repository](https://github.com/DioVayne/tick/tree/main/home-assistant/custom_components/tick) and copied here for each release. Issues and ideas are welcome here.

## License

MIT
