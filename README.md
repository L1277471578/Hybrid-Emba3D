# Hybrid-Emba3D: Geometry-Aware and Cross-Path Feature Hybrid Enhanced State Space Model for Point Cloud Classification

[[paper]](https://arxiv.org/abs/2505.11099) 

We will release the code and weights soon!

## To do
- ✅ Publish training and testing logs
- ✅ Release [pretraining](https://github.com/L1277471578/Hybrid-Emba3D/releases/download/v1.0/pretrain_pointmae.pth) and finetune weights
- ⏳ release the model and evaluation code...

## Experimental Results on ModelNet40 and ScanObjectNN
This table compares the performance of different 3D point cloud architectures on ModelNet40 and ScanObjectNN datasets. Our Hybrid-Emba3D achieves state-of-the-art results with:
- 🏆95.99% accuracy on ModelNet40
- 94.34% on hardest PB_T50_RS variant
- Maintains low computational cost (3.95G FLOPs)

﻿
*For detailed experimental settings and citations, please refer to the original paper.*


| Methods               | Architecture Type       | ModelNet40<br>(1k P) |  	 | ScanObjectNN | 	  | Params<br>(M) | FLOPs<br>(G) |
|-----------------------|-------------------------|----------------------|---------|----------|-----------|---------------|--------------|
|                       |                         |                      | OBJ_BG  | OBJ_ONLY | PB_T50_RS |               |              |
| 🔴 **Supervised Learning Only**                               |                                                                 |
| PointNet              | Point-wise              | 89.2                 | 73.3    | 79.2     | 68.0      | 3.5          | 0.5          |
| PointNet++            | Point-wise              | 90.7                 | 82.3    | 84.3     | 77.9      | 1.5          | 1.7          |
| DGCNN                 | Point-wise              | 92.9                 | 82.8    | 86.2     | 78.1      | 1.8          | 2.4          |
| PointMLP              | Point-wise              | 94.5                 | -       | -        | 85.4      | 12.6         | 31.4         |
| MVTN                  | Multi-view              | 93.8                 | 92.6    | 92.3     | 82.8      | 11.2         | 43.7         |
| Transformer           | Transformer       	    | 94.1                 | 79.9    | 80.6     | 77.2      | 22.1         | 4.8          |
| PointConT             | Transformer       	    | 93.5                 | -       | -        | 90.3      | -            | -            |
| Pointmamba            | Mamba           	      | -                    | 88.3    | 87.8     | 82.5      | 12.3         | 3.6          |
| Mamba3D               | Mamba           	      | 93.4                 | 92.9    | 92.1     | 91.8      | 16.9         | 3.9          |
| **Hybrid-Emba3D**     | Mamba           	    | 94.0                 | 93.6    | 92.3     | 91.1      | 16.96        | 3.95         |
| 🟢**With Pre-training**                                                                        |
| Point-BERT*           | Transformer     	  | 93.4                 | 88.1    | 88.3     | 83.7      | 23.8         | 4.8          |
| Point-MAE*            | Transformer     	  | 94.4                 | 91.2    | 90.0     | 84.9      | 23.8         | 4.8          |
| Point-FMAE*           | Transformer     	  | 95.2                 | 95.2    | 93.3     | 90.2      | 27.4         | 3.6          |
| Pointdif              | Diffusion           | -                    |93.29    |91.91     |  87.61    |  -           |  -           |
| Pointmamba            | Mamba           	  | 93.6                 | 94.3    | 92.6     | 89.3      | 12.3         | 3.6          |
| Mamba3D*              | Mamba           	  | 95.1                 | 95.2    | 92.6     | 93.3      | 16.9         | 3.9          |
| **Hybrid-Emba3D**    | Mamba            	  | 95.6                 | 93.8    | 93.1     | 93.1     | 16.96        | 3.95         |
| **Hybrid-Emba3D***    | Mamba            	  | **95.99** 🏆         | 95.2    | 93.8     | 94.3     | 16.96        | 3.95         |

*: Voting strategy applied
