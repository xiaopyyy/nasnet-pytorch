## A neat pytorch implementation of NASNet

The performance of the ported models on ImageNet:

| Model Checkpoint    | Million Parameters | Val Top-1 | Val Top-5 |
| ------------------- | ------------------ | --------- | --------- |
| NASNet-A_Mobile_224 | 5.3                | 70.2      | 89.4      |
| NASNet-A_large_331  | 88.9               | 82.3      | 96.0      |

The differences may come from 1) the slightly different pooling padding methods between tensorflow and pytorch 2) data preprocessing.

The porting process is done by `tensorflow_dump.py` and `pytorch_load.py`, modified from [Cadene's project](https://github.com/Cadene/tensorflow-model-zoo.torch).

You can evaluate the models by running `imagenet_eval.py`, e.g. evaluate the NASNet-A_Mobile_224 ported model by

```shell
python imagenet_eval.py --nas-type mobile --resume /path/to/modelfile --gpus 0 --data /path/to/imagenet_root_dir
```

The ported model file are provided: [NASNet-A_Mobile_224, NASNet-A_large_331](https://www.dropbox.com/sh/ng93kp7f7ypat73/AABUQhImioJ2saQ3N-qWzrJga?dl=0).