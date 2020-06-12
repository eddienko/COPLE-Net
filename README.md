# COPLE-Net: COVID-19 Pneumonia Lesion segmentation network
This repository provides source code and pretrained model of COPLE-Net for COVID-19 pneumonia lesion segmentation network proposed by G. Wang et al.[1]. If you use this code or the pretrained model, please cite the following paper:

* [1] G. Wang, X. Liu, C. Li, Z. Xu, J. Ruan, H. Zhu, T. Meng, K. Li, N. Huang, S. Zhang. 
[A Noise-robust Framework for Automatic Segmentation of COVID-19 Pneumonia Lesions from CT Images.][tmi2020] IEEE Transactions on Medical Imaging. 2020. DOI: [10.1109/TMI.2020.3000314][tmi2020]

![coplenet_result](./pictures/coplenet_result.png)
A segmentation example. (a), one slice of a CT volume. (b) segmentation by COPLE-Net (green) compared with ground truth (orange). (c) 3D visualization.

![coplenet_structure](./pictures/coplenet_structure.png)
The structure of COPLE-Net. 

# Requirements
* [Pytorch][torch_link] version >=1.0.1.
* [PyMIC][pymic_link], a Pytorch-based toolkit for medical image computing. Install it by `pip install PYMIC`.
* Some basic python packages such as Numpy, Pandas, SimpleITK.

[tmi2020]:https://ieeexplore.ieee.org/document/9109297
[torch_link]:https://pytorch.org
[pymic_link]:https://github.com/HiLab-git/PyMIC

# How to use
1. Download the pretrained model and example CT images from [Google Drive][google_link] or [Baidu Netdisk][baidu_link] (extract code q0ci). Put them into the folder `coplenet_data`.
2. Run `python net_run.py config/config.cfg`. The results will be saved in `coplenet_data/result`.
3. To segment COVID-19 pneumonia lesions from your own images, make sure that the images have been cropped into the lung region, and the intensity has been normalized into [0, 1] using window/level of 1500/-650. Open the configure file `config/config.cfg` and edit `root_dir`, `test_csv` and `output_dir` according to the path of your images. Then return to step 2 to obtain the segmentation results.

[google_link]:https://drive.google.com/drive/folders/1K1jbrxWWhG_L7dh6yMyB4DtklBr-bhxH?usp=sharing
[baidu_link]:https://pan.baidu.com/s/1TSTSkORYNWsX94PxiQUfjw 


