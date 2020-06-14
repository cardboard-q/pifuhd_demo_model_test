# pifuhd_demo_model_test

Ran some tests on: https://github.com/facebookresearch/pifuhd
It is from this paper: https://arxiv.org/pdf/2004.00452.pdf
Only used the provided Colab notebook and uploaded stock photos with a person in them. https://colab.research.google.com/drive/11z58bl3meSzo6kFqkahMa35G5jmh2Wgt

## Their citation:
@inproceedings{saito2020pifuhd,
  title={PIFuHD: Multi-Level Pixel-Aligned Implicit Function for High-Resolution 3D Human Digitization},
  author={Saito, Shunsuke and Simon, Tomas and Saragih, Jason and Joo, Hanbyul},
  booktitle={CVPR},
  year={2020}
}

## Results







## Thoughts:
- I think 512 x 512 is a necessary size for the spatial processsing, so your image will be rescaled down to fit it
  - square images are best, which I eventually realized
  - you can see how the rescaling changed the reference images
- It does the image segmentation for you, but having a clean background helps
  - The README also says that for better results you can pre-process with a segmentation mask, so this makes sense
- It seems better models resulted from face-on images, but that could be a training thing. Also, my assumption is that you want to see the face and infer the rest (and not the other way around because of facial expressions), so I'm personally fine if it only works on face-on images.
- I think this is a very interesting paper, and I look forward to seeing more!
