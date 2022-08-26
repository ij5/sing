# Korean Singing Voice Synthesis
# Preprocessing
```bash
python preprocess.py -c config/default_train.yml --use_cpu True
```

You can speed up preprocessing by increasing the number of processes or 'num_proc'.
You can use preprocess.py with GPU but 'num_proc' should be 1.

# Training
```bash
python train.py -c config/default_train.yml --device 0 --batch_size 32
```

If your system doesn't have enough memory, you can change 'data_mode' to 'multi' which loads data with queue.
Also type following command for tensorboard monitoring.
```bash
tensorboard --logdir=checkpoint/default
```

# Inference
```bash
python infer.py -c config/default_train.yml config/default_infer.yml --device 0
```
