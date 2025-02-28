<h1>How to train own object detection classifier using TensorFlow on Windows 10</h1>


<a href="https://youtu.be/ZuG-k__yFrc" target="_blank"><img src="https://github.com/maacofficial/tensorflow-train-object-detection-classiffier-tutorial/blob/master/assets/youtube.jpg" alt="How to train own object detection classifier using Tensorflow (CPU) on Windows 10"></a>
<p>Turkish translation of this tutorial is located in the lang folder. If you would like to add new translation for this guide.You can request.</p>

<p>You can train your own object detection classifier on Windows 10,8 and 7. This repository written with TensorFlow 1.5.0 version. If you try with newer version of TensorFlow and different tensorflow models version, you can receive too many errors.</p>

<p>Also i published a YouTube video for this tutorial.</p>


<h2>Statement</h2>

<p>You can use TensorFlow (GPU) instead of TensorFlow (CPU) changing "pip install --ignore-installed --upgrade tensorflow==1.5.0" to "pip install --ignore-installed --upgrade tensorflow-gpu==1.5.0" and you need to install CUDA and cuDNN.</p>

<p>If you use GPU for training,you should have Nvidia GPU for trainig object detection classifier with TensorFlow. Also your graphic card should meet minimum requirements. TensorFlow required minimum 3.5 Compute Capability for training own object detection classifier. <a href="https://developer.nvidia.com/cuda-gpus" target="_blank">Compute Capability List For Each Graphic Card</a></p>
<p>If your graphic card is medium level, it take about 3 hours. And <a href="https://www.tensorflow.org/install/source_windows#gpu" target="_blank">here</a> is a table of compatible CUDA versions with TensorFlow.</p>

<h2>Steps</h2>

<h3>1.Install Anaconda</h3>

<p>First of all we should <a href="https://www.anaconda.com/distribution/#download-section" target="_blank">download</a> Anaconda that is a free and open-source distribution of the Python for package management.</p>

<p>You can follow steps from video.</p>


<h3>2.Create TensorFlow directory</h3>

If you don't want to train another version of TensorFlow, you can download this repository directly from <a href="https://codeload.github.com/maacofficial/tensorflow-train-object-detection-classiffier-tutorial/zip/master" target="_blank">here</a>. And continue from third step.

<p>2.1. Create folder in C:/ that named "tensorflow1". This directory will include our models,object_detection and training folder. We will work in "tensorflow1" directory.</p>

<p>2.2. Download TensorFlow models repository from above links. We use TensorFlow 1.5 version in this guide.</p>

<table>
<thead>
<tr>
<th>TensorFlow version</th>
<th>GitHub Models Repository</th>
</tr>
</thead>
<tbody>
 <tr>
<td>TF v1.4</td>
<td><a href="https://github.com/tensorflow/models/tree/1f34fcafc1454e0d31ab4a6cc022102a54ac0f5b">https://github.com/tensorflow/models/tree/1f34fcafc1454e0d31ab4a6cc022102a54ac0f5b</a></td>
</tr>
<tr>
<td>TF v1.5</td>
<td><a href="https://github.com/tensorflow/models/tree/d90d5280fea4a5303affc1e28af505d8292d84b8">https://github.com/tensorflow/models/tree/d90d5280fea4a5303affc1e28af505d8292d84b8</a></td>
</tr>
 <tr>
<td>TF v1.6</td>
<td><a href="https://github.com/tensorflow/models/tree/4c05414826e87f3b8ef0534862748e4b7fcd1ec7">https://github.com/tensorflow/models/tree/4c05414826e87f3b8ef0534862748e4b7fcd1ec7</a></td>
</tr>
<tr>
<td>TF v1.7</td>
<td><a href="https://github.com/tensorflow/models/tree/adfd5a3aca41638aa9fb297c5095f33d64446d8f">https://github.com/tensorflow/models/tree/adfd5a3aca41638aa9fb297c5095f33d64446d8f</a></td>
</tr>
<tr>
<td>TF v1.8</td>
<td><a href="https://github.com/tensorflow/models/tree/abd504235f3c2eed891571d62f0a424e54a2dabc">https://github.com/tensorflow/models/tree/abd504235f3c2eed891571d62f0a424e54a2dabc</a></td>
</tr>
<tr>
<td>TF v1.9</td>
<td><a href="https://github.com/tensorflow/models/tree/d530ac540b0103caa194b4824af353f1b073553b">https://github.com/tensorflow/models/tree/d530ac540b0103caa194b4824af353f1b073553b</a></td>
</tr>
<tr>
<td>TF v1.10</td>
<td><a href="https://github.com/tensorflow/models/tree/b07b494e3514553633b132178b4c448f994d59df">https://github.com/tensorflow/models/tree/b07b494e3514553633b132178b4c448f994d59df</a></td>
</tr>
<tr>
<td>TF v1.11</td>
<td><a href="https://github.com/tensorflow/models/tree/23b5b4227dfa1b23d7c21f0dfaf0951b16671f43">https://github.com/tensorflow/models/tree/23b5b4227dfa1b23d7c21f0dfaf0951b16671f43</a></td>
</tr>
<tr>
<td>TF v1.12</td>
<td><a href="https://github.com/tensorflow/models/tree/r1.12.0">https://github.com/tensorflow/models/tree/r1.12.0</a></td>
</tr>
<tr>
<td>TF v1.13</td>
<td><a href="https://github.com/tensorflow/models/tree/r1.13.0">https://github.com/tensorflow/models/tree/r1.13.0</a></td>
</tr>
<tr>
<td>Latest version</td>
<td><a href="https://github.com/tensorflow/models">https://github.com/tensorflow/models</a></td>
</tr>
</tbody>
</table>
<p>2.3. Extract tensorflow model repository to your "tensorflow1" directory that we have created in "C:/" and rename extracted folder to "models".</p>

<p>2.4. Download "Faster-RCNN-Inception-V2-COCO" model from TensorFlow's model zoo from this <a href="https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/detection_model_zoo.md">link</a>.</p>

<p>2.5. Extract downloaded "faster_rcnn_inception_v2_coco_2018_01_28.tar.gz" file to "C:\tensorflow1\models\research\object_detection\" folder.</p>

<p>2.6. Download "Edje Electronics repository" model from this <a href="https://codeload.github.com/EdjeElectronics/TensorFlow-Object-Detection-API-Tutorial-Train-Multiple-Objects-Windows-10/zip/master">link</a>.</p>

<p>2.7. Extract downloaded "TensorFlow-Object-Detection-API.zip" file to "C:\tensorflow1\models\research\object_detection\" folder.</p>

<p>2.8. Finally your "object_detection" folder looks like this.</p>
<div><img src="https://github.com/maacofficial/tensorflow-train-object-detection-classiffier-tutorial/blob/master/assets/repos.png" width="400" height="557">
</div>


<h3>3. Create and Set up Anaconda Virtual Environment</h3>
<p>3.1 Open your command prompt as administrator.</p>
<p>3.2 Than run this command: <code>C:\>conda create -n tensorflow1 pip python=3.5</code></p>
<p><code>C:\>conda activate tensorflow1</code></p>
<p>3.3 Install TensorFlow 1.5 version: <code>C:\>pip install --ignore-installed --upgrade tensorflow==1.5.0</code></p>
<p> If you want to install TensorFlow GPU 1.5 version: <code>C:\>pip install --ignore-installed --upgrade tensorflow-gpu==1.5.0</code></p>
<p>3.4 Install TensorFlow 1.5 version: <code>C:\>pip install --ignore-installed --upgrade tensorflow==1.5.0</code></p>
<p>3.5 Install necessary packages by running following commands;<p>
<p><code>C:\>conda install -c anaconda protobuf</code><p>
<p><code>C:\>pip install pillow lxml cython jupyter matplotlib pandas opencv-python</code><p>
<p>3.6 Configure environment variable: 
<pre><code>C:\>set PYTHONPATH=C:\tensorflow1\models;C:\tensorflow1\models\research;C:\tensorflow1\models\research\slim</code></pre><p>

 
<h3>4. Compile protobufs and run setup.py</h3>
In command prompt go to research folder by running:
<pre><code>C:\>cd C:\tensorflow1\models\research</code></pre>

Then run the following commands:
<pre><code>protoc --python_out=. .\object_detection\protos\anchor_generator.proto .\object_detection\protos\argmax_matcher.proto .\object_detection\protos\bipartite_matcher.proto .\object_detection\protos\box_coder.proto .\object_detection\protos\box_predictor.proto .\object_detection\protos\eval.proto .\object_detection\protos\faster_rcnn.proto .\object_detection\protos\faster_rcnn_box_coder.proto .\object_detection\protos\grid_anchor_generator.proto .\object_detection\protos\hyperparams.proto .\object_detection\protos\image_resizer.proto .\object_detection\protos\input_reader.proto .\object_detection\protos\losses.proto .\object_detection\protos\matcher.proto .\object_detection\protos\mean_stddev_box_coder.proto .\object_detection\protos\model.proto .\object_detection\protos\optimizer.proto .\object_detection\protos\pipeline.proto .\object_detection\protos\post_processing.proto .\object_detection\protos\preprocessor.proto .\object_detection\protos\region_similarity_calculator.proto .\object_detection\protos\square_box_coder.proto .\object_detection\protos\ssd.proto .\object_detection\protos\ssd_anchor_generator.proto .\object_detection\protos\string_int_label_map.proto .\object_detection\protos\train.proto .\object_detection\protos\keypoint_box_coder.proto</code></pre>
<pre><code>(tensorflow1) C:\tensorflow1\models\research>python setup.py build</code></pre>
<pre><code>(tensorflow1) C:\tensorflow1\models\research>python setup.py install</code></pre>

<h3>5. Take and label images</h3>

<p>You can use your phone to take images. But they should be less then 200KB and their resolution should be less then 720x1280. After you take images you should copy %20 of them to "C:\tensorflow1\models\research\object_detection\images\test\" folder and %80 of them to "C:\tensorflow1\models\research\object_detection\images\train\" folder. Finally care to variety of pictures in folders.</p>

In this step we should download "LabelImg" tool to label images from <a href="https://tzutalin.github.io/labelImg/">here</a>.


<h3>6. Generate training record</h3>

<p>First we should convert images xml data to csv. To do this:</p>
<pre><code>(tensorflow1) C:\tensorflow1\models\research\object_detection>python xml_to_csv.py</code></pre>

<p>After that, edit generate_tfrecord.py with a text editor. Change label map with your own label map.</p>


<pre><code># TO-DO replace this with label map
def class_text_to_int(row_label):
    if row_label == '200TL':
        return 1
    elif row_label == '5TL':
        return 2
    else:
        None</code></pre>
 <p>TO:</p>
 
 <pre><code># TO-DO replace this with label map
def class_text_to_int(row_label):
    if row_label == 'cat':
        return 1
    elif row_label == 'dog':
        return 2
    elif row_label == 'bird':
        return 3
    elif row_label == 'person':
        return 4
    else:
        None</code></pre>
 <p>Then,generate data files by running following commands in "C:\tensorflow1\models\research\object_detection" folder:</p>
 
  <pre><code>python generate_tfrecord.py --csv_input=images\train_labels.csv --image_dir=images\train --output_path=train.record
python generate_tfrecord.py --csv_input=images\test_labels.csv --image_dir=images\test --output_path=test.record</code></pre>

<h3>7. Edit label map and configure training config</h3>
<p>Edit "C:\tensorflow1\models\research\object_detection\training\labelmap.pbtxt" with a text editor.</p>


 <pre><code>item {
  id: 1
  name: '200TL'
}

item {
  id: 2
  name: '5TL'
}</code></pre>

To:

 <pre><code>item {
  id: 1
  name: 'cat'
}

item {
  id: 2
  name: 'dog'
}
item {
  id: 3
  name: 'bird'
}
item {
  id: 4
  name: 'person'
}</code></pre>

<p>After that edit "C:\tensorflow1\models\research\object_detection\training\faster_rcnn_inception_v2_pets.config" file with a text editor to configure training.</p>

<p>a. Line 9 - Change num_classes to the number of objects you want to detect.For example; cat,dog,bird and person "num_classes:4" </p>
<p>b. Line 110 - Change fine_tune_checkpoint:
 <pre><code>
fine_tune_checkpoint: "C:/tensorflow1/models/research/object_detection/faster_rcnn_inception_v2_coco_2018_01_28/model.ckpt"</code></pre>
</p>
<p>c. Line 126-128 - Change some variables in the train_input_reader section:
 <pre><code>
train_input_reader: {
  tf_record_input_reader {
    input_path: "C:/tensorflow1/models/research/object_detection/train.record"
  }
  label_map_path: "C:/tensorflow1/models/research/object_detection/training/labelmap.pbtxt"
}
</code></pre>
</p>
<p>d. Line 140-142 - Change some variables in the eval_input_reader section:
 <pre><code>
  tf_record_input_reader {
    input_path: "C:/tensorflow1/models/research/object_detection/test.record"
  }
  label_map_path: "C:/tensorflow1/models/research/object_detection/training/labelmap.pbtxt"
  shuffle: false
  num_readers: 1
}
</code></pre>
</p>

<p>e. Line 132 -  Change num_examples to the number of images you have in the "C:\tensorflow1\models\research\object_detection\images\test" folder:
<code>num_examples: 89</code>
</p>

<p>f. Save your file and exit.</p>

<h3>8. Run the train.py</h3>

<p>If you use a newer version of TensorFlow ,train.py file is located in C:\tensorflow1\models\research\object_detection\legacy" folder. You can copy it to object_detection folder.</p>

<p>Let's run train.py! Run the following command from "C:\tensorflow1\models\research\object_detection" folder:</p>
<pre><code>python train.py --logtostderr --train_dir=training/ --pipeline_config_path=training/faster_rcnn_inception_v2_pets.config
</code></pre>

<p>When training begins, it will look like this:</p>
<div><img src="https://github.com/maacofficial/tensorflow-train-object-detection-classiffier-tutorial/blob/master/assets/screenshot.png">
</div>

<h3>9. Export inference graph</h3>

<p>When training is completed,we generate inference graph file(.pb).Change "XXXX" with your highest number in your "C:\tensorflow1\models\research\object_detection\training" folder. Please run the following command to generate file from "C:\tensorflow1\models\research\object_detection" folder:</p>
<pre><code>python export_inference_graph.py --input_type image_tensor --pipeline_config_path training/faster_rcnn_inception_v2_pets.config --trained_checkpoint_prefix training/model.ckpt-XXXX --output_directory inference_graph
</code></pre>

<p>Generated file is located in "C:\tensorflow1\models\research\object_detection\inference_graph" folder.</p>

<h3>10. Using own object detection classifier</h3>
<p>If you want to detect with webcam run "Object_detection_webcam.py" that is located in "C:\tensorflow1\models\research\object_detection" folder.Before running "Object_detection_webcam.py" file ,edit "NUM_CLASSES = 2" section. Finally run following command:</p>
<pre><code>python Object_detection_webcam.py</code></pre>

<h4>Dream until your dreams come true!!!</h4>
