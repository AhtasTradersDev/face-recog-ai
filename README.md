# Virtual Environments
## Activate Virtaul Environment
```bash
source face-recog-ai-env/bin/activate
```
## Installing OpenCV On Ubuntu
```bash 
$ sudo apt update
$ sudo apt install libopencv-dev python3-opencv
$ pip3 install opencv-contrib-python
$ python3 -c "import cv2; print(cv2.__version__)"
```

## Running extract_embedding.py
```bash
python3 extract_embeddings.py --dataset dataset         --embeddings output/embeddings.pickle         --detector face_detection_model         --embedding-model openface.nn4.small2.v1.t7

```

## Running train_model.py
```bash
python3 train_model.py --embeddings output/embeddings.pickle \
	--recognizer output/recognizer.pickle \
	--le output/le.pickle
```

## Running recognizer.py
```bash
python3 recognize.py --detector face_detection_model \
	--embedding-model openface.nn4.small2.v1.t7 \
	--recognizer output/recognizer.pickle \
	--le output/le.pickle \
	--image images/adnanahtas.jpg
```


## Running recognize_video.py
```bash
python3 recognize_video.py --detector face_detection_model \
	--embedding-model openface.nn4.small2.v1.t7 \
	--recognizer output/recognizer.pickle \
	--le output/le.pickle
```