# pifuhd_demo_model_test

- Ran some tests on: https://github.com/facebookresearch/pifuhd
- It is from this paper: https://arxiv.org/pdf/2004.00452.pdf
- Only used the provided Colab notebook and uploaded stock photos with a person in them. https://colab.research.google.com/drive/11z58bl3meSzo6kFqkahMa35G5jmh2Wgt

## Their citation:
@inproceedings{saito2020pifuhd,
  title={PIFuHD: Multi-Level Pixel-Aligned Implicit Function for High-Resolution 3D Human Digitization},
  author={Saito, Shunsuke and Simon, Tomas and Saragih, Jason and Joo, Hanbyul},
  booktitle={CVPR},
  year={2020}
}

## Results

### Caveats
- Did this using stock photos (https://www.pexels.com/)
- Didn't do any pre-processing other than picking photos that I thought could be segmented decently
- It's running inside a colab notebook, so it has a resolution limit
- Image quality was lost on the conversion from mp4 to gif.

![image](/walking.gif)
![image](/water.gif)
![image](/half.gif)
![image](/side.gif)
![image](/back.gif)
![image](/yoga.gif)

## Thoughts:
- I think 512 x 512 is a necessary size for the spatial processsing, so your image will be rescaled to fit
  - since it rescales, square images are best, which I eventually realized
  - you can see how the rescaling can warp the reference images
- It does the image segmentation for you, so having a clean background helps
  - The README also says that for better results you can pre-process with a segmentation mask, so this makes sense
- It seems better models resulted from face-on images. Could be the training, or it could be the input. However, my assumption is that you want to see the face and infer the rest (and not the other way around because of facial expressions), so I'm personally fine if it only works on face-on images.
- The yoga picture catches the leg that is held up, but it also seems to be inferring that there is another leg that is obfuscated. It doesn't help that the colors are pretty uniform in that region.
