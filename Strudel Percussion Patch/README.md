# Strudel Percussion Patch Documentation
- Starting from the studel code that I had made in class last week, the first thing I did was rewrite it in a stack format just so that it was more organized and all of the instruments weren't just on one line.

        stack (
         "[Linn9000_bd ~!5 Linn9000_bd ~ Linn9000_bd!2 ~!6]",
         "[~!4 Linn9000_sd ~!7 Linn9000_sd ~!3]",
         "[Linn9000_hh!16?]",
         "[~!6 LinnDrum_oh ~!3 LinnDrum_oh ~!5]",
        ).s()

- Following this, I felt that the hi hats and open hats were quite loud in the mix so I used...
        
        ".gain(".3!16)" 
    ... to reduce the volume of each hi hat and open hat hit to 0.3 for all 16 beats.

        stack (
        "[Linn9000_bd ~!5 Linn9000_bd ~ Linn9000_bd!2 ~!6]",
         "[~!4 Linn9000_sd ~!7 Linn9000_sd ~!3]",
         "[Linn9000_hh!16?]".gain(".3!16"),
         "[~!6 LinnDrum_oh ~!3 LinnDrum_oh ~!5]".gain(".3!16"),
        ).s()

- I slowed the speed of the loop down by adjusting the cpm (cycles per minute) value to 25.
- I then wanted to add a tom pattern so to stick with the linn drum theme I have going on, I added a middle tom and a low tom. 

        stack (
         "[Linn9000_bd ~!5 Linn9000_bd ~ Linn9000_bd!2 ~!6]",
         "[~!4 Linn9000_sd ~!7 Linn9000_sd ~!3]",
         "[Linn9000_hh!16?]".gain(".3!16"),
         "[~!6 LinnDrum_oh ~!3 LinnDrum_oh ~!5]".gain(".3!16"),
        "[~!10 LinnDrum_mt!2 ~ LinnDrum_lt ~ LinnDrum_lt]".gain("0.2!16"),
        ).s().cpm(25)   

- I then wanted to extend the length of the loop so I duplicated each instrument line and combined some of the repeated rests together. I then realized that the cpm stayed the same and that the drum loop was essentially doubletimed so I halved the cpm from 25 to 11. 

        stack (
         "[Linn9000_bd ~!5 Linn9000_bd ~ Linn9000_bd!2 ~!6 Linn9000_bd ~!5 Linn9000_bd ~ Linn9000_bd!2 ~!6]",
             "[~!4 Linn9000_sd ~!7 Linn9000_sd ~!7 Linn9000_sd ~!7 Linn9000_sd ~!3]",
         "[Linn9000_hh!32?]".gain(".3!16"),
        "[~!6 LinnDrum_oh ~!3 LinnDrum_oh ~!11 LinnDrum_oh ~!3 LinnDrum_oh ~!5]".gain(".3!32"),
         "[~!10 LinnDrum_mt!2 ~ LinnDrum_lt ~ LinnDrum_lt ~!10 LinnDrum_mt!2 ~ LinnDrum_lt ~ LinnDrum_lt]".gain("0.2!16"),
         "[Linn9000_cr ~!31]".gain("0.4!16"),
        ).s().cpm(11) 

- oh and I added a crash at the very end too.