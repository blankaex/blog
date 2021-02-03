---
layout: post
title:  "Making NicoKara - The Easy Way"
date:   2021-02-03
excerpt: "Tired of K-timing in Aegisub?"
tag:
- Tutorial
---

Tired of K-timing in Aegisub? What if I told you there was a lazy way to K-time your trash weeaboo songs? There's some [excellent](https://www.nicovideo.jp/watch/sm16623246) [documentation](https://shinta0806be.ldblog.jp/tag/ニコカラメーカー2) in Japanese, but if you're a filthy EOP then you're shit out of luck... Until today.

## What you'll need:
* [RhythmicaLyrics](http://suwa.pupu.jp/RhythmicaLyrics.html)
* [ニコカラメーカー２ (NicoKara Maker 2)](https://shinta.coresv.com/software/nicokaramaker2-jpn/)

### Optional:
* [ffmpeg](https://github.com/FFmpeg/FFmpeg)
* [youtube-dl](https://github.com/ytdl-org/youtube-dl)

You'll also need a video to overlay the lyrics onto. Make sure it's 16:9 so that the words fit onto the screen. If your song isn't in the video's audio track, get that ready too. Keep your lyrics handy as well—any kind of plaintext is fine.

## Instructions

### 1. Inputting lyrics

Open up RhythmicaLyrics and go into text edit mode (the page button) to paste in your lyrics. Try to keep the "segments" a dozen or so (full-width Japanese) characters long, because NicoKara Maker isn't too smart when it comes to inserting automatic line breaks. Segments are separated by spaces or newlines, but I find it's generally a bit cleaner to work with if you remove any unnecessary whitespace and keep each segment on its own line.

{% capture images %}
    {{ site.url }}/assets/res/2021-02-03-nicokara-tutorial/1.jpg

{% endcapture %}
{% include gallery images=images cols=2 %}

### 2. Generating checks

Once you're done tidying up your lyrics, get out of text edit mode by clicking the button again. RhythmicaLyrics will automatically generate "checks" (the little triangle marks) for each syllable, which is what you'll be tagging with timestamps. If you messed up somehow and the checks aren't automatically generated when you go back, hit the tool button and select `自動チェック付加実行` (the first option).

{% capture images %}
    {{ site.url }}/assets/res/2021-02-03-nicokara-tutorial/2.jpg
    {{ site.url }}/assets/res/2021-02-03-nicokara-tutorial/3.jpg
{% endcapture %}
{% include gallery images=images cols=2 %}

### 3. Configuring ruby text

Ensure ruby display is turned on by going to `ルビ→ルビを表示する` on the menu bar. You might notice there's ruby text on every single character, including the _kana_ and English. To clean that up, head back to the menu bar and go `ルビ→文字種を指定してルビを削除` and select pretty much everything other than 漢字 (_kanji_) and hit `実行` to start.

{% capture images %}
    {{ site.url }}/assets/res/2021-02-03-nicokara-tutorial/4.jpg
    {{ site.url }}/assets/res/2021-02-03-nicokara-tutorial/5.jpg
{% endcapture %}
{% include gallery images=images cols=2 %}

### 4. Timing the lyrics

Here comes the fun part. Drag and drop in your video (or audio) file, and then press play. You'll notice the text greys out, and one of the checks will be highlighted pink. This is the cursor to indicate your current position. All you need to do here is tap space in time with the start of each syllable in the song to place a time tag at your cursor and advance to the next syllable. It's just like a rhythm game :^)

As you place time tags, the checks will turn purple to indicate the ones you've already marked. Also note the empty square checks at the end of each line. These are tagged on key _release_. Basically, hold down space on the last syllable and let go as it ends in the audio. If you mess up (you will), just rewind the song and time over your previous time tags. 

Obviously, repeat this through to the end. If that didn't make sense, check out [this video that I linked earlier](https://www.nicovideo.jp/watch/sm16623246) from about 1:45.

{% capture images %}
    {{ site.url }}/assets/res/2021-02-03-nicokara-tutorial/6.jpg
    {{ site.url }}/assets/res/2021-02-03-nicokara-tutorial/7.jpg
{% endcapture %}
{% include gallery images=images cols=2 %}

Some useful hotkeys:

| Key  | Action            | Key  | Action                  |
|------|-------------------|------|-------------------------|
| ←↑↓→ | Reposition cursor | Q    | Decrease playback speed |
| Z    | Skip backwards    | W    | Increase playback speed |
| X    | Skip forwards     | 1    | Decrease volume         |
| D    | Play/pause        | 2    | Increase volume         |

The automatic ruby text generation is pretty good, but it isn't (and won't ever be) perfect, especially if the lyricist likes their _ateji_. If you run into such a situation, position your cursor on the offending text and press `Ctrl+H`. You can edit the ruby text in the bottom field, being mindful of the comma positions. Saving this will also add or remove checks so that the syllable count adds up.

{% capture images %}
    {{ site.url }}/assets/res/2021-02-03-nicokara-tutorial/8.jpg
    {{ site.url }}/assets/res/2021-02-03-nicokara-tutorial/9.jpg
{% endcapture %}
{% include gallery images=images cols=2 %}

### 5. Exporting the timed lyrics

Once you're mostly happy with your handiwork, hit the `@` button (on the toolbar, not your keyboard) to enter the song metadata. Title and artist are the main ones. Make sure to check the boxes. Then to export your file, go to `ファイル→出力(O)→ルビ拡張規格でタイムタグ出力(2)→実行(E)`, or press `Ctrl+2`, and save your file. Doing it this way ensures that your ruby text is exported along with the timed lyrics.

{% capture images %}
    {{ site.url }}/assets/res/2021-02-03-nicokara-tutorial/10.jpg
    {{ site.url }}/assets/res/2021-02-03-nicokara-tutorial/11.jpg
{% endcapture %}
{% include gallery images=images cols=2 %}

### 6. Putting it all together

We're done with RhythmicaLyrics now, so we can close that and open up NicoKara Maker. This is the tool that will overlay the timed karaoke lyrics onto your video and make it look all pretty.

Go into the 2nd tab and drop in your video file. If your audio is in a separate file, check the `別のファイルの音声を使用する` box and drop that in too. Then go to the next tab and drop in the `.lrc` file we just exported from RhythmicaLyrics. If it's in the same directory with the same filename, it should be loaded automatically. You can check here to see if it's correctly displaying the lyrics and ruby text.

{% capture images %}
    {{ site.url }}/assets/res/2021-02-03-nicokara-tutorial/12.jpg
{% endcapture %}
{% include gallery images=images %}

You can adjust the title in the 4th tab, mess around with fonts and styling in the 5th, and adjust the layouts in the 6th. I won't go into too much detail here; you can explore and play around with the options on your own. It's quite self-explanatory, and the defaults aren't too shabby either. The 7th tab is to preview the final product.

Again once you're happy, go to the final tab and press `動画出力` to export the file. This will write a lossless `.avi`, which means it will take ages and render a gigantic file. This is why I suggest ffmpeg to re-encode the video into something sane, since NicoKara Maker unfortunately doesn't have any better output options. Once you're done with that though, you're done for real. Congratulations! This is what the final product should look like:

<iframe width="560" height="315" src="https://www.youtube.com/embed/PjpVyoGqVhA" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
