# Intentional Feedback Loops via Input Monitoring

To create an audio feedback effect in Reaper, similar to a microphone placed near a speaker, you need to set up a deliberate **feedback loop**. This is not enabled by default in Reaper because it can cause a rapid, loud increase in volume, potentially damaging your speakers or ears. Proceed with caution and keep your master volume low.

### Enabling Feedback Routing

The first step is to enable feedback routing in Reaper's settings. 

1. Go to **File > Project Settings**.
2. Navigate to the **Advanced** tab.
3. Check the box for **"Allow feedback in routing (can result in lower performance, louder noises)"**.

This single step gives you the ability to create a signal path that feeds back into itself.

---

### Creating the Feedback Loop

Once feedback routing is enabled, you'll create the loop using sends and returns. This setup allows you to control the level and character of the feedback.

1.  **Create a New Track 🎤**: This will be your input track, where your microphone is armed and monitoring is enabled.
2.  **Create an FX Track**: Add a second track to serve as your "effects" or "speaker" track. This is where you will add effects that mimic the characteristics of a speaker and the air between the mic and the speaker. You'll likely want to use plugins like an EQ to shape the tone, a saturator or distortion to add grit, and a delay or reverb to create the repeating effect.
3.  **Set up the Send**: On your mic track, click the **Route** button. This will open the routing window. Create a send from your mic track to your FX track. This sends a copy of the microphone's signal to the effects track.
4.  **Set up the Return**: On your FX track, click the **Route** button. Create a send from the FX track back to the mic track. This is the crucial step that completes the feedback loop.
5.  **Disable Master Send on the FX Track**: In the routing window for your FX track, uncheck the **"Master Send"** box. This prevents the raw, unprocessed signal from the FX track from going directly to your master output, which helps you isolate and control the feedback effect.
6.  **Control the Feedback**: Use the faders on the sends to carefully control the amount of signal that is being fed back. You can also adjust the levels on the tracks themselves. Start with very low levels to avoid a sudden, loud **"howl-round"** effect.

By experimenting with the effects on the FX track (especially delay and EQ) and adjusting the send levels, you can emulate the specific sound of a mic and speaker interacting in a physical space. The delay between the sound leaving the speaker and re-entering the microphone is simulated by the send/return routing and any delay plugins you add to the FX track.

[Quickly Creating FX Sends & Returns in REAPER](https://www.youtube.com/watch?v=ymOpmgjhqFY) is a video that demonstrates how to set up sends and returns in Reaper, which is a key component of creating a feedback loop.
