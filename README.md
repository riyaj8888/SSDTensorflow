# SSDTensorflow
SSD object detection TF
### crate dataset in PascalVOC format.
*         VOC2007/Annotations--->has per image xml file annotation.
*        /ImageSets/Main ---> trainval.txt,test.txt--> which images(files name) are used for training and testing.
*        /JPEGImages --> All images inside this directory.
* checkpoints should be places under checkpoints/ssd_300_vgg.ckpt folder 
## changes to be done 
### datasets/pascalvoc_2007.py  --> Train statistics --> indicates no of bboxes/per class in training <br />.
### Test statistics  --> indicates no of bboxes/per class in testing <br />.
### SPLITS_TO_SIZES --> Total number of bboxes <br />.
### datasets/pascalvoc_common.py --> VOC_LABELS --> with your dataset labels <br />.

### train_ssd_network.py
    *DATASET_DIR='path to tfrecords'*
    *TRAIN_DIR='path to logs dir/'
    *CHECKPOINT_PATH='checkpoints/ssd_300_vgg.ckpt'
    *!python train_ssd_network.py --dataset_name=pascalvoc_2007 --dataset_split_name=train --model_name=ssd_300_vgg --save_summaries_secs=60 --save_interval_secs=600 --weight_decay=0.0005 --optimizer=adam --learning_rate=0.001 --batch_size=2 --gpu_memory_fraction=0.9 --checkpoint_exclude_scopes =ssd_300_vgg/conv6,ssd_300_vgg/conv7,ssd_300_vgg/block8,ssd_300_vgg/block9,ssd_300_vgg/block10,ssd_300_vgg/block11,ssd_300_vgg/block4_box,ssd_300_vgg/block7_box,ssd_300_vgg/block8_box,ssd_300_vgg/block9_box,ssd_300_vgg/block10_box,ssd_300_vgg/block11_box
