Companion github repository for the paper ["Exploring Polyphonic Accompaniment Generation using Generative Adversarial Networks"](https://smcsweden.se/proceedings/SMC2023_proceedings.pdf#page=198), accepted in SMC-2023. The paper deals with the generation of symbolic multi-track music (as pianorolls), in two different setups:

i) *Unconditional* generation (the multi-track pianoroll is generated without any prior condition provided by the human user)

ii) *Conditional* generation (a single instrumental track is provided as conditional input; the network generates the rest of the tracks as accompaniment)

The repo currently contains: Generated audio samples using both the unconditional and the conditional model architectures developed.

**On The Uploaded Samples**

Generated samples have been uploaded, in .wav format, for both *unconditional* and *conditional* cases, in the respective folders. Since our models were trained using the Lakh MIDI dataset, the multi-track pieces generated contain tracks for bass, drums, guitar, piano and strings. To convert the generated pianorolls to .wav files,[pypianoroll](https://github.com/salu133445/pypianoroll) was used to get MIDI files as an intermediate representation, and the MIDI files were converted to .wav files using [timidity++](https://timidity.sourceforge.net/).

The unconditional folder contains generated music tracks with all 5 instruments.

The conditional folder contains ground-truth single-instrument tracks, as well as the respective generated accompaniments, for 2 conditional instruments: piano and guitar, and 4 different training configuration for each conditional case:

i) global: Only one global discriminator was used, and the conditional embedding encoder was trained jointly with the discriminator.

ii) global_ae: Only one global discriminator was used, but the conditional embedding encoder was trained separately, with a reconstruction loss objective.

iii) global_local: Two discriminators, one global (for the whole multi-track) and one local (for the generated accompaniment only) were used, whereas the conditional embedding encoder was trained jointly with the discriminator.

iv) Two discriminators, one global (for the whole multi-track) and one local (for the generated accompaniment only) were used, whereas the conditional embedding encoder was trained separately, with a reconstruction loss objective.

Code to be uploaded soon!


