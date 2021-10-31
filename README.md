# SSDTensorflow
SSD object detection TF
### crate dataset in PascalVOC format.
*         VOC2007/Annotations--->has per image xml file annotation.
*        /ImageSets/Main ---> trainval.txt,test.txt--> which images(files name) are used for training and testing.
*        /JPEGImages --> All images inside this directory.
* checkpoints should be places under checkpoints/ssd_300_vgg.ckpt folder 
## changes to be done 
**datasets/pascalvoc_2007.py  --> Train statistics --> indicates no of bboxes/per class in training <br />.
**--> Test statistics  --> indicates no of bboxes/per class in testing <br />.
**--> SPLITS_TO_SIZES --> Total number of bboxes <br />.
**datasets/pascalvoc_common.py --> VOC_LABELS --> with your dataset labels <br />.

** train_ssd_network.py
    *DATASET_DIR='path to tfrecords'
    *TRAIN_DIR='path to logs dir/'
    *CHECKPOINT_PATH='checkpoints/ssd_300_vgg.ckpt'
