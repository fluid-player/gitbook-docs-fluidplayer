# Introduction

**Fluid Player is a free video player for your website.** Drop it onto any page, point it at your video, and you're done. It works on phones, tablets, and desktops, runs ads if you want them to, and stays out of the way of the rest of your site.

You don't need an engineering team to set it up - if you can paste a few lines of HTML, you can be running in about two minutes. And if you'd rather not touch code at all, there's an official WordPress plugin.

💡 **In a hurry?** → [**Quick setup**](integration/quick-setup.md) gets you a working player in five minutes flat.

***

### **What you can do with it**

Rather than a flat feature list, **here's what Fluid Player actually does for you** and your site.

#### **💰Make money from your videos**

If you sell ads - or you'd like to - Fluid Player has full ad support built in.

* **Run ads before, during, and after your videos** - pre-roll, mid-roll, and post-roll slots.
* **Video ads and banner ads** - both full-screen video ads (linear) and smaller banner overlays in GIF, JPG, or PNG (non-linear).
* **Works with any ad network** - uses the industry-standard VAST format, so it plugs into the ad provider you already use.
* **Chain multiple ad networks** - VAST Wrappers let you route through ad exchanges.
* **Interactive ad support** - VPAID ads (linear, non-linear, and switching from non-linear to linear) work out of the box.
* **Custom call-to-action text during ads** -  drive viewers to your landing page.

New to ad serving? [See **What is VAST** below.](./#what-is-vast)

#### **🎨 Looks right on your site**

* **Built-in design** - comes with a clean, modern skin that's easy to customize.
* **Use the browser's default look** - if you'd rather match the native feel.
* **Add your own logo** - brand the player with your image.
* **Subtitles** - captions for accessibility and reach.
* **Timeline preview** - thumbnail previews when viewers hover the progress bar.

#### **👀 Keeps viewers watching**

* **Mini Player** - when viewers scroll past your video, it shrinks into a floating window so they can keep watching.
* **Suggested Videos** - show related videos after one ends, to keep the session going.
* **Quality options** - offer HD, SD, or whatever versions you have; viewers pick what works best.
* **HLS quality switching** - including an Auto mode (the default) that adapts to the viewer's connection speed.
* **Autoplay control** - fine-grained control over what plays automatically.

#### **⚡ Fast and dependable**

* **Lightweight** - small footprint, won't slow your pages down.
* **Responsive** - adapts to phones, tablets, and desktops.
* **Works in every modern browser** - current Chrome, Firefox, Safari, Edge.
* **Multiple players on one page** - embed as many videos as you like.
* **Hosted on a CDN** - no need to host scripts yourself (though you can if you prefer).
* **Keyboard shortcuts** - configurable per key, for accessibility.

***

### **Get started in 30 seconds**

#### **Step 1: Add a video to your page**

```html
<video id="example-player">
    <source src="video.mp4" type="video/mp4" />
</video>
```

The `id` attribute is what tells Fluid Player which video to enhance - make sure it's there.

#### **Step 2: Load Fluid Player and start it**

```html
<script src="https://cdn.fluidplayer.com/v3/current/fluidplayer.min.js"></script>
<script>
    var player = fluidPlayer('example-player');
</script>
```

That's it. Refresh your page - you should see the Fluid Player skin replace the browser's default video controls.

***

### **Pick your path**

Most people landing here fall into one of a few groups. Pick the one that sounds like you:

* **Running WordPress?** → Use the[ Fluid Player WordPress plugin](integration/wordpress.md) - no code needed.
* **Have your own site and want to add it yourself?** → [Quick setup ](integration/quick-setup.md)walks through the install.
* **Setting up video ads?** →[ Advertisements](configuration/advertisements.md) cover VAST tags, ad slots, and VPAID.
* **Building a web app or custom product?** → Head to the[ Developer guide](https://app.gitbook.com/s/8rGD7jsniiB2SIkmyD9Z/api) for the full API, events, and controls.

***

### **What is VAST?**

If you're planning to run ads on your videos, you'll see "VAST" mentioned a lot - here's the short version.

**VAST stands for Video Ad Serving Template.** It's a standard from the IAB (Interactive Advertising Bureau) that lets ad networks and video players communicate in a shared language.

In practice, **VAST is what makes Fluid Player work with any ad provider** - your own ad server, ad networks, ad exchanges, all of them. You point Fluid Player at a VAST tag (a URL your ad provider gives you), and Fluid Player handles the rest: fetching the ad, playing it, tracking views and clicks, and resuming your video when the ad ends.

You don't need to understand the technical details to use it - just paste the VAST tag your ad provider gives you into the configuration.

**For the full specification**, see the[ IAB VAST documentation](https://iabtechlab.com/standards/vast/).

***

### **License**

Fluid Player is released under the **MIT License** - free to use commercially or non-commercially, including in closed-source products.&#x20;

See the[ License page](https://docs.fluidplayer.com/about/license) for the full terms.

***

### **Where next?**

> 💡 **Ready to set it up?** → [**Quick setup**](integration/quick-setup.md)**.**
>
> 📖 **Want to see every option?** → [**Configuration**](https://app.gitbook.com/s/8rGD7jsniiB2SIkmyD9Z/configuration)**.**
>
> 💬 **Need help?** → [**Help & support**](about/help.md)**.**
