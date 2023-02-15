# Image Matching Challenge 2022

This repository presents our solution to the [Image Matching Challenge 2022](https://www.kaggle.com/competitions/image-matching-challenge-2022/), a competition hosted by Google Research as part of the CVPR'22 Workshop: [Image Matching: Local Features & Beyond](https://image-matching-workshop.github.io/). Our solution finished at 34th place out of 642 participating teams, earning us a Kaggle Competition Silver Medal :2nd_place_medal:.

> Authors: [Armando Fortes](https://atfortes.github.io/) & [David Pissarra](https://github.com/davidpissarra)

We hope our solution can serve as a resource for the community and inspire future work. If you find it useful, please consider giving it a star!

## Overview

Our solution leverages the [SuperGlue](https://github.com/magicleap/SuperGluePretrainedNetwork) (detector-based) and [LoFTR](https://github.com/zju3dv/LoFTR) (detector-free), two highly regarded methods for the image matching task. The chosen feature detector to complement the SuperGlue pre-trained network was [SuperPoint](https://github.com/magicleap/SuperPointPretrainedNetwork). In addition, we add [QuadTree Attention](https://github.com/Tangshitao/QuadTreeAttention) to LoFTR, improving the performance of the detector-free model.

For each pair of input images, we feed them into the two different local feature matching heads (i.e. the detector-based and detector-free approaches described above). The resulting matches from both heads are then concatenated and fed into the MAGSAC consensus algorithm for inlier/outlier detection and fundamental matrix calculation.

More details on the implementation and experiments can be found in our [report](https://github.com/atfortes/ImageMatchingChallenge2022/blob/main/report.pdf).

## Examples

Some inference examples of our model, using photos from famous monuments around the world. The colors of the resulting matches range from **green** for high-confidence matches to **red** for low-confidence matches.

|||
|:------------------:|:------------------:|
|||
|  **Colosseum**  |  **Taj Mahal**  |
|  ![](/assets/rome.png)  |  ![](/assets/taj_mahal.png)  |
|||
|||
|  **Basilica of the Sagrada Familia**  |  **Trevi Fountain**  |
|  ![](/assets/sagrada.png)  | ![](/assets/trevi.png)  |
|||
|||
