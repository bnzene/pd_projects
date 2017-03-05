# pd_projects
projects i'm working on in pure data:

pd motion tracking patch - a project I built gradually to learn Pure Data and, in particular, how to generate audio/MIDI output from webcam input. This does what it says on the tin; the user can set how frequently the webcam takes snapshots which are each compared to their predecessor, and the numerical output (currently mysterious to me) is filtered to different outputs which generate a MIDI signal. This was made to be hooked up to a corresponding Ableton Live project. I also used TouchOSC on iOS, via Osculator, to connect an iPhone as a MIDI controller; the separate bank of controls to the right uses the iPhone's accelerometer data to control some audio parameters of the output, including volume and a range of effects.

background_radiationscope - an oscilloscope to use alongside a static audio piece I made, generating a manipulable visualisation of the sound and, ideally, a unified audiovisual piece.

## Getting Started

Clone the repository and open any of the non-README files in Pure Data. background_radiationscope works independently; simpleMIDI for pd patch\.oscd is supplementary to  pd motion tracking patch.pd.

To run background_radiationscope, first check the box beside IN/OUT in the Pd-extended window which opens on launching the program; in the window named 'background_radiationscope.pd' edit the text 'open background_radiation.wav' (press cmd+E to enter edit mode and double-click on the text) to 'open' and the path to an audio file on your computer, pressing cmd+E to exit edit mode once finished. 
Now to start the program: go into the window named 'scope' and click the large orange toggle labelled 'on/off' to the right, and a large window labelled 'GEM' will open; when the audio starts so should the video. There will be a 30-second delay, but to bypass this click on the '1' box below 'del 30000' in the background_radiationscope window. Once it's running, have a play around with the various controls in the 'scope' window, to change the shape, size, angle and composition of the video material.

The motion tracking patch runs as soon as it's opened and loaded. The best way to use it is to play around with the various controls to change tempo, register and a range of other parameters, but to get any sound out you'll need to hook up each MIDI output to corresponding MIDI inputs on software instruments in a DAW project. Although not essential, if you want to use your iPhone as a controller you'll need to replace the IP address and port numbers on the top right of the patch with those of your own phone (incoming and outgoing port numbers are accessible in TouchOSC settings) and computer (in the Pd patch, press cmd+E to enter Edit mode; double-click on the text, replace it and cmd+E again). You'll also need to open ``` simpleMIDI for pd patch\.oscd ``` and set up your MIDI routing with the same port numbers there, as well as setting up the appropriately mapping MIDI channels between the controls in Osculator and on your phone, and between the Pure Data patch and your DAW. Nobody said this would be easy.

### Prerequisites

To run these programs you'll need to have installed [Pure Data](http://puredata.info/downloads/pure-data).
To use your iPhone as a controller, you'll also need [TouchOSC](https://hexler.net/software/touchosc) and [Osculator](https://osculator.net).

## Built With

* [Pure Data](http://puredata.info/downloads/pure-data)
* [TouchOSC](https://hexler.net/software/touchosc)
* [Osculator](https://osculator.net)

## Authors

* **Eleanor Kavanagh-Brown** - (https://github.com/bnzene)

## Acknowledgments

* Rafael Hernandez for his fantastic series of Puredata tutorials https://www.youtube.com/playlist?list=PL12DC9A161D8DC5DC
* Jerobeam Fenderson for his supremely useful downloadable puredata oscilloscope, lilscope, which enabled me to get started http://www.jerobeamfenderson.net/tagged/puredata
