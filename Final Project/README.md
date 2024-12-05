# Final Project Documentation
- For this final project in Tidal Cycles, I started off with using a sliced sample again, just as I did with my second tidal cycles patch. I found this sample in my sample library called "Fade" by Ryuichi Sakamoto and I took a portion of it and imported it into SuperCollider. To start my code off, I wrote:

        d1 $ striate 2 $ slice 8 "[2|4|8|16]" $ s "[sakamoto:3]" # size 0.9 # delay 0.9 #lpf 300 # gain 1
        solo 1
        unsolo 1
        mute 1
        unmute 1

- With this sample, I experimented with the "striate" effect which essentially creates a granular effect on the sample itself. The higher number  multiplied by 2 (128, 256, 512, 1024, etc.) the more "de-sampled" and grainier it sounded which added a cool effect. As usual, I added a room reverb, delay, and a low-pass filter that I will be adjusting throughout the performance. 

- I then began setting some drums. Here's what it looks like:

        --stutter kicks
        d1 $ rev $ stut 3 0.5 0.125 $ sound "[sakamoto:1](3,8)"
        d1 $ stut' 1 0.125 (|*| gain "0.8") $ sound "[sakamoto:1](3,8)"
        solo 1
        unsolo 1
        mute 1
        unmute 1

        --metro hi hat
        d2 $ sound "hh*4" # n "0 0 0 0"
        solo 2
        unsolo 2
        mute 2
        unmute 2

        d3 $ sound "~!4 sn:2 ~!7 sn:2 ~!3" # gain "0.8" # dry 0.7 # room 0.4 # size 0.8
        solo 3
        unsolo 3
        mute 3
        unmute 3

- For the kicks, I was experimenting with the stutter feature in "stut" and playing around with the 3 parameters. In terms of the kick sample I used, I used on I found in my sample library and connected it in the same folder as the Ryuichi Sakamoto sample, "hence the Sakamoto:1 name". I came up with two stutter kick patterns, the top one being much busier than the other below.

- The hi hat pattern was initially made as a metronome so I could keep the beat whilst listening to the stutter kick patterns. However I kept it in and didn't change anything to it so it's just playing eightnotes.

- The snare pattern is pretty simple as well, just playing on beats 2 and 4 with some reverb.

- Next, I added an arpeggio to add some melodic color to the sample.

        d4 $ slow 0.5 $ sound "supersaw*8" # n "12 17 19 24 29 24 19 17" # lpf 800 # legato 0.5 # room 0.6 # size 0.9 # gain 0.6 # delay 0.7 # phaserrate 0.3
        solo 4
        unsolo 4
        mute 4
        unmute 4

- After some rearrangement of the code as a whole, this is what my final project looks like:

        setcps (110/60/4)

        --stutter kicks
        d1 $ rev $ stut 3 0.5 0.125 $ sound "[sakamoto:1](3,8)"
        d1 $ stut' 1 0.125 (|*| gain "0.8") $ sound "[sakamoto:1](3,8)"
        solo 1
        unsolo 1
        mute 1
        unmute 1

        --metro hi hat
        d2 $ sound "hh*4" # n "0 0 0 0"
        solo 2
        unsolo 2
        mute 2
        unmute 2

        d3 $ sound "~!4 sn:2 ~!7 sn:2 ~!3" # gain "0.8" # dry 0.7 # room 0.4 # size 0.8
        solo 3
        unsolo 3
        mute 3
        unmute 3

        d4 $ slow 0.5 $ sound "supersaw*8" # n "12 17 19 24 29 24 19 17" # lpf 800 # legato 0.5 # room 0.6 # size 0.9 # gain 0.6 # delay 0.7 # phaserrate 0.3
        solo 4
        unsolo 4
        mute 4
        unmute 4

        --striate range from 2 -> 4096
        d5 $ striate 2 $ slice 8 "[2|4|8|16]" $ s "[sakamoto:3]" # size 0.9 # delay 0.9 #lpf 200 # gain 1
        solo 5
        unsolo 5
        mute 5
        unmute 5

        --bass 8th notes
        d6 $ slow 1 $ sound "supersaw*8" # n "-24" # lpf 200 # crush 5 # gain 0.9
        --I
        d6 $ slow 1 $ sound "supersaw*8" # n "-26" # lpf 200 # crush 5 # gain 0.9
        --bVII
        d6 $ slow 1 $ sound "supersaw*8" # n "-28" # lpf 200 # crush 5 # gain 0.9
        --bVI
        d6 $ slow 1 $ sound "supersaw*8" # n "-29" # lpf 200 # crush 5 # gain 0.9
        --V
        d6 $ slow 1 $ sound "supersaw*8" # n "-31" # lpf 200 # crush 5 # gain 0.9
        --IV
        d6 $ slow 1 $ sound "supersaw*8" # n "-33" # lpf 200 # crush 5 # gain 0.9
        --bIII
        d6 $ slow 1 $ sound "supersaw*8" # n "-34" # lpf 200 # crush 5 # gain 0.9
        --II
        d6 $ slow 1 $ sound "supersaw*8" # n "-36" # lpf 200 # crush 5 # gain 0.9
        --I
        solo 6
        unsolo 6
        mute 6
        unmute 6


        hush

