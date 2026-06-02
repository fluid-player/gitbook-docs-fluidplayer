# Quick setup

This page walks you through adding Fluid Player to your website. There are two ways to do it:

* **The CDN approach** - paste a `<script>` tag and you're done. **Best for most websites**, no installation needed.
* **The NPM approach** - install the package via NPM. **For developers using a build tool like Webpack or Vite.**

**Pick whichever matches your setup. If you're not sure, the CDN approach is the right choice.**

> ℹ️ **Running WordPress?** You don't need to do any of this - **install the** [**Fluid Player WordPress plugin**](wordpress.md) **instead.**

***

### **Option 1: Use the CDN (recommended)**

A CDN is a service that hosts the Fluid Player files for you, so you don't have to download or install anything. You just link to them from your page.

#### **Step 1: Add a video to your page**

If you don't already have one, add a `<video>` tag where you want the player to appear:

```html
<video id="example-player">
    <source src="video.mp4" type="video/mp4" />
</video>
```

The `id` attribute is what tells Fluid Player which video to enhance - make sure it's there.

#### **Step 2: Load Fluid Player and start it**

Just before the closing `</body>` tag of your page, add the Fluid Player script and a one-line initializer. Your finished page should look like this:

```html
<!-- The video, somewhere in your page -->
<video id="example-player">
    <source src="video.mp4" type="video/mp4" />
</video>

<!-- Just before </body> -->
<script src="https://cdn.fluidplayer.com/v3/current/fluidplayer.min.js"></script>
<script>
    var player = fluidPlayer('example-player');
</script>
```

That's it. Refresh your page - you should see the Fluid Player skin replace the browser's default video controls.

> ✅ **As of v3.0.0**, the CDN build includes the CSS automatically. You don't need a separate `<link>` tag for stylesheets.

#### **Pinning to a specific version**

The URL above (`/v3/current/`) always serves the latest v3 release - recommended for most cases. If you'd rather lock to a specific version so it never changes underneath you, use:

```html
<script src="https://cdn.fluidplayer.com/3.0.0/fluidplayer.min.js"></script>
```

***

### **Option 2: Install via NPM**

Use this approach if you're building a JavaScript application with a bundler like Webpack, Vite, or Rollup.

#### **Install the package**

Run one of these in your project root (where `package.json` lives):

**Using npm:**

```bash
npm install fluid-player@^3.0.0
```

**Using yarn:**

```bash
yarn add fluid-player@^3.0.0
```

#### Import the JavaScript

Wherever you want to use Fluid Player in your code:

```javascript
import fluidPlayer from 'fluid-player';
```

#### Import the CSS

The NPM build does not bundle CSS — you need to import it separately. How you do that depends on your bundler. For a Webpack project using `~` as the `node_modules` import prefix:

```css
@import "~fluid-player/src/css/fluidplayer.css";
```

Refer to your bundler's documentation if you're using a different tool.

***

### Adding multiple quality options

If you have your video in different qualities (1080p, 720p, etc.), you can let viewers pick. Add multiple `<source>` tags — Fluid Player will show a quality selector in the player controls.

```html
<video id="my-video" controls style="width: 640px; height: 360px;">
    <source src="vid_1080p.mp4" title="1080p" type="video/mp4" />
    <source src="vid_720p.mp4" title="720p" type="video/mp4" />
    <source src="vid_480p.mp4" title="480p" type="video/mp4" />
</video>
```

The `title` attribute is what shows up in the quality menu.

#### Marking a source as HD

To highlight high-definition options visually, add `data-fluid-hd` to the `<source>` tag. The HD label uses your player's primary color by default.

```html
<video id="my-video" controls style="width: 640px; height: 360px;">
    <source data-fluid-hd src="vid_1080p.mp4" title="1080p" type="video/mp4" />
    <source data-fluid-hd src="vid_720p.mp4" title="720p" type="video/mp4" />
    <source src="vid_480p.mp4" title="480p" type="video/mp4" />
</video>
```

If you'd rather use a different color for the HD label, override it in your own CSS - the relevant class is `fp_hd_source`:

```css
.fp_hd_source { color: yellow !important; }
```

***

### Customizing the player

Fluid Player accepts a configuration object as a second argument. This is where you set up appearance, ad behavior, and almost everything else.

```html
<video id="my-video" controls style="width: 640px; height: 360px;">
    <source src="vid.mp4" type="video/mp4" />
</video>

<script type="text/javascript">
var player = fluidPlayer(
    'my-video',
    {
        layoutControls: {
            // Parameters to customise the look and feel of the player
        },
        vastOptions: {
            // Parameters to customise how the ads are displayed and behave
        }
    }
);
</script>
```

For the full list of options, see the [**Configuration reference**](https://app.gitbook.com/s/8rGD7jsniiB2SIkmyD9Z/configuration).

***

### Reference: the initializer

```javascript
var player = fluidPlayer(target [, options]);
```

**`target`** _(required)_ - tells Fluid Player which video to attach to. You can pass either:

* The `id` of your `<video>` tag as a string, e.g. `'my-video'`, or
* The video element directly, e.g. `document.getElementById('my-video')`

**`options`** _(optional)_ - a configuration object. See [**Configuration**](https://app.gitbook.com/s/8rGD7jsniiB2SIkmyD9Z/configuration) for the full list.

> ⚠️ **Heads up:** If you pass the video element directly and it doesn't already have an `id` attribute, Fluid Player will add one automatically. If your code relies on the element not having an id, set one yourself before calling `fluidPlayer()`.

***

### Where next?

> 💡 **Set up ads** → [**Advertisements**](../configuration/advertisements.md)**.**
>
> 🎨 **Customize the look** → [**Layout configuration**](../configuration/layout.md)**.**
>
> 📝 **Add subtitles** → [**Subtitles**](../configuration/subtitles.md)**.**
