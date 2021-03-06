# CIFAR10 Deep Learning Speed Benchmark

For informally benchmarking CUDA hardware.

IMPORTANT NOTES ABOUT ACCURACY:

* This program outputs the accuracy only as a sanity check.
* Accuracy should not be compared across batch sizes, since the batch size influences the total number of iterations, which in turn influences the accuracy.

## Usage

This script looks for the CIFAR data inside `$CIFAR`; if the environment variable does not exist, it downloads the dataset into `./data`. You can manually [download the data here](https://www.cs.toronto.edu/~kriz/cifar-10-python.tar.gz) and put it inside the directory.

```
usage: benchmark.py [-h] [--gpus GPUS] [--progressive]
                    [--measurements MEASUREMENTS] [--size SIZE]
                    [--epochs EPOCHS] [--batches BATCHES]
                    [--batch-size BATCH_SIZE]
                    {densenet,wideresnet}

Image classification speed benchmark

positional arguments:
  {densenet,wideresnet}

optional arguments:
  -h, --help                     show this help message and exit
  --gpus GPUS                    Number of gpus to use. Default: all
  --progressive                  Try 1 gpus, 2 gpus, 3 gpus, etc.
  --measurements MEASUREMENTS    Num measurements for avg and std
  --size SIZE                    image size multiplier
  --epochs EPOCHS
  --batches BATCHES              stop early for testing
  --batch-size BATCH_SIZE        Batch size PER GPU
```
