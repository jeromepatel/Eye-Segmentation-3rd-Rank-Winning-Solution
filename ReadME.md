# 3D Eye Segmentation - 3rd Rank Winning Solution 

## Instructions:
There are two separate scripts for Training and Testing.
### Training:
* Training can be done using `train_eyesemseg.py`. To use CPU when training, use `--gpu 0`and by default GPU option is enabled.
* Place the dataset in `data/eyeseg` directory, please make sure it includes `train` and `val` part inside them. 
* Install all the necessary libraries mentioned inside `requirements.txt`.
* Simply run the command `python train_eyesegmseg.py` for default arguments, which include `gpu 1` and `epoch 32` too.

The model will train for 32 epochs and will save the pretrained model inside `log/eyeseg/*` directory. 
### Inference:
* Testing can be done using `test_eyesemseg.py`. GPU and CPU option are available for testing as well, using `gpu 0`.
* Important arguments are `--log_dir pre_trained_model/2021-08-14_19-08`, `--test_dir test/val` `--save_labels True/False`. `--valid` can be used if the labels for the test_dir are present inside the directory(eg. in case of val)
* Finally to run the inference from pre_trained_model (provided by us), run the command `python test_eyesemseg.py --log_dir pre_trained_model --test_dir test --save_labels True`.
* The labels can be found as *.npy files inside output folder. 
* To create json file from npy labels, use `create_json_ss.py` script by running the command `python create_json_ss.py --list-file submissionFiles.txt --submission-json pointnet2Submission.json`
