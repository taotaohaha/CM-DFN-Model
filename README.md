# CM-DFN-Model
 Image-Non-Image Cross-Modal Data Fusion Network (CM-DFN)
For code files see: CM_DFN.zip
The dataset file is available at: data_1.zip
The ANN training run method is:
In the dataset.xlsx file (in the dataset) place the required non-image data in the order of ECG, EMG, BT, T, RH, Groy, Label in columns 1-7 in the file at a time, and name the table as Sheet4
Put the XunyuImages folder under the project and run the ANN_train file to train the ANN and get the fused image.
You need to manually separate the images into training, validation and test sets in the dataset folder before you can proceed to the next step of training.
You need to run the txt_productor file, which will automatically generate the labels for yolov5s (only for the provided non-image dataset).
Put the data and images into the dataset folder in the order of training, validation, and testing, and put the original images into the dataset1 folder in the order of training, validation, and testing (the supplied dataset has already been put in place)
yolov5s training method.
You need to point all the paths in the data\data.yaml file to your training set, default epoch==300;.
If you train on the original image files, you need to name the weights obtained from the training as yolo_model.pt and put them under the project.
If you train on the fused image files, you need to put the weights obtained from the training under the project named multi_model.pt for use in detection.
If you want to verify the effect of the feedback module, you need to prepare two folders, yolo and multi, and then run the detect_yolo and detect_multi code files.
After that you put the labels of the images you want to detect into the labels folder.
After that, you can run the feedback_train file to get the result.
Detection process:
First you need to make sure that the yolo_model.pt file and the multi_model.pt file are in the right place.
You put the image you need to detect into the picture folder, and put its corresponding non-image information into the Non_image.xlsx file in the Non_image folder.
Note: the picture folder and the Non_image folder can store only one image, if you want to recognize more than one image, please replace them in turn.
After that, you need to run the main_detect file to get the result.
