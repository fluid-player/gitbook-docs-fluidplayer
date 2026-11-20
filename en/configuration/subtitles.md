# Subtitles

Subtitles are text derived from either a transcript or screenplay of the dialog or commentary in films, television programs, video games, and the like, usually displayed at the bottom of the screen.

### VTT format

```
WEBVTT

1
00:00:15.000 --> 00:00:18.000 align:start
At the left we can see...

2
00:00:18.167 --> 00:00:20.083 align:middle
At the right we can see the...

3
00:00:20.083 --> 00:00:22.000
...the head-snarlers

4
00:00:22.000 --> 00:00:24.417 align:end
Everything is safe. Perfectly safe.

5
00:00:24.583 --> 00:00:27.083
Emo?
```

### Adding to Fluid Player

To configure Fluid Player to use your VTT file, set the optional `subtitlesEnabled` parameter under `layoutControls`.

Provide subtitle URLs in `<track>` tags under `kind='metadata'`.

Please make sure that you **do not specify** `kind='subtitles'`, because that doesn't work in some browsers.

```html
<video id="my-video" controls>
    <source src="video.mp4" type="video/mp4"/>
    <track label="English" kind="metadata" srclang="en" src="/subtitles/english.vtt" default>
    <track label="Deutsch" kind="metadata" srclang="de" src="/subtitles/deutsch.vtt">
</video>

<script type="application/javascript">
fluidPlayer(
    'my-video',
    {
        layoutControls: {
            subtitlesEnabled: true
        }
    }
);
</script>
```

### subtitlesOnByDefault

Set this parameter to **true** to have subtitles on by default. This parameter is by default already set to **true**.

```javascript
fluidPlayer(
    'my-video',
    {
        layoutControls: {
            subtitlesOnByDefault: false, // Default true
        }
    }
);
```

### Font Size Options

Fluid Player supports subtitle font size controls, enhancing accessibility and viewer experience by allowing text size adjustments. Users can customize subtitle size in two convenient ways:

#### Method 1: Keyboard Shortcuts

While viewing content, users can quickly adjust subtitle size using simple keyboard shortcuts:

* Press the `+` key to increase subtitle font size
* Press the `-` key to decrease subtitle font size

#### Method 2: Font Size Submenu

A dedicated Font Size submenu is available in the subtitles/captions control panel. This menu provides precise control with predefined percentage options:

* 50%
* 75%
* 100% (Default)
* 150%
* 200%
