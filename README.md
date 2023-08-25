# Link for sharing the data of my silique detection project on Google Drive(See details of Folds in Google Drive in the Reference below)

https://drive.google.com/drive/folders/1exa6yb4qGhfI0TRP9_xQLssUN6lyq86s?usp=sharing

# Link for download Mask-RCNN(If do not want to ues the one on the Google Drive)

https://github.com/matterport/Mask_RCNN

# Instruction for training model and testing testing model(indexes of the cells in the BrassicaDection.ipynb file)

## Contents in this fold
Bra017testing contains 2 brassica017 images for testing
Bra0022testing contains 2 brassica017 images for testing 
TestModel contains the best model for this project
BrassicaDection.ipynb file runs on Google Colaboratory
README file is the instruction of the project

## Seeting the Google Colaboratory ready for the project

(2)->(1)->(3)->(4)->(5)

In (2), uncomment the code or click the icon of files and then click the icon of mount drive to connect the google drive
In (1), click Runtime -> Change runtime type - GPU, then choose to run the free version GPU or subscription version by runing different codes
In (4), after installing the q keras ==2.1.6 need to restart run time to activate
In (5), setting the path of mask-rcnn and the different path for different models, details see below

## Testing

### Testing image without an annotation file

(2)->(1)->(3)->(4)->(5)->(6)->(11)->(16)->(17)->(18)->(19)I

Things need to take in mind:
In (2), uncomment the code or click the icon of files and then click the icon of mount drive to connect the google drive
In (1), click Runtime -> Change runtime type - GPU, then choose to run the free version GPU or subscription version by runing different codes
In (4), after installing the q keras ==2.1.6 need to restart run time to activate
In (5), TEST_IMAGE_DIR(change the fold you like, in this fold Bra017testing and Bra022testing can be put in this valuable) for (19)I, 
SILIQUES_MODEL_PATH(change a weight for infering model) for (17)
In (19)I, run the code in the cell "Testing images without annotation files"

### Testing image with an annotation file

(2)->(1)->(3)->(4)->(5)->(6)->(7)->(8)->(9)->(10)->(11)->(16)->(17)->(18)->(19)I

Things need to take in mind:
in (2),(1),(4), tha same as testing image without an annotation file
in (5) val_annotation_file(change a validation CSV file you like)and annotation_file(change a training CSV file you like) for (7),
IMAGE_DIR(change the corresponding fold of images for val_annotation_file and annotation_file) for (8),
SILIQUES_MODEL_PATH(change a weight for infering model, the weight in the TestModel can be put in this valuable) for (17)
In (19)I, run the code in the cell "Testing images with annotation files"

In this section, you can run all codes after (19)I until the end for evaluation

##Training

(2)->(1)->(3)->(4)->(5)->(6)->(7)->(8)->(10)->(11)->(12)->(13)->(14)->(15)

Things need to take in mind:
in (2),(1),(4), tha same as testing image without an annotation file
in (5) val_annotation_file(change a validation CSV file you like)and annotation_file(change a training CSV file you like) for (7),
IMAGE_DIR(change the corresponding fold of images for val_annotation_file and annotation_file) for (8)

In this section, you can run all codes after (15)Iuntil the end for testing and evluation if you do not close the window

# Reference

## Tittle of each index above
(1) Add GPU and RAM for colab
(2) Mounting Google Drive for Colab
(3) Import libraries for the project
(4) Correct version of TensorFlow and its support
(5) Correct path from Google Drive to Colab for the project
(6) Import mask-rcnn for the project
(7) Add training datasets and validation datasets
(8) Create a class for datasets
(9) Functions for testing
(10) Loading annotation of datasets to object
(11) Configuration for model
(12) Create a training model
(13) Add a weight to the training model
(14) Training the model
(15) Save the training model
(16) Setting inference configuration
(17) Create an inference model and add weight to the model
(18) Add names of the classes
(19) Predictions
     I. Randomly predict an image for validation dataset and having some statistic evaluation
	    1) Precision-recall curve
		2)Grid of ground truth objects and their predictions
		3)Compute mAP @ IoU=50 on Batch of Images
	 II. Save and evaluate prediction of entire datasets
	    1) Save validation images and its annotation
		2) Save validation images and its predicted annotation
	    3) Save as CSV file for prediction
		4) Save as pkl file for prediction
		5) Visualization for Evaluation
(20) Evaluation by analysing the features of siliques collected from prediction
     I. Get data from correct fold saving data of a dataset prediction
	 II. Collect and organise data from validation and perdiction
	 III. Scatter chart, regression line, and R-square for the length of siliques per image
	 IV. Line chars for comparing the length of siliques for per image against validation data and prediction data
	 V. Compare number of siliques per image against validation and prediction by histogram
	 VI. Compare average length per image against validation and prediction by histogram
	 VII. Compare total number of bounding boxes of entire dataset against validation and prediction by histogram

## Folds in Google Drive
“Detection” fold contains “Brassica” fold and “Mask_RCNN”. There is another BrassicaDection.ipynb
“Mask_RCNN” fold contains weights of models, all examples of Mask-RCNN , and libraries of Mask-RCNN  and the project has to use it to build the training model and testing model.
“Brassica” fold contains all rest folds except the three above. It is the storage for all datasets, testing results and logs.
“Val_images_brassica022” fold has the images of brasscia022 used for validation.
“Val_annotation” fold has all annotation datasets that are CSV files for validation.
“Train_annotation” has all annotation datasets that are CSV files for validation.
“Scripts” fold contains a Python script “utils1.py” derived from the Mask-RCNN  library utils.py. it comes from my supervisor and it fits the program better and will be used instead of the Mask-RCNN  library utils.py in this project.
“Save_pre_val_brasscia022” saves the prediction and validation images of brassica022 with bounding boxes, scores and labels.
“Save_pre_val” saves the prediction and validation images of brassica017 with bounding boxes, scores and labels.
“Save_pre_pkl_brasscia022” saves annotation data of prediction to “.pkl” files for the brassica022 dataset.
“Save_pre_pkl” saves annotation data of prediction to “.pkl” files for the brassica017 dataset.
“Save_CSV022” saves annotation data of prediction to CSV files for the brassica022 dataset.
“log” saves the records for training models.
“Image” fold contains brassica017(100 images) will be used to train and validate the model.
“images_and_022” fold contains brassica022(20 images) with brassica017(100 images) will be used to train and validate the model.
“Annotation” has the CSV annotation file combining the total information of training annotation and validation annotation.

##Important variables for path
ROOT_DIR = os.path.abspath("/content/drive/MyDrive/Detection") is the main path of  the project, all the contents required are under this path.
Mask_RCNN_DIR = os.path.join(ROOT_DIR, "Mask_RCNN") mounts the contents of Mask-RCNN  to Colab.
BRASSICA_DIR = os.path.join(ROOT_DIR, "Brassica") is the main path for fetching data, updating data, storing logs, and saving files. The specific path for specific content will be under this path.
ANNOTATION_DIR = os.path.join(BRASSICA_DIR, "Train_annotation") is a path of fold containing CSV files.
annotation_file = os.path.join(ANNOTATION_DIR, "annot_train_bra022.csv") is a path for training CSV file.
IMAGE_DIR = os.path.join(BRASSICA_DIR, "Image") is a path leading to images, can be changed againse the CSV files.
VAL_ANNOTATION_DIR = os.path.join(BRASSICA_DIR, "Val_annotation") is a path of CSV datasets of validation fold.
val_annotation_file = os.path.join(VAL_ANNOTATION_DIR, "annot_val.csv") is a path leading to a CSV file of validation can be changed to fir the training CSV files.
MODEL_DIR = os.path.join(BRASSICA_DIR, "log") is the training model log path.
TEST_IMAGE_DIR = os.path.join(BRASSICA_DIR, "Image") is used to testing images without annotation.
COCO_MODEL_PATH = os.path.join(Mask_RCNN_DIR, "mask_rcnn_coco.h5") is the path for default weight of Mask-RCNN .
SILIQUES_MODEL_PATH = os.path.join(Mask_RCNN_DIR, "Siliques_mask_rcnn_trained_1.h5") is a path for saving weight for a training model. And for the weight of testing model.
