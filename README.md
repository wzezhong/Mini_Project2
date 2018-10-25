# Mini_project2
First, I used tensor flow to study how to deep learning. I used tensorflow tutorial to trained my first part flowers. After I finished the tutorial part of the flowers, I retrained myself part which include cars, suv and truck. If you want to training my part of three kinds of cars, you can download my car photos which included in my photos directory. Also, you can use "googleimagesdownload" function to download some photos. As the following is the tutorial of how to use tensorflow to recognitization images. All of steps in the tutorial, I don't explain it at here. You need to make sure you have installed tensorflow first. Command is "pip install --upgrade tensorflow 1.7.*". https://www.tensorflow.org/hub/tutorials/image_retraining

Second classifier uses the Tensorflow Inception v3 model.
It is a transfer learning model built by Google and trained on the ImageNet Large Visual Recognition Challenge dataset. This portion is implemented according to the codelabs tutorial at https://codelabs.developers.google.com/codelabs/tensorflow-for-poets/#0

To train the model, run:

python -m retrain 
--bottleneck_dir=tf_files/bottlenecks 
--how_many_training_steps=500 
--model_dir=tf_files/models/ 
--summaries_dir=tf_files/training_summaries/"${ARCHITECTURE}" 
--output_graph=tf_files/retrained_graph.pb 
--output_labels=tf_files/retrained_labels.txt 
--architecture="${ARCHITECTURE}" 
--image_dir=tf_files/flower_photos

in order for the inception model to work you will need to save the following as local variables in the Unix shell

IMAGE_SIZE=224

ARCHITECTURE="mobilenet_0.50_${IMAGE_SIZE}"

Third run the program
    Just run the program with the path of a .jpg image as an argument

    example: python run.py "/path/image.jpg"
   dependencies
   
Fourth I offered some environment what you need to set first
    pip install opencv-python # installs opencv 
    
   pip install sklearn # installs scikit-learn
   
   brew install bazel # you'll need java8 for this
   
   git clone https://github.com/tensorflow/tensorflow.git
    
   cd tensorflow
    
   git checkout v1.9.0
    
   ./configure
    
   bazel build --config=opt 
    
   //tensorflow/tools/pip_package:build_pip_package 
    
   //tensorflow:libtensorflow_framework.so 
   
   //tensorflow:libtensorflow.so
    
   bazel-bin/tensorflow/tools/pip_package/build_pip
