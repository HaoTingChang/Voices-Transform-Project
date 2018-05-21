Guide on geting yourself started
===

1.SSH to the machine
---

```
ssh wlchin@140.116.226.80
```


2.Make your foler
---

Enter the commands:
```
mkdir <name>
cd <name>
```

Replace `<name>` with a name you favor
`cd` means change directory

```
pwd
```
`pwd` shows our path


3.Clone the project
---

```
git clone https://github.com/andabi/deep-voice-conversion/
virtualenv -p python2.7 deep-voice-conversion
cd deep-voice-conversion
ls
```

We cloned the project code from a remote repository. Then created a python environment with specified python version 2.7.

This is essential since most of the time python version control and package management could be troublesome.

4.Download the Dataset 
---

For Net1 we need TIMIT to train and test:
```
cd ..
git clone https://github.com/HaoTingChange/Voices-Transform-Project
cp -r Voices-Transform-Project/TIMIT deep-voice-conversion/dataset
cp Voices-Transform-Project/timit.sh deep-voice-conversion/dataset
rm -rf Voices-Transform-Project
```

TIMIT is a paid dataset so we sneak and upload the dataset on our own github repo.
Then copy the dataset into dataset folder in repository and remove the clone reposity since it won't do much help for now.

5.Dataset Partition
---

Dataset is supposed to be partitioned into training set and test set.

```
cd deep-voice-conversion/dataset
ls
bash timit.sh
```

timit.sh should be placed in the same directory as the TIMIT folder.

6.Train your model
---

```
cd ..
pwd
python train1.py dataset/TIMIT
```

It will be certain that there are errors and the model won't be trained. 
That's why we have you to figure it out. 
Normally the progress bar should be moving. 

Check the GPU occupation in another terminal by command `nvidia-smi`
**Memory occupation will be around 150M  when it is not training.**


