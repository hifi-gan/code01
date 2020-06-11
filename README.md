# Code01

## Pre-requisites
1. Python >= 3.6
2. Clone this repository.
3. Install python requirements. Please refer [requirements.txt](requirements.txt)
4. Download and extract the [LJ Speech dataset](https://keithito.com/LJ-Speech-Dataset/).
And move all wav files to `LJSpeech-1.1/wavs`


## Training
```
python train.py --config config_v1.json
```
To train V2 or V3 Generator, replace `config_v1.json` with `config_v2.json` or `config_v3.json`.<br>
Checkpoints and copy of the configuration file are saved in `cp_hifigan` directory by default.<br>
You can change the path by adding `--checkpoint_path` option.


## Pretrained Model
[Download](https://drive.google.com/file/d/1_Z2X_pKnMBOTQ1Ihk1rbtAhjAAdbf3Mp/view?usp=sharing)


## Inference from wav file
1. Make `test_files` directory and copy wav files into the directory.
2. Run the following command.
```
python inference.py --checkpoint_file [generator checkpoint file path]
```
Generated wav files are saved in `generated_files` by default.<br>
You can change the path by adding `--output_dir` option.


## Inference for end-to-end speech synthesis
1. Make `test_mel_files` directory and copy mel-spectrogram files into the directory.<br>
You can generate mel-spectrograms using [Tacotron2](https://github.com/NVIDIA/tacotron2).
2. Run the following command.
```
python inference_e2e.py --checkpoint_file [generator checkpoint file path]
```
Generated wav files are saved in `generated_files_from_mel` by default.<br>
You can change the path by adding `--output_dir` option.
