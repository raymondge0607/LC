# First Tidal Cycles Patch With Documentation
- To start off, I was sick last week so I missed out on the basics of Tidal Cycles but I caught up through the github repository notes and some youtube tutorials and caught on pretty quickly. I recognized some of the similarities to Strudel. 
- In making a basic patch to start off with, I've been listening to a lot of Magdalena Bay recently amidst their new album a couple months ago so I decided to recreate the basic soundscape to their song "Fear, Sex". I began by setting the CPS "setcps 0.22" to initiate the tempo and in the notes I read that the function "setcps (-1)" could pause whatever's playing but for some reason I couldn't get it to work but I left it in there.
- I then started with the drums:

        -- hi hat
        d1 $ sound "hh!16" # gain "0.85 0.6 1 0.6 0.85 0.6 1 0.6 0.85 0.6 1 0.6 0.85 0.6 1 0.6"
        solo 1
        unsolo 1
        mute 1
        unmute 1

        -- snare
        d2 $ sound "~!4 sn:2 ~!7 sn:2 ~!7 sn:2 ~!4 sn:2 ~!2 sn:2 ~!3" # gain "0.8"
        solo 2
        unsolo 2
        mute 2
        unmute 2

        -- kick
        d4 $ sound "~!6 bd:1 bd:1 ~!14 bd:1 bd:1 ~!8"
        solo 4
        unsolo 4
        mute 4
        unmute 4    

- Something I really enjoy about tidal cycles are the solo/unsolo and mute/unmute functions. I like how they almost serve as buttons that u can toggle with shift-enter at anytime an are attached to whatever pattern its applied to.
- A lot of the other functions in terms of sound design are obviously very similar to Strudel. However, something I didn't like (or I may just not be aware of it yet) is how you can't really organize the effects like how you can in Strudel where you can separate them on different lines as long as the brackets are correct. I like the more organized aesthetic as opposed to on Tidal Cycles where its all on one line of code in which the pattern is initiated.

- I then moved on to other patterns:

        d6 $ n "[d f g a g f d f g a g f d f g a]" # sound "superfm" # gain "0.6" # dry 0.4 # room 0.6 # size 0.8
        d6 $ n "[cs f g a g f cs f g a g f cs f g a]" # sound "superfm" # gain "0.6" # dry 0.4 # room 0.6 # size 0.8
        d6 $ n "[c f g a g f c f g a g f c f g a]" # sound "superfm" # gain "0.6" # dry 0.4 # room 0.6 # size 0.8
        solo 6
        unsolo 6
        mute 6
        unmute 6

- I recreated this arpeggiated synth in the Magdalena Bay song, in which there are 3 different patterns that follow the change in the chord progression. Once again I had a little fun with the effects and im curious to know if there is a more effecicent to play these different patterns after each other instead of having to manually toggle them in which I have written here.

- Next up were the synth pad chords.

        d7 $ sound "[chords:4]" # dry 0.4 # room 0.6 # size 0.8 # cutoff 1300
        d7 $ sound "[chords:1]" # dry 0.4 # room 0.6 # size 0.8 # cutoff 1300
        d7 $ sound "[chords:2]" # dry 0.4 # room 0.6 # size 0.8 # cutoff 1300
        d7 $ sound "[chords:3]" # dry 0.4 # room 0.6 # size 0.8 # cutoff 1300
        solo 7
        unsolo 7
        mute 7
        unmute 7

- For these chords, I created them in Ableton and bounced them as individual one-shots. I then uploaded them to SuperDirt in a folder with the command:

        ~dirt.loadSoundFiles("/Users/raymondge/Downloads/chords/");

- I once again had a little more fun with the sound design and the effects and added the solo/unsolo and mute/unmute functions as I did with the other patterns. 
- To top all of this off, I added at the very end:

        hush
