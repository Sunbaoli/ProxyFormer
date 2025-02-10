# ProxyFormer
This repo implements the training and testing of referring video object segmentation  for "Referring Video Object Segmentation with Cross-Modality Proxy Queries" by Baoli Sun, Zhihui Wang and et al. at DLUT.



## Abstract
Referring video object segmentation (RVOS) is an emerging cross-modality task that aims to generate pixel-level maps of the target objects referred by given textual expressions. The main concept involves learning an accurate alignment visual elements and language expressions within a semantic space. Recent approaches address cross-modality alignment through conditional queries, tracking  the target object using a query-response based mechanism built upon transformer structure. However, they exhibit two limitations: (1) these conditional queries, identifying the same object across different frames through the same query, lack inter-frame dependency and variation modeling, making accurate target tracking challenging amid significant frame-to-frame variations; and (2) they handle the temporal feature of a video and build visual-language interaction sequentially, integrating textual constraints belatedly,  which may cause the video features potentially focus on the non-referred objects. Therefore, we propose a novel RVOS architecture called ProxyFormer, which introduces a set of proxy queries to integrate visual and text semantics and facilitate the flow of semantics between them. By progressively updating and propagating proxy queries across multiple stages of video feature encoder, ProxyFormer ensures that the video features are as focused as much possible on the object of interest. This dynamic evolution of the queries across video frames also enables the proxy queries to establish inter-frame dependencies, enhancing the accuracy and coherence of object tracking throughout the video sequence. To mitigate the high computational costs associated with full spatio-temporal interactions between video frames and proxy queries, we propose to decouple cross-modality interactions into their temporal and spatial dimensions, respectively. 
Additionally, we design a Joint Semantic Consistency (JSC) training strategy to align semantic consensus between the proxy queries and the combined video-text pairs.
Comprehensive experiments on four widely used RVOS benchmarks, i.e., Ref-Youtube-VOS, Ref-DAVIS17, A2D-Sentences and JHMDB-Sentences, clearly demonstrate the superiority of our ProxyFormer to the state-of-the-art methods.


## The proposed referring video object segmentation framework
![](https://github.com/Sunbaoli/ProxyFormer/net.pdf)

## Results
![](https://github.com/Sunbaoli/ProxyFormer/result1.jpg)



## Requirements
We test the codes in the following environments, other versions may also be compatible:

` CUDA 11.1 `
` Python 3.7 `
` Pytorch 1.8.1 `

## Download pretrained models

## Data Preparation

We provide the pretrained model for different visual backbones. You may download them here and put them in the directory pretrained_weights.

After the organization, we expect the directory struture to be the following:

ReferFormer/
├── data/
│   ├── ref-youtube-vos/
│   ├── ref-davis/
│   ├── a2d_sentences/
│   ├── jhmdb_sentences/
├── davis2017/
├── datasets/
├── models/
├── scipts/
├── tools/
├── util/
├── pretrained_weights/
├── eval_davis.py
├── main.py
├── engine.py
├── inference_ytvos.py
├── inference_davis.py
├── opts.py
...

## Citation 
If you find this code useful, please cite:

` Baoli Sun* et al., Referring Video Object Segmentation with Cross-Modality Proxy Queries, Submitted to IEEE Trans. IEEE Trans. Multim, Major revision. `




