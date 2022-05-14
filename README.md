# GeoQA-Plus
Download GeoQA+ benchmark [<a href="https://drive.google.com/file/d/1KL4_wIzr3p8XSKMkkLgYcYwCbb0TzZ9O/view?usp=sharing">Google Drive</a>]
Download the data.zip, move it to /data/GeoQA2.2 path, and unzip it. json-image_files contains all Original problems we collected, GeoQA-train.pk is the traing of GeoQA, Mix-train.pk are the training set after mixing our newly annotated problems，Backtrans-train.pk is the training set after performing data augmentation on Mix-train, new-test.pk is the test formed by our new dataset. When using data files as training sets make sure to rename the corresponding data files to "train.pk".
# Environment
pip install -r requirement.txt

# Train the model
cd GeoQA+
unzip and rename the dataset
run: allennlp train config/NGS_Aux.json --include-package NGS_Aux -s save/test

#Evaluation
run: allennlp evaluate save/test  data/GeoQA3/test.pk --include-package NGS_Aux_test --cuda-device 0
