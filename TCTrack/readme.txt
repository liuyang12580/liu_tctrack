source activate tctrack

export PYTHONPATH=/home/dc/ly/TCTrack:$PYTHONPATH

CUDA_VISIBLE_DEVICES=0

## 2. Test
Download pretrained model and put it into `tools/snapshot` directory.
Download testing datasets and put them into `test_dataset` directory. 

```bash 
cd TCTrack
python  ./tools/test.py   --dataset UAV123_10fps   --tracker_name TCTrack  --snapshot snapshot/general_model.pth   # pre-train model path
```
The testing result will be saved in the `results/dataset_name/tracker_name` directory.


## 3. Train
### Prepare training datasets
Download the datasets：
* [VID](http://image-net.org/challenges/LSVRC/2017/)
* [Lasot](https://paperswithcode.com/dataset/lasot)
* [GOT-10K](http://got-10k.aitestunion.com/downloads)
**Note:** `train_dataset/dataset_name/readme.md` has listed detailed operations about how to generate training datasets.


### Train a model
To train the TCTrack model, run `train.py` with the desired configs:

```bash
cd tools
python train.py
```



## 4. Evaluation
put those results into  `results` directory.
```
python eval.py  --tracker_path ./results   --dataset UAV10fps   --tracker_prefix  'general_model'   # tracker_name
```






test	
python  /home/dc/ly/TCTrack/tools/test.py   --dataset UAV123   --tracker_name TCTrack  --snapshot ./tools/snapshot/checkpoint00_e1.pth 


