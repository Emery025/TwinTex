# TwinTex: Geometry-aware Texture Generation for Abstracted 3D Architectural Models

Implementation for our paper "TwinTex: Geometry-aware Texture Generation for Abstracted 3D Architectural Models" (ACM SIGGRAPH Asia 2023).

![tensor](https://github.com/Ligo04/TwinTex/blob/main/images/teaser.png?raw=true)

## SOP_TwinTex 

### Prerequisites

- Environments: Windows10/11, Houdini>=19.5.x

### Installation

Copy our dlls in the following folder `C:\Users\xxx\Documents\houdini19.5\dso` :

```
----dso
 ├──SOP_TwinTex.dll
 ├──libgmp-10.dll
 ├──opencv_world460.dll
```

Then you can search `TwinTex` in Houdini and add our tool as a node.

![sop_twintex](https://github.com/Ligo04/TwinTex/blob/main/images/SOP_TwinTex.png?raw=true)

### Usage 

1. `Config File`: Specify the configuration file `default_config.yaml`.

2. `Scene Path`: Specify the path to the data directory, which is structed as follows:

   ```
   ----
    ├──Mesh
       ├──original_mesh.ply
       ├──simplify_mesh.ply
       ├──simplify_mesh_sub.ply
    ├──Scene
       ├──XXX.JPG
       ├──XXX.CAM
    ├──Results(auto）
   ```

3.  `Load Data`: Load scene data.

4. (Optional) `Load Results`: Load the results in `Result\final_result`.

5. (Optional) `Show Views`: Show the position and direction of the views(only work in single plane mode). The single plane mode and plane id are specified in the configuration file.

6. (Optional) `Show Image`: Show the output images of `ViewSelection` or `ImageStitching` (only work in single plane mode).

7. `ViewSelection`:  Modify parameters of `ViewSelection` and apply.

8. `ImageStitching`: Modify parameters of `ImageStitching` and apply.

9. `Inpainting`

   - `MMRP Path`: Specify the path of the MMRP project. MMRP details in [here](https://github.com/Ligo04/TwinTex/tree/main/MMRP).
   - `Inpainting`: Inpaint the planes via MMRP.

10. `start`: Apply `ViewSelection` and `ImageStitching`

If Houdini crashes, please first check that you have followed the environment, configuration and steps above.

## License

Copyright (c) 2023. VCC  All rights reserved.

## Citation

If you find TwinTex useful for your research, please cite the following paper.

```
@article{TwinTex23,
title={TwinTex: Geometry-aware Texture Generation for Abstracted 3D Architectural Models},
author={Weidan Xiong and Hongqian Zhang and Botao Peng and Ziyu Hu and Yongli Wu and Jianwei Guo and Hui Huang},
journal={ACM Transactions on Graphics (Proceedings of SIGGRAPH ASIA)},
volume={42},
number={6},
pages={},
year={2023},
}
```
