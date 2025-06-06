# Audio – Theme Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/themes/functionality/media/audio/](https://developer.wordpress.org/themes/functionality/media/audio/)  
**Last Updated:** 2025-05-24T13:54:47.877Z  
**Extracted:** 2025-05-31 16:56:23

---

# Audio – Theme Handbook | Developer.WordPress.org

## [Audio](#audio)

You can directly embed audio files and play them back using a simple shortcode **\[audio\]**. Supported file types are mp3, ogg, wma, m4a and wav.

### [Audio shortcode](#audio-shortcode)

Following shortcode displays audio player that loads music.mp3 file:

```
[[audio src="music.mp3"]]
```

To use the shortcode from template file, use do\_shortcode function. When music.mp3 file was stored in (theme\_directory)/sounds directory, insert following code into your template file:

```
$music_file = get_template_directory_uri() . "/sounds/music.mp3";
echo do_shortcode('[[audio mp3=' . $music_file . ']]');
```

The shortcode creates the audio player as shown in the screenshot below.

![Audio player](https://i0.wp.com/developer.wordpress.org/files/2014/10/audio_shortcode_basic.jpg?resize=558%2C66&ssl=1)

### [Loop and Autoplay](#loop-and-autoplay)

The following basic options are supported:

#### loop

Allows for the looping of media.

*   “off” – Do not loop the media. Default.
*   “on” – Media will loop to beginning when finished and automatically continue playing.

#### autoplay

Causes the media to automatically play as soon as the media file is ready.

*   0 – Do not automatically play the media. Default.
*   1 – Media will play as soon as it is ready.

The following example starts playing music immediately after the page load and loops.

```
echo do_shortcode('[[audio mp3=' . $music_file . ' loop = "on" autoplay = 1]]');
```

### [Styling](#styling)

If you want to change the look & feel of audio player, you can do so by targeting the default class name of “wp-audio-shortcode”. If you insert following code into your style.css, half width of audio player will be displayed.

```
.wp-audio-shortcode {
  width: 50%;
}
```

#### Supported Audio format

*   mp3
*   ogg
*   wma
*   m4a
*   wav

### [References](#references)

For more technical details such as the internal library that enables this function, refer to

*   [https://make.wordpress.org/core/2013/04/08/audio-video-support-in-core/](https://make.wordpress.org/core/2013/04/08/audio-video-support-in-core/).
*   [Audio Shortcode](https://codex.wordpress.org/Audio_Shortcode)
*   [Function do\_shortcode()](https://developer.wordpress.org/reference/functions/do_shortcode/)

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
