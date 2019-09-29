# GCSHack

# Commands to Run the CNN
#### To Retrain the network <br>
IMAGE_SIZE=224 <br>
ARCHITECTURE="mobilenet_0.50_${IMAGE_SIZE}" <br>
python -m scripts.retrain \
  --bottleneck_dir=tf_files/bottlenecks \
  --model_dir=tf_files/models/"${ARCHITECTURE}" \
  --summaries_dir=tf_files/training_summaries/"${ARCHITECTURE}" \
  --output_graph=tf_files/retrained_graph.pb \
  --output_labels=tf_files/retrained_labels.txt \
  --architecture="${ARCHITECTURE}" \
  --image_dir=tf_files/YOUR_IMAGE_DIRECTORY_HERE <br>
  
#### To generate output <br>
python -m scripts.label_image \
    --graph=tf_files/retrained_graph.pb  \
    --image=YOUR_PATH_TO_IMAGE_HERE
