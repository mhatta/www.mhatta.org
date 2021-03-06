---
layout: post
title: "2nd Denousen: Abe vs. Shueso"
date: 2013-03-24 04:50
comments: true
categories:
- shogi
- debian
---
[The 2nd Shogi Denousen](http://ex.nicovideo.jp/denousen2013/) has began.  This is the first cut-throat match between top-notch professional Shogi players(yes, there are [such people](http://www.shogi.or.jp/player/index.html)) and the best crop of computer Shogi engines, 5 on 5.

<!--more-->

[Shogi](http://en.wikipedia.org/wiki/Shogi) is a distant cousin of Chess.  Unlike Chess, you may re-use captured pieces anywhere on the board anytime.  It brings quite lot of additional complexities, and even after [the defeat of Garry Kasparov](http://en.wikipedia.org/wiki/Deep_Blue_versus_Garry_Kasparov) in 1997, many considered that (at least top-level) human Shogi players have a great lead on computer Shogi engines.

The situation had changed dramatically when a newcomer Shogi engine called [Bonanza](http://ja.wikipedia.org/wiki/Bonanza), developed by a Japanese chemist Kunihito Hoki, won [the 16th World Computer Shogi Championship](http://www.computer-shogi.org/wcsc16/index_e.html).  Bonanza appeared totally out of the blue --- Hoki incorporated some new ideas developed in the field of computer Chess, and Bonanza beated existing engines with no mercy.  Bonanza could even corner some professional Shogi players in 2007.  Later Hoki released(but not strictly open-source) [the source code of Bonanza](http://www.geocities.jp/bonanza_shogi/), and the standard of computer Shogi has risen considerably since then.  Finally, in the 1st Denousen last year, [Kunio Yonenaga](http://en.wikipedia.org/wiki/Kunio_Yonenaga), long retired but possibly one of the greatest Shogi players in the history, was defeated by Bonkras, a clustered version of Bonanza developed by Eiki Itoh of Fujitsu. 

The first match of Denousen this year was held yesterday between [Kouru Abe](http://ja.wikipedia.org/wiki/%E9%98%BF%E9%83%A8%E5%85%89%E7%91%A0), an 18-year old prodigy from Aomori, and Shueso, which finished in 5th at [the 22nd World Computer Shogi Championship](http://www.computer-shogi.org/wcsc22/index_e.html).  I hoped a close game, but [Abe could beat Shueso quite easily](http://live.nicovideo.jp/watch/lv118753162).  Shueso somehow could not bring its ability into full play, to my great disappointment.  Next weekend(Mar. 30), we will see [the second match](http://live.nicovideo.jp/watch/lv118754300) between [Shinichi Sato](http://ja.wikipedia.org/wiki/%E4%BD%90%E8%97%A4%E6%85%8E%E4%B8%80_%28%E6%A3%8B%E5%A3%AB%29), another young pro, and Ponanza, developed based on Bonanza by [Issei Yamamoto](http://www.graco.c.u-tokyo.ac.jp/~issei/) of The University of Tokyo.

BTW, Debian already has [the package of GPS Shogi](http://packages.debian.org/ja/source/sid/gpsshogi), which won [the 22nd World Computer Shogi Championship](http://www.computer-shogi.org/wcsc22/index_e.html) and considered by many the strongest Shogi engine available now (there is also [gnushogi](http://packages.debian.org/ja/source/sid/gnushogi) in Debian, but gnushogi is quite weak).

You may have fun with

        $ xshogi -fsp gpsshogi

Unfortunately, we don't have good modern GUI for Shogi yet...
