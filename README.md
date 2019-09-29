# Cello-Tuner-Metronome-Code-File
// Play metronome @120bpms (allegro) when screen is up
input.onGesture(Gesture.ScreenUp, function () {
    basic.showNumber(120)
    music.setTempo(120)
    basic.clearScreen()
})
// Play metronome @72bpms (adagio) when screen is down
input.onGesture(Gesture.ScreenDown, function () {
    basic.showNumber(72)
    music.setTempo(72)
    basic.clearScreen()
})
// Play a "C" tone when button "A" is pressed
input.onButtonPressed(Button.A, function () {
    for (let i = 0; i < 2; i++) {
        basic.showLeds(`
            . # # # .
            # . . . .
            # . . . .
            # . . . .
            . # # # .
            `)
        music.playTone(131, music.beat(BeatFraction.Breve))
        basic.clearScreen()
    }
})
// Play a "D" tone when both buttons "A" and "B" are
// pressed
input.onButtonPressed(Button.AB, function () {
    for (let i = 0; i < 2; i++) {
        basic.showLeds(`
            # # # . .
            # . . # .
            # . . # .
            # . . # .
            # # # . .
            `)
        music.playTone(294, music.beat(BeatFraction.Breve))
        basic.clearScreen()
    }
})
// Play a "G" tone when button "B" is pressed
input.onButtonPressed(Button.B, function () {
    for (let i = 0; i < 2; i++) {
        basic.showLeds(`
            . # # # .
            # . . . .
            # . # # .
            # . . # .
            . # # # .
            `)
        music.playTone(196, music.beat(BeatFraction.Breve))
        basic.clearScreen()
    }
})
// Play an "A" tone when micro bit is tilted to the
// left
input.onGesture(Gesture.TiltLeft, function () {
    for (let i = 0; i < 2; i++) {
        basic.showLeds(`
            . # # # .
            # . . . #
            # # # # #
            # . . . #
            # . . . #
            `)
        music.playTone(440, music.beat(BeatFraction.Breve))
        basic.clearScreen()
    }
})
basic.showString("Cello Tuner")
basic.clearScreen()
