# Gather-Excite: Exploiting Feature Context in Convolutional Neural Networks <sub>([arXiv](https://arxiv.org/pdf/1810.12348.pdf))</sub>
By Jie Hu<sup>[1]</sup>, Li Shen<sup>[2]</sup>, Samuel Albanie<sup>[2]</sup>, Gang Sun<sup>[1]</sup>, Andrea Vedaldi<sup>[2]</sup>.

[Momenta](https://momenta.ai/)<sup>[1]</sup> and [University of Oxford](http://www.robots.ox.ac.uk/~vgg/)<sup>[2]</sup>.

## Approach
<div align="center">
  <img src="https://github.com/hujie-frank/GENet/blob/master/figures/GE-module.jpg">
</div>
<p align="center">
  Figure 1: The Diagram of a Gather-Excite module.
</p>

<div align="center">
  <img src="https://github.com/hujie-frank/GENet/blob/master/figures/GEPF8.jpg"  width="420" height="480">
  <img src="https://github.com/hujie-frank/GENet/blob/master/figures/GEPF.jpg" width="400" height="480">
  <img src="https://github.com/hujie-frank/GENet/blob/master/figures/GEP8.jpg" width="460" height="480">
  <img src="https://github.com/hujie-frank/GENet/blob/master/figures/GEP.jpg"  width="400" height="480">
</div>
<p align="center">
  Figure 2: The Schema of Gather-Excite modules. Top-left: $GE-\theta^-\,(E8)$. Top-right: $GE-\theta^-$. Bottom-left: $GE-\theta\,(E8)$. Bottom-right: $GE-\theta$.
</p>

## Implementation
In this repository, all the models are implemented by [Caffe](https://github.com/BVLC/caffe).
 
We use the data augmentation strategies with our previous work [SENet](https://github.com/hujie-frank/SENet). 

There are three new layers introduced for efficient training and inference, these are *Axpy*, *DepthwiseConvolution* and *CuDNNBatchNorm* layers.  
+ The [*Axpy*](https://github.com/hujie-frank/SENet/blob/master/src/caffe/layers/) layer is already implemented in [SENet](https://github.com/hujie-frank/SENet).
+ As for [*DepthwiseConvolution*](https://github.com/yonghenglh6/DepthwiseConvolution/tree/master/caffe/src/caffe/layers) layer, it is publicly avaliable at the [repo](https://github.com/yonghenglh6/DepthwiseConvolution/), or you can directly replace it with the standard *Convolution* layer if you don't care about the operational efficiency.
+ The *CuDNNBatchNorm* layer will be released in these days.

## Trained Models
Coming soon!

## Citation

If you use Squeeze-and-Excitation Networks in your research, please cite the paper:
    
    @inproceedings{hu2018genet,
      title={Gather-Excite: Exploiting Feature Context in Convolutional Neural Networks},
      author={Jie Hu and Li Shen and Samuel Albanie and Gang Sun and Andrea Vedaldi},
      journal={NIPS},
      year={2018}
    }
