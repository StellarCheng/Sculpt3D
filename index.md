---
layout: project_page
permalink: /

title: Sculpt3D: Multi-View Consistent Text-to-3D Generation with Sparse 3D Prior
authors:
    Cheng Chen<sup>1</sup>, Xiaofeng Yang<sup>1</sup>, Fan Yang<sup>1</sup>, Chengzeng Feng<sup>1</sup>, Zhoujie Fu <sup>1</sup>, Chuan-Sheng Foo<sup>2</sup>,  Guosheng Lin<sup>1</sup> and Fayao Liu<sup>2</sup>
affiliations:
    <sup>1</sup>Nanyang Technological University, <sup>2</sup>A*STAR, Singapore
paper: https://arxiv.org/abs/2312.04820
code: https://github.com/yangxiaofeng/LODS
---

<div class="columns is-centered has-text-centered">
    <div class="column is-four-fifths">
        <h2>Abstract</h2>
        <div class="content has-text-justified">
Recent works on text-to-3d generation show that using only 2D diffusion supervision for 3D generation tends to produce results with inconsistent appearances (e.g., faces on the back view) and inaccurate shapes (e.g., animals with extra legs). Existing methods mainly address this issue by retraining diffusion models with images rendered from 3D data to ensure multi-view consistency while struggling to balance 2D generation quality with 3D consistency. In this paper, we present a new framework Sculpt3D that equips the current pipeline with explicit injection of 3D priors from retrieved reference objects without re-training the 2D diffusion model. Specifically, we demonstrate that high-quality and diverse 3D geometry can be guaranteed by keypoints supervision through a sparse ray sampling approach. Moreover, to ensure accurate appearances of different views, we further modulate the output of the 2D diffusion model to the correct patterns of the template views without altering the generated object's style. These two decoupled designs effectively harness 3D information from reference objects to generate 3D objects while preserving the generation quality of the 2D diffusion model. Extensive experiments show our method can largely improve the multi-view consistency while retaining fidelity and diversity.        </div>
    </div>
</div>




## Performance on T3Bench (with NeRF)


| Dataset      | Dreamfusion | Magic3D | LatentNeRF | Fantasia3D | SJC  | ProlificDreamer | LODS Emb. | LODS LoRA |
|:------------:|:-----------:|:-------:|:----------:|:----------:|:----:|:---------------:|:---------:|:---------:|
| Single Obj.  |     24.4    |   37.0  |    33.1    |    26.4    | 24.7 |       49.4      |  **52.3** |    51.3   |
| Surroundings |     24.6    |   35.4  |    30.6    |    27.0    | 19.8 |       44.8      |  **49.8** |    47.3   |
| Multi. Obj.  |     16.1    |   25.7  |    20.6    |    18.5    | 11.7 |       35.8      |  **39.7** |    37.5   |
| Average      |     21.7    |   32.7  |    28.1    |    24.0    | 18.7 |       43.3      |  **47.3** |    45.4   |

We achieve state-of-the-art performance on T3Bench.

## Generation Results (NeRF)

<table style="border: none;">
  <tr>
    <td style="text-align: center;">
      <img src="static/image/demo_gif1.gif" alt="A red and white lighthouse on a cliff" />
      <br><em>A red and white lighthouse on a cliff</em>
    </td>
    <td style="text-align: center;">
      <img src="static/image/demo_gif2.gif" alt="An intricately-carved wooden chess set" />
      <br><em>An intricately-carved wooden chess set</em>
    </td>
  </tr>
  <tr>
    <td style="text-align: center;">
      <img src="static/image/demo_gif3.gif" alt="A cactus with pink flowers" />
      <br><em>A cactus with pink flowers</em>
    </td>
    <td style="text-align: center;">
      <img src="static/image/demo_gif4.gif" alt="A vintage porcelain doll with a frilly dress" />
      <br><em>A vintage porcelain doll with a frilly dress</em>
    </td>
  </tr>
</table>

## Generation Results (3D Gaussian Splatting)

<table style="border: none;">
  <tr>
    <td style="text-align: center;">
      <img src="static/image/demo_gif_gs_1.gif" alt="A DSLR image of a hamburger" />
      <br><em>A DSLR image of a hamburger</em>
    </td>
    <td style="text-align: center;">
      <img src="static/image/demo_gif_gs_2.gif" alt="A pair of worn-in blue jeans" />
      <br><em>A pair of worn-in blue jeans</em>
    </td>
  </tr>
  <tr>
    <td style="text-align: center;">
      <img src="static/image/demo_gif_gs_3.gif" alt="A worn-out leather briefcase" />
      <br><em>A worn-out leather briefcase</em>
    </td>
    <td style="text-align: center;">
      <img src="static/image/demo_gif_gs_4.gif" alt="An ivory candlestick holder" />
      <br><em>An ivory candlestick holder</em>
    </td>
  </tr>
</table>


## Citation
```
@article{yang2023lods,
  title={Learn to Optimize Denoising Scores for 3D Generation},
  author={Xiaofeng Yang, Yiwen Chen, Cheng Chen, Chi Zhang, Yi Xu, Xulei Yang, Fayao Liu and Guosheng Lin},
  journal={arXiv:2312.04820},
  year={2023}
}
```
