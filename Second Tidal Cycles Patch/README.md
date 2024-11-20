# Second Tidal Cycles Patch Documentation
- For this week's Tidal Cycles patch, I first adjusted the cps to 110/60/4. I then started off with this bass pattern. I was experimenting with some polymetric gatherings and effects. I used the bit crush effect to add some distortion to the sub bass and adjusted the gain a bit.

        d1 $ n "[d3(3,8) f3(3,8) e3(3,8,2) a3(3,8,2)]/2" # s "sine" # crush 5 # gain 0.7
        solo 1
        unsolo 1
        mute 1
        unmute 1

- Next, I moved onto the drum pattern:

        d2 $ sound "[bd ~!2 bd ~!2 bd ~ bd ~!2 bd ~!2 bd ~]" # hpf 300 #phaserrate 0.3
        solo 2
        unsolo 2
        mute 2
        unmute 2

        d3 $ sound "bd:4!4"
        solo 3
        unsolo 3
        mute 3
        unmute 3

        d4 $ sound "~!4 sn:2 ~!7 sn:2 ~!3" # gain "0.8" # dry 0.7 # room 0.4 # size 0.8
        solo 4
        unsolo 4
        mute 4
        unmute 4

        d5 $ sound "hh!16" # gain "0.75 0.5 0.9 0.5 0.75 0.5 0.9 0.5"
        solo 5
        unsolo 5
        mute 5
        unmute 5

- First off is the "tom" sound. I used a bass drum to start off with and followed this "reggaeton" pattern and then I put a high pass filter to eq out the lows. I tried to experiment with the phaser effect but im not sure if I could hear I properly. Secondly was just a four on the floor kick pattern. Next I added the snare on beats 2 and 4 with a little reverb on it. I wanted to add a slider effect to adjust the dry and wet signal of the reverb, similar to how it was presented in class a few weeks ago in strudel but I couldn't find a similar effect. Last off was the hi hat pattern and I kept it pretty similar to last week's patch's hi hat pattern.
- After the drums, I sliced a this synth sample called "palladium". I imported it through superDirt. I've sliced it into 16 pieces and have it programmed so that it plays random sections of the 16 chops. This gives the pattern some variety as the sample itself it quite prolonged on certain chords.

        d6 $ slice 16 "[2|4|8|16]" $ s "[palladium:1]" # gain 1
        solo 6
        unsolo 6
        mute 6
        unmute 6

- Lastly I added a simple arpeggio using the pentatonic scale of the key of the sample. I added some effects including reverb, gain adjustment, release, and bit crush once more.

        d7 $ n "[d e g a b d e g a b d e g a b d e g a b]" # sound "superfm" # release 0.15 # gain "0.55" # dry 0.4 # room 0.6 # size 0.9 # crush 5
        solo 7
        unsolo 7
        mute 7
        unmute 7

- To top it all off, I added Hush

        hush        