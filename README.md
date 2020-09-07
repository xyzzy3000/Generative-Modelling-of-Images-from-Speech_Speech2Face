# Speech2Face

This project implements a framework to convert speech to facial features as described in the CVPR 2019 paper - [Speech2Face: Learning the Face Behind a Voice](https://arxiv.org/pdf/1905.09773.pdf) by MIT CSAIL group.

### Getting Started

1. Go to preprocess folder and run `prepare_directory.sh` and then download AVSpeech Dataset. Run `data_download.py` file for data download from youtube based on AVSpeech Dataset.
```
cd preprocess/
sh prepare_directory.sh
```
Download [AVSpeech Dataset](https://looking-to-listen.github.io/avspeech/download.html) in the folder.
```
python3 data_download.py
usage: data_download.py [-h] [--from_id FROM_ID] [--to_id TO_ID]
                        [--low_memory LOW_MEMORY] [--sample_rate SAMPLE_RATE]
                        [--duration DURATION] [--fps FPS] [--mono MONO]
                        [--window WINDOW] [--stride STRIDE]
                        [--fft_length FFT_LENGTH] [--amp_norm AMP_NORM]
                        [--face_extraction_model FACE_EXTRACTION_MODEL]
                        [--verbose]
```
2. Now run the base file with train option if you want to train.
```
python3 base.py
usage: base.py [-h] [--from_id FROM_ID] [--to_id TO_ID] [--epochs EPOCHS]
               [--start_epoch START_EPOCH] [--batchsize BATCHSIZE]
               [--num_gpu NUM_GPU] [--num_samples NUM_SAMPLES]
               [--load_model LOAD_MODEL] [--save_model SAVE_MODEL] [--train]
               [--verbose]
```

## Results
We have used face retrieval performace as a evaluation metric and we are able to achieve a decent accuracy. Increasing the computation power and using complete dataset can help us achieve greater accuracy.

<p align="center">
    <img src="results/result1.png" alt="Image"/>
</p>
<p align="center">
    <img src="results/result2.png" alt="Image" width="800" height="700"/>
</p>


## Future Work
1. Implementation of the Face Decoder Model, which takes as input the face features predicted by Speech2Face model and produces an image of the face in a canonical form (frontal-facing and with neutral expression).
2. The pretrained Face Decoder Model used by the paper was not available and the model was based on another CVPR paper (Synthesizing Normalized Faces from Facial Identity Features)
3. We tried implementing the model but this required lots of data for the model to train properly and the result was not even human recognizable.
4. As the main focus of the project was on Speech Domain, we plan to complete this Vision task in the future.


## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## References
1. Speech2Face: Learning the Face Behind a Voice (https://arxiv.org/pdf/1905.09773.pdf)
2. Wav2Pix: Speech-conditioned face generation using generative adversarial networks (https://arxiv.org/pdf/1903.10195.pdf)
3. AVSpeech Dataset (https://looking-to-listen.github.io/avspeech/download.html)
