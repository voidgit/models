# After forked from https://github.com/tensorflow/models (insturction added below is intended for personal usage and provided "as is"):

Exapmle was done by following instructions from: ENG: https://blog.kovalevskyi.com/rnn-based-chatbot-for-6-hours-b847d2d92c43 , RU: https://www.youtube.com/watch?v=Oo3DgYTL-Nw&list=PLsQAG1V_t58COuo7oRYsvdvwa9mfUK8RS&index=6 / https://habrahabr.ru/post/317732/

Everything was executed on local machine - Win 10 x64/Nvidia 1070/tensorflow-gpu

Model was trained for 1-2h. Should be trained at much more. Please check links above.

----------------------

* If you want to prepare training set youself run https://github.com/b0noI/dialog_converter
* On Win10 64x(provided "as is", haven't checked for safety) download following *.whl from http://www.lfd.uci.edu/~gohlke/pythonlibs/) 
** pip install numpy-1.13.3+mkl-cp36-cp36m-win_amd64.whl
** pip install scipy-1.0.0rc1-cp36-cp36m-win_amd64.whl

----------------------

* Install tenosrflow (or tensorflow-gpu) per https://www.tensorflow.org/install/ (currently TensorFlow 1.3)
* Clone this git repository
* cd /tutorials/rnn/translate
* Unarchive directory 'train' from https://files.fm/u/f4jnppq4 or from https://ufile.io/owfs2
(File: train.zip
	CRC-32: b0a486a5
	MD4: abb1f343193ce57fc4bf9150da3a843c
	MD5: 35b86a7a57358dafb24f9fce1bb43871
	SHA-1: 11f157a68bfb22673185698d5e0a26a2fcbe5c0b)
* To continue training model 'python ./translate.py  --en_vocab_size=40000 --fr_vocab_size=40000 --data_dir=./train --train_dir=./train'
* To run model (it was not trained enough so do not expect much): 'python ./translate.py  --en_vocab_size=40000 --fr_vocab_size=40000 --data_dir=./train --train_dir=./train --decode' (P.S. do not run both training and execution on default configuration)

	
P.S. changes include 
* Copy/paste from https://github.com/b0noI/tensorflow
* Changes at https://github.com/voidgit/models/blob/master/tutorials/rnn/translate/translate.py#L82 which probably at least partially crippling the logic. Was done to circumwent https://github.com/tensorflow/models/issues/1790 . There is a chance that issue is caused by Windows10/Python(3.6.3 x64)/TensorFlow stack - going to try Ubuntu on the same machine... If you know how to fix it please reply to the issue.


# TensorFlow Models

This repository contains a number of different models implemented in [TensorFlow](https://tensorflow.org):

The [official models](official) are a collection of example models that use TensorFlow's high-level APIs. They are intended to be well-maintained, tested, and kept up to date with the latest stable TensorFlow API. They should also be reasonably optimized for fast performance while still being easy to read. We especially recommend newer TensorFlow users to start here.

The [research models](research) are a large collection of models implemented in TensorFlow by researchers.

The [tutorial models](tutorials) are models described in the [TensorFlow tutorials](https://www.tensorflow.org/tutorials/).
