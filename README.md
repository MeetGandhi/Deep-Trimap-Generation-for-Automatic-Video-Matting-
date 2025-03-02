## Visualizing test results

For viewing the test results, please clone this repository, unzip the zipped folders and host **index.html** file present in each of the subfolder titled *Results/test*. 

# Deep-Trimap-Generation-for-Automatic-Video-Matting-using-GAN

## Abstract

In this proposal, we attempt to solve the problem of video matting using the deep learning framework. The major challenge in video matting is the extraction of mattes along with the foreground and the background from a video accurately while being computationally fast and requiring minimal human intervention. Deep learning framework provides us with the necessary tools to achieve faster algorithms for dealing with videos. We propose to use the encoder-decoder network along with long short term memory (LSTM) network in order to develop the framework for solving the video matting problem. We assume that the trimap or scribble information is available only in certain key frames of the video in the initial phase of our work. The ultimate goal of our work is to design a deep neural network which is intelligent, user-friendly, computationally efficient and takes as input a normal video and outputs associated high quality video matte without any input of trimap/scribbles.   

## Proposal

Video matting is the tool to estimate the matte, the foreground, and the background from a given video with distinct foreground and background regions [Wang and Cohen, 2008]. The video matting extends image matting to video generally by propagating the scribbles/trimap on successive frames [Sonane et al., 2016]. Various approaches have been proposed to address the video matting problem in the past such as [Chuang et al., 2002]. The main goal of such approaches is to achieve video matting by pulling an accurate matte with minimal computational complexity while keeping the user intervention in terms of trimap/scribbles as minimal as possible. Recently, a deep network has been developed and shown to give the best results for the single image matting problem [Xu et al., 2017]. Another recent work achieves good results for the problem of single image matting [Aksoy et al., 2017]. We would like to apply the principles of deep learning in order to design a deep video matting network which could potentially outperform the existing methods. Prior work in the field of video matting involved very high computational cost as they used to perform single image matting individually for all the frames and hence the overall system would be so slow that it loses the aspect of being user friendly.

There is no large scale benchmark dataset publicly available at present which contains the ground truth video mattes [Erofeev et al., 2015]. The first step is to generate such a dataset which consists of video frames with trimap/scribbles and the corresponding ground truth mattes. The methodology proposed to solve this problem involves splitting the given video into multiple shots [Costaces et al., 2006]. We shall identify keyframes from each shot which needs to be subjected to single image matting. An encoder-decoder network will be employed in order to perform single image matting for the selected frames [Xu et al., 2017]. We shall train a long short term memory (LSTM) or gated recurrent neural network which learns the temporal variation of intensity values and the corresponding mattes across the successive frames between any two keyframes [Chung et al., 2015]. The prediction for the mattes corresponding to frames other than the keyframes will be achieved by the LSTM or the gated recurrent neural network. We shall initially assume that the trimap/scribbles are sparsely available on only selected keyframes of the test video. We shall then modify the network after initial experiments in order to perform video matting on even videos without any trimap/scribbles on any of the frames.

A unique aspect of the proposed network is that we shall solve both the single image matting and the video matting problems in an unified framework. A detailed evaluation of the results will be performed on the benchmark dataset created and extensive comparisons using measures such as variants of sum of squared difference will be done. The hyper parameters of the developed network will be varied in order to obtain the optimal results. The pre-trained network will be released to the community on successful completion of the work in order to promote reproducible research.

The practical benefits of our work would comprise of everything which can be done to alpha video mattes [Wang and Cohen, 2008] like compositing the alpha video matte and the associated video onto a new background in addition to resizing the foreground while keeping the background same for a video. Once high computational efficiency is achieved for video matting through our work, the post processing done at present during visual effects through Chroma key compositing would change as with our work we can change the background of any highly dynamic object in a video efficiently. This would free the usage of green screen at present times for Chroma key compositing. Also by merging two alpha video mattes one can create a composite video comprising the features of the merged videos.

## Approach

Used https://phillipi.github.io/pix2pix/ and https://junyanz.github.io/CycleGAN/

## References

* Aksoy, Y., Aydın, T. O., & Pollefeys, M. (2017). Designing effective inter-pixel information flow for natural image matting. CVPR.
* Chuang, Y. Y., Agarwala, A., Curless, B., Salesin, D. H., & Szeliski, R. (2002). Video matting of complex scenes. ACM Transactions on Graphics (ToG), 21(3), 243-248.
* Chung, J., Gulcehre, C., Cho, K., & Bengio, Y. (2015). Gated feedback recurrent neural networks. In ICML (pp. 2067-2075).
* Cotsaces, C., Nikolaidis, N., & Pitas, I. (2006). Video shot detection and condensed representation. a review. IEEE signal processing magazine, 23(2), 28-37.
* Erofeev, M., Gitman, Y., Vatolin, D., Fedorov, A., & Wang, J. (2015). Perceptually Motivated Benchmark for Video Matting. In BMVC.
* Sonane, B., Ramakrishnan, S., & Raman, S. (2016). Automatic video matting through scribble propagation. In Proceedings of the Tenth Indian Conference on Computer Vision, Graphics and Image Processing ICVGIP (p. 87). ACM.
* Xu, N., Price, B., Cohen, S., & Huang, T. (2017). Deep Image Matting. CVPR.
* Wang, J., & Cohen, M. F. (2008). Image and video matting: a survey. Foundations and Trends® in Computer Graphics and Vision, 3(2), 97-175.


