# Learning from Noisy Anchors for <br/> One-stage Object Detection

This repo contains the implementation for "[Learning from Noisy Anchors for One-stage Object Detection](https://arxiv.org/abs/1912.05086)" based on [Detectron2](https://github.com/facebookresearch/detectron2).

## Installation
See [INSTALL.md](INSTALL.md). The following environment has been tested:
```
Python 3.7
CUDA 10.1
PyTorch 1.4.0
torchvision 0.5.0
```

## Training and Testing
The config files are located at `./configs/COCO-Detection-NoisyAnchor`. See [GETTING_STARTED.md](GETTING_STARTED.md) and follow the standard procedure to train/test RetinaNet with our method applied.

Before training, please download ImageNet pre-trained models as instructed in [GETTING_STARTED.md](GETTING_STARTED.md) and put them under `./outputs`.

## Results on COCO 2017 Val
#### RetinaNet:
<!--
./gen_html_table.py --config 'COCO-Detection/retina*50*' 'COCO-Detection/retina*101*' --name R50 R50 R101 --fields lr_sched train_speed inference_speed mem box_AP
-->


<table><tbody>
<!-- START TABLE -->
<!-- TABLE HEADER -->
<th valign="bottom">Name</th>
<th valign="bottom">lr<br/>sched</th>
<th valign="bottom">box<br/>AP</th>
<th valign="bottom">download</th>
<!-- TABLE BODY -->
<!-- ROW: retinanet_R_50_FPN_1x baseline -->
 <tr><td align="left"><a href="configs/COCO-Detection/retinanet_R_50_FPN_1x.yaml">R50-Baseline</a></td>
<td align="center">1x</td>
<td align="center">36.5</td>
<td align="center"><a href="https://dl.fbaipublicfiles.com/detectron2/COCO-Detection/retinanet_R_50_FPN_1x/137593951/model_final_b796dc.pkl">model</a></td>
</tr>
<!-- ROW: retinanet_R_50_FPN_1x ours-->
 <tr><td align="left"><a href="configs/COCO-Detection-NoisyAnchor/retinanet_R_50_FPN_1x_noisyanchor.yaml">R50-NoisyAnchor</a></td>
<td align="center">1x</td>
<td align="center">38.6</td>
<td align="center"><a href="https://drive.google.com/file/d/1bLZVxmBbsbuH2Po9TQHgMn-gr24swQJn/view?usp=sharing">model</a></td>
</tr>
<!-- ROW: retinanet_R_50_FPN_3x -->
 <tr><td align="left"><a href="configs/COCO-Detection/retinanet_R_50_FPN_3x.yaml">R50-Baseline</a></td>
<td align="center">3x</td>
<td align="center">37.9</td>
<td align="center"><a href="https://dl.fbaipublicfiles.com/detectron2/COCO-Detection/retinanet_R_50_FPN_3x/137849486/model_final_4cafe0.pkl">model</a></td>
</tr>
<!-- ROW: retinanet_R_50_FPN_3x -->
 <tr><td align="left"><a href="configs/COCO-Detection-NoisyAnchor/retinanet_R_50_FPN_3x_noisyanchor.yaml">R50-NoisyAnchor</a></td>
<td align="center">3x</td>
<td align="center">40.2</td>
<td align="center"><a href="https://drive.google.com/file/d/1xpKTOGA99J4HefH5rFdwiA9vqkFouLbx/view?usp=sharing">model</a></td>
</tr>
<!-- ROW: retinanet_R_101_FPN_3x -->
 <tr><td align="left"><a href="configs/COCO-Detection/retinanet_R_101_FPN_3x.yaml">R101-Baseline</a></td>
<td align="center">3x</td>
<td align="center">39.9</td>
<td align="center"><a href="https://dl.fbaipublicfiles.com/detectron2/COCO-Detection/retinanet_R_101_FPN_3x/138363263/model_final_59f53c.pkl">model</a></td>
</tr>
<!-- ROW: retinanet_R_101_FPN_3x -->
 <tr><td align="left"><a href="configs/COCO-Detection-NoisyAnchor/retinanet_R_101_FPN_3x_noisyanchor.yaml">R101-NoisyAnchor</a></td>
<td align="center">3x</td>
<td align="center">42.0</td>
<td align="center"><a href="https://drive.google.com/file/d/1dslIQOWWIW8c6Db0qMXneUhIo_Y0ZpdG/view?usp=sharing">model</a></td>
</tr>
</tbody></table>


## Citation
If you find this project useful for your research, please use the following BibTeX entry:

```BibTeX
@inproceedings{li2020learning,
  title={Learning from noisy anchors for one-stage object detection},
  author={Li, Hengduo and Wu, Zuxuan and Zhu, Chen and Xiong, Caiming and Socher, Richard and Davis, Larry S},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  pages={10588--10597},
  year={2020}
}
```
