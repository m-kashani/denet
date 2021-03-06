
## Model Downloads (v1)
* DeNet-34 skip: [Google Drive](https://drive.google.com/uc?export=download&id=0B2Y3zi7OSEbrMmNYZGhyS29NQms)
* DeNet-34 wide: [Google Drive](https://drive.google.com/uc?export=download&id=0B2Y3zi7OSEbrUFlwdW05eFdwNXc)
* DeNet-101 skip: [Google Drive](https://drive.google.com/uc?export=download&id=0B2Y3zi7OSEbrMjlQUlAzZFpqRUU)
* DeNet-101 wide: [Google Drive](https://drive.google.com/uc?export=download&id=0B2Y3zi7OSEbrTDhodlZ2NExmYW8)

DeNet: Scalable Real-time Object Detection with Directed Sparse Sampling
By Lachlan Tychsen-Smith (research engineer), Lars Petersson (supervisor)
https://arxiv.org/abs/1703.10295

## Model Downloads (v2)
* DeNet-34 wide c1 (v2): [Google Drive](https://drive.google.com/uc?export=download&id=1L5TA-ZdUd3tOZRDOxTwXKH_SknxyCby6)
* DeNet-101 wide c1 (v2): [Google Drive](https://drive.google.com/uc?export=download&id=1SYNRoI4JsV-dUF-BctwKiULMO4reGtZf)

Models include Joint Fitness NMS, Bounded IoU Loss and Corner Clustering

Improving Object Localization with Fitness NMS and Bounded IoU Loss
By Lachlan Tychsen-Smith (research engineer), Lars Petersson (supervisor)
https://arxiv.org/abs/1711.00164


## Prediction
Use the following command to evaluation models on gpu0:

    GPU=0 model-predict --batch-size 8 --thread-num 4 --predict-mode detect,mscoco --input MSCOCO_DIR --model MODEL_FNAME --extension mscoco,2015-test-dev,images_per_subset=128,crop=512,scale_mode=large
    
where: 
* MSCOCO_DIR is the path to the base mscoco dataset
* MODEL_FNAME is the path to the downloaded model file (see above)  

This command will generate a "results.json" file which can be zipped and uploaded to Codalabs MSCOCO server for evaluation.

To output images with annotated bounding boxes set "--predict-mode detect,mscoco,image"
