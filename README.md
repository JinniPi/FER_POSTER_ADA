# FER_POSTER_ADA (add alignment function to FER with backbone POSTER)
This project for the Advanced Machine Learning class at SeoulTech [1st semester - 2023]

### Preparation
- create conda environment (we provide requirements.txt)

- Data Preparation

  Download [RAF-DB](http://www.whdeng.cn/RAF/model1.html#dataset) dataset, and make sure it have a structure like following:
 
	```
	- data/raf-basic/
		 EmoLabel/
		     list_patition_label.txt
		 Image/aligned/
		     train_00001_aligned.jpg
		     test_0001_aligned.jpg
		     ...
	```

- Pretrained model weights
 - Put entire `pretrain` folder under `models` folder.

	```
	- models/pretrain/
		 ir50.pth
		 mobilefacenet_model_best.pth.tar
		     ...
	```

### Testing

- put best model under `checkpoint ` folder. You can evaluate our model on RAD-DB dataset by running: 

```
python test.py --checkpoint checkpoint/rafdb_best.pth -p
```

### Training
Train on RAF-DB dataset:
```
python train.py --gpu 0,1 --batch_size 200
```
You may adjust batch_size based on your # of GPUs. Usually bigger batch size can get higher performance. We provide the log in  `log` folder. You may run several times to get the best results. 






## Acknowledgments

Our implementation and experiments based on the official of ADA code and POSTER code. 


