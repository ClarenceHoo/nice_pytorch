Nonlinear Independent Components Estimation
===========================================

An implementation of the NICE model from Dinh et al (2014) in PyTorch.

I was only able to find [the original theano-based repo](https://github.com/laurent-dinh/nice) from the first author,
and I figured it would be good practice to re-implement the architecture in Torch.

Please cite the paper by the original authors and credit them (not me or this repo) if any of the code in this repo
ends up being useful to you in a publication:

["NICE: Non-linear independent components estimation"](http://arxiv.org/abs/1410.8516), Laurent Dinh, David Krueger, Yoshua Bengio. ArXiv 2014.


Requirements
------------
* PyTorch 0.4.1+
* NumPy 1.14.5+
* tqdm 4.15.0+ (though any version should work --- we primarily just use the main tqdm and trange wrappers.)


Benchmarks
----------
We plan to use the same four datasets as in the original paper (MNIST, TFD, SVHN, and CIFAR-10) and attempt to reproduce the results in the paper. At present, MNIST, SVHN, and CIFAR10 are supported; TFD is a bit harder to get access to (due to privacy issues regarding the faces, etc.)

Running `python train.py --dataset={'mnist','cifar10','svhn','tfd'}` will download the relevant dataset and store it in
the appropriate folder the first time you run it; subsequent runs will re-use the downloaded files.

`(TBD: comparisons to original repo & paper results here)`


Status
------
* Training on MNIST currently works. Benchmarks forthcoming (once I find the time to run this for 1500 epochs...)

To Do
-----
+ [ ] [Priority] Implement ZCA
+ [ ] [Priority] Training loop for CIFAR10, SVHN datasets.
+ [ ] [Priority] CUDA support
+ [ ] [Priority] Implement sampling & inpainting from trained model.
+ [ ] [Medium] Toronto Face Dataset? (See remark about privacy issues above)
+ [ ] [Enhancement] Implement affine coupling law
+ [ ] [Enhancement] Allow arbitrary partitions of the input in coupling layers?
