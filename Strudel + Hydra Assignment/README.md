### Studel + Hydra Peformance Patch
- So to start off with my peformance patch, I wanted to base it off of one of my favorite songs of all time, "Thinking About You" by Frank Ocean. I based this strudel patch around the chord progression and experimented with the layering of synths. 
- Initially, when experimenting with stacks with drums and synths, for some reason I kept running into issues where either only the drums would play and the synths would be silent or vice versa. I tried to troubleshoot this for a few days and couldn't find a solution. Thus, I gave up on the stack format which is a shame because it wouldv'e helped in conforming everything to make it easier to toggle certain patters on and off. However, I instead used "$:" in front of each line of code to initialize them as an individual pattern. This solved my issue of being able to play both the melodic synth parts and the drums at the same time.
- After laying out the main foundation of the song (chords, bass, and drums), this is what my code looked like:
   
        $: note("[[<[f3,a3,c4,e4] [d3,f3,a4,c4] [e3,g3,b4,d4] [c3,e3,a4,c4]>]]").sound("gm_electric_guitar_muted").delay(.6).lpf(600)
        $: note("[<[f2] [d2] [e2] [a1]>]").sound("sine").distort(0.8).attack(.05).decay(1).sustain(.5).release(.1)
        //$: note("[[<[f3,a3,c4,e4] [e3,g3,b4,d4] [eb3,g3,bb4,d4] [d3,f3,a4,c4]>]]").sound("gm_electric_guitar_muted").delay(.5).lpf(600)
        //$: note("[<[f2] [e2] [eb2] [d2]>]").sound("sine").distort(0.8).attack(.05).decay(1).sustain(.5).release(.1)

        $: sound("bd ~!2 bd ~!4").bank("RolandTR707").lpf(1000).delay(.1)
        $: sound("~!4 rim ~!3").bank("RolandTR707").delay(.2).room(0.2)
        $: sound("[[<[hh!6 oh!1 ~] [hh!6 oh!1 ~] [hh!6 oh!1 ~] [hh!2 oh!1 ~ hh!2 oh!1 ~]>]]").lpf(2000).gain("<[0.3] [0.5]>")

- To then add some visuals, I wanted to use this hydra camera effect I've been working on, it looks like this:
 
        await initHydra()
        s0.initCam()
        src(s0)
        .scale(0.9,0.5)
        .modulate(o0, ()=>Math.sin(time/2)*0.2)
        .hue(0.9)
        .saturate(3)
        .modulate(o0,-0.05)
        .blend(o0)
        .out()

- Additionally, I wanted to add a piano roll to layer on top of this that would follow the notes of the main piano chords. I achieved this by using ".pianoroll()":

        $: note("[[<[f3,a3,c4,e4] [d3,f3,a4,c4] [e3,g3,b4,d4] [c3,e3,a4,c4]>]]").sound("gm_electric_guitar_muted").delay(.6).lpf(600).pianoroll()

- I then added some variance in the drum patterns so I added a doubletime bit that I can toggle between.

        //$: sound("bd ~!2 bd ~!4").bank("RolandTR707").lpf(1000).delay(.1).gain(0.8)
        //$: sound("bd ~!2 bd ~!6 bd ~!5").bank("RolandTR707").lpf(1000).delay(.1).gain(0.8)

        //$: sound("~!4 rim ~!3").bank("RolandTR707").delay(.2).room(0.2)
        //$: sound("[~!4 rim ~!3] [~ rim ~!2 rim ~!3]").bank("RolandTR707").delay(.2).room(0.2)

- And overall, that was pretty much it with my performance patch. I wanted to keep it relatively simple but something that I could expand on production wise later on. This is what my code looked like in the end:

        await initHydra()
        s0.initCam()
        src(s0)
        .scale(0.9,0.5)
        .modulate(o0, ()=>Math.sin(time/2)*0.2)
        .hue(0.9)
        .saturate(3)
        .modulate(o0,-0.05)
        .blend(o0)
        .out()

        //$: note("[[<[f3,a3,c4,e4] [d3,f3,a4,c4] [e3,g3,b4,d4] [c3,e3,a4,c4]>]]").sound("gm_electric_guitar_muted").delay(.6).lpf(500).pianoroll()
        //$: note("[<[f2] [d2] [e2] [a1]>]").sound("sine").distort(0.8).attack(.05).decay(1).sustain(.5).release(.1)

        //$: note("[[<[f3,a3,c4,e4] [e3,g3,b4,d4] [eb3,g3,bb4,d4] [d3,f3,a4,c4]>]]").sound("gm_electric_guitar_muted").delay(.5).lpf(500).pianoroll()
        //$: note("[<[f2] [e2] [eb2] [d2]>]").sound("sine").distort(0.8).attack(.05).decay(1).sustain(.5).release(.1)

        //$: note("[[<[f4,a4,c5,e5] [d4,f4,a4,c4] [e4,g4,b4,d4][c4,e4,a4,c4]>]]").sound("sawtooth").attack(.05).decay(1).sustain(.5).release(.1).phaser(4).delay(.5).lpf(600).gain(0.3)

        //$: sound("bd ~!2 bd ~!4").bank("RolandTR707").lpf(1000).delay(.1).gain(0.8)
        //$: sound("bd ~!2 bd ~!6 bd ~!5").bank("RolandTR707").lpf(1000).delay(.1).gain(0.8)

        //$: sound("~!4 rim ~!3").bank("RolandTR707").delay(.2).room(0.2)
        //$: sound("[~!4 rim ~!3] [~ rim ~!2 rim ~!3]").bank("RolandTR707").delay(.1).room(0.2)

        //$: sound("[[<[hh!6 oh!1 ~] [hh!6 oh!1 ~] [hh!6 oh!1 ~] [hh!2 oh!1 ~ hh!2 oh!1 ~]>]]").lpf(2400).gain("<[0.3] [0.5]>")







 