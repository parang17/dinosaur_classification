# Dinosaur Classification

A machine learning model for native mobile devices to perform dinosaur image classification using TensorFlow Lite. This ML model is integrated with flutter environment for mobile application.
[Flutter DinoFinder](https://github.com/iRyanBell/flutter_dinofinder) The code is based on Google Tensorflow model (The link is in Reference section).  

## Image scroller:

To collect training data-set for dinosaur image classification, the image scroller that efficiently collects image data is implemented. The image scroller link is as follows:
[Google Image Scroller](https://github.com/parang17/Google_image_downloader)

## Train the network:
For the dinosaur classification problem, it uses mobilenet provided by Tensorflow.
In the terminal, 
```
IMAGE_SIZE=224
ARCHITECTURE="mobilenet_0.50_${IMAGE_SIZE}"

python -m scripts.retrain \
  --bottleneck_dir=tf_files/bottlenecks \
  --how_many_training_steps=500 \
  --model_dir=tf_files/models/ \
  --summaries_dir=tf_files/training_summaries/"${ARCHITECTURE}" \
  --output_graph=tf_files/retrained_graph.pb \
  --output_labels=tf_files/retrained_labels.txt \
  --architecture="${ARCHITECTURE}" \
  --image_dir=data
```

## Test the network:
In the terminal, 
```
python -m scripts.label_image \
    --graph=tf_files/retrained_graph.pb  \
    --image=data/Dimetrodon/Dimetrodon_0001.jpg
```


## Reference:

[TensorFlow For Poets](https://codelabs.developers.google.com/codelabs/tensorflow-for-poets/index.html#0)
