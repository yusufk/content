<!--
date: '2010-06-15'
published: true
slug: 2010-06-howto-vuvuzela-filter-using-linux
time_to_read: 5
title: 'Howto: Vuvuzela filter using Linux (Ubuntu)'
-->

By now there are more than a few bog posts like this on how to filter out the resonant frequencies produced by the vuvuzela.  
  
I wasn't too happy with any of them and thought I'd share what I came up with after some tinkering.  
  
For the impatient:  
  
To install required tools:  
> sudo apt-get install sox

  
To test:  
> play vuvuzela.wav vol 0.9 bandreject 116.56 3.4q bandreject 233.12 3.4q bandreject 466.24 3.4q bandreject 932.48 3.4q bandreject 1864 3.4q

  

The test file can be downloaded [here](http://ubuntuone.com/p/78M/).

  

My starting point for this was [a post by](http://www.russellbeattie.com/blog/linux-command-line-streaming-vuvuzela-filter) Russell Beattie, where he describes his attempts at using [SoX](http://sox.sourceforge.net).

  

You can test both approaches (using an equalizer vs. using a band-reject filter), and I think the latter does a better job. I also used slighty more accurate frequencies as suggested [here](http://fetzig.org/2010/06/13/vuvuzela-filter-using-fedora/#comment-190) and added an additional lower resonant frequency at 116.56 because I could still here a faint toot.

  

Russell chose to use [Octave](http://en.wikipedia.org/wiki/Octave) to define the width around the central frequency that is removed (.1o), whereas I prefer using the [Q-factor](http://en.wikipedia.org/wiki/Q_factor) as did the [original German Blog post on this](http://www.surfpoeten.de/tube/vuvuzela_filter) subject (3.4q)

  
To use:  
> rec -d|play -d vol 0.9 bandreject 116.56 3.4q bandreject 233.12 3.4q bandreject 466.24 3.4q bandreject 932.48 3.4q bandreject 1864 3.4q

  
Assuming your default sound input source is the your line-in or tv-tuner.  
  
Updated: I updated the fundamental and harmonics as per [this site](http://decibel.ni.com/content/blogs/Simon/2010/06/16/world-cup-2010--filtering-the-annoying-vuvuzela-noise).  
  
Updated again: The above update should have been better, theoretically, but it isn't.  
  
Vuvuzela Frequencies  
  
Fundamental: 232.4 Hz  
  
Harmonic 1: 464.8  
  
Harmonic 2: 697.2  
  
Harmonic 3: 929.6  
  
Harmonic 4: 1162  
  
Harmonic 5: 1394.4  
  
Harmonic 6: 1626.8  
  
Harmonic 7: 1859.3



## 4 comments captured from [original post](https://ysfk.blogspot.com/2010/06/howto-vuvuzela-filter-using-linux.html) on Blogger

**Christoph said on 2010-06-15**

Indeed, this works quite good!

**Yusuf said on 2010-06-15**

I wonder if SoX is available on the iPhone or Android? It would be cool if one could implement this on a mobile for taking with into the stadium, instead of earplugs!

**Vuvuzela Filter with Ubuntu Lucid, PulseAudio &amp; LADSPA – Help Needed « Christian Neumair said on 2010-06-16**

[...] The most convincing filter prototype for notch filtering is used by sox, as pointed out by Yusuf. It is a simple biquadratic filter based on Robert Bristow-Johnson’s great Audio Cookbook, [...]

**Yusuf said on 2010-06-19**

The version that you saw (prior to my latest update) screwed things up. It should theoretically have been better, but it introduced the strange bathroom sound. Please try the reverted settings: play vuvuzela.wav vol 0.9 bandreject 116.56 3.4q bandreject 233.12 3.4q bandreject 466.24 3.4q bandreject 932.48 3.4q bandreject 1864 3.4q



[Original post](https://ysfk.blogspot.com/2010/06/howto-vuvuzela-filter-using-linux.html)

#howto #linux #ubuntu #world cup #legacy-blogger 