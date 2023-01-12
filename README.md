# pixel-distribution-learning
Motion Segmentation is the task of identifying the independently moving objects (pixels) in the video and separating them from the background motion.

Thanks for helping from Chenqiu, and Dr.Basu.

Our work include use the state of the art : Pixel distribution model (random feature selection) to preprocess the extracted optical flow images. The optical flow is extracted use the state of the art model, RAFT provided by Teed and Deng. Then we will serve the extracted pixel distributions as inputs to our motion segmentation net. Finally, we will generate our own segementation binary masks against groud truths.

Tested dataset:
http://www.cvlibs.net/datasets/kitti/

![alt text](https://github.com/youwei1-sudo/pixel-distribution-learning/blob/main/documents/git_docs/workFlow.jpg)


## Required Data
To train/test the model, you need to download the dataset from:
* [KITTI MoSeg](http://webdocs.cs.ualberta.ca/~vis/kittimoseg/)

We also test our model on DAVIS 2016:
* [DAVIS](https://davischallenge.org/davis2016/code.html)

## Training
To train the model,
```Shell
python3 train.py --data_root=directory to the KITTI MoSeg --checkpoint=./ckpt
```

## Testing
To test the model from a saved checkpoint:
Example
```Shell
python3 test.py --data_root=directory  --model_path=./checkpoint_0423/ckpt_22.pth  --test_image_dir=the directory where you want to save tested image result --gt_dir=the directory to save the ground truth
```
 
 
 
the pre-trained model is saved in /checkpoint_0423/ckpt_22.pth 

