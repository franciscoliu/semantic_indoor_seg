# semantic_indoor_seg

First run 
```
!wget http://download.microsoft.com/download/2/8/5/28564B23-0828-408F-8631-23B1EFF1DAC8/redkitchen.zip
```
This is the dataset that we tried to establish semantic segmentation label (from 7 senses), which may take awhile. Then run

```
!unzip redkitchen.zip -d redkitchen
```
Just for testing, we just unzip seq-01, seq-02 for reference: 
```
unzip re dkitchen/redkitchen/seq-01.zip -d redkitchen/redkitchen/seq-01
unzip redkitchen/redkitchen/seq-02.zip -d redkitchen/redkitchen/seq-02
```
Then run (Note that you need python=3.7):
```
pip install -r requirements.txt
```

Then you need to downgrade some of the packages by running:
```
pip install protobuf==3.20.*
```

Furthermore, you need to download the pretrained model for later generation [here](https://drive.google.com/file/d/1o7QrlNxH6BX6uYatlR06-A_cutWD9sNg/view).

Lastly, run:

```
python inference.py --img_path redkitchen/redkitchen/seq-01/seq-01/frame-000000.color.png --restore_from=pretrained_models/ResNet101/
```

However, I ran into some problems here and I am trying to figure it out. This work is beyond the work of improving depth map estimation, but it is necessary for 3D reconstruction. Hence, we will leave this for future work.
