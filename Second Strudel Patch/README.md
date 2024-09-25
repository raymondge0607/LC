# Strudel Percussion Patch Documentation
- Starting from the studel code that I had made in class last week, I wanted to add more synth layers to what I had already. I added another arpeggio, this time as a palindrom and in a higher register

        note("e6 c6 b5 g5 e5 c5").palindrome().slow(2).sound("sine").room       ("<1>").delay("<0.4>").gain("0.3"), 

- As for the bass sound, I had it randomly choosing between C1, E1, G1, and B1, all chord tones of Cmaj7. Additionally, I found that it was switching between these notes too fast so I used the ".slow(2)" command to slow the pace down.

        note ("c1!5 | e1!5 | g1!5 | b1!5").slow(2).sound("gm_synth_bass_2").gain("0.85!5").lpf(600),

- In terms of some minor mix tweaks, I thought the initial mix of the arpeggios sounded a bit muddy so I utilized some low and hi pass filters to fix some of that.

        n("7 6 4 2 0").sound("sawtooth").scale("C:major").hpf(200).lpf(500).pan("<.5 1 .5 0>").room("<1>").delay("<0.4>").gain("0.6"), 

- This is what my final patch looks like...

        stack(
         n("7 6 4 2 0").sound("sawtooth").scale("C:major").hpf(200).lpf(500).pan("<.5 1 .5 0>").room("<1>").delay("<0.4>").gain("0.6"), 
         n("2 0 7 6 4").sound("sine").scale("C:major").pan("<0 0.5 1 0.5>").room("<1>").delay("<0.4>").gain("0.6"), 
         note("e6 c6 b5 g5 e5 c5").palindrome().slow(2).sound("sine").room("<1>").delay("<0.8>").gain("0.3"), 
         note ("c1!5 | e1!5 | g1!5 | b1!5").slow(2).sound("gm_synth_bass_2").gain("0.85!5").lpf(600),
         note ("c2!5").sound("gm_synth_bass_2").gain("0.05!5").lpf(800),
         note ("b3!5").sound("gm_synth_bass_2").gain("0.25!5").lpf(800),
         note ("a3!5").sound("gm_synth_bass_2").gain("0.15!5").lpf(800),
        ).cpm(100) 


 
