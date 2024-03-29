---
layout: project_page
permalink: /

title: Sculpt3D&#58 Multi-View Consistent Text-to-3D Generation with Sparse 3D Prior
authors:
    Cheng Chen<sup>1</sup>, Xiaofeng Yang<sup>1</sup>, Fan Yang<sup>1</sup>, Chengzeng Feng<sup>1</sup>, Zhoujie Fu <sup>1</sup>, Chuan-Sheng Foo<sup>2</sup>,  Guosheng Lin<sup>1</sup> and Fayao Liu<sup>2</sup>
affiliations:
    <sup>1</sup>Nanyang Technological University, <sup>2</sup>A*STAR, Singapore
paper: https://arxiv.org/abs/2403.09140
code: https://github.com/StellarCheng/Scuplt_3d/tree/main
---
<div class="columns is-centered has-text-centered">
    <div class="column is-four-fifths">
        <h2>Abstract</h2>
        <div class="content has-text-justified">
Recent works on text-to-3d generation show that using only 2D diffusion supervision for 3D generation tends to produce results with inconsistent appearances (e.g., faces on the back view) and inaccurate shapes (e.g., animals with extra legs). Existing methods mainly address this issue by retraining diffusion models with images rendered from 3D data to ensure multi-view consistency while struggling to balance 2D generation quality with 3D consistency. In this paper, we present a new framework Sculpt3D that equips the current pipeline with explicit injection of 3D priors from retrieved reference objects without re-training the 2D diffusion model. Specifically, we demonstrate that high-quality and diverse 3D geometry can be guaranteed by keypoints supervision through a sparse ray sampling approach. Moreover, to ensure accurate appearances of different views, we further modulate the output of the 2D diffusion model to the correct patterns of the template views without altering the generated object's style. These two decoupled designs effectively harness 3D information from reference objects to generate 3D objects while preserving the generation quality of the 2D diffusion model. Extensive experiments show our method can largely improve the multi-view consistency while retaining fidelity and diversity.        </div>
    </div>
</div>




## Performance on T3Bench


| Dataset      | Dreamfusion | Magic3D | LatentNeRF | Fantasia3D |  ProlificDreamer | **Ours-Sculpt3D**|
|:------------:|:-----------:|:-------:|:----------:|:----------:|:---------------:|:-----------------:|
| Quality      |     24.9    |   38.7  |    34.2    |    29.2    |     51.1        |     **53.6**      |  
| Alignment    |     24.0    |   35.3  |    32.0    |    23.5    |     47.8        |     **49.3**      |  
| Cons. Rate   |      34%    |    38%  |     30%    |     26%    |     32%         |      **76%**      |  

We achieve state-of-the-art performance on T3Bench. We manually identify and count 3D inconsistencies (e.g., multiple faces, legs, and other distorted shapes.) to calculate the consistent rate of each method. 

## Generation Results 

<table style="border: none; width: 100%;">
  <tr>
    <td style="text-align: center;">
    <video width="320" height="240" autoplay controls muted loop style="object-fit: cover;">
    <source src="static/image/small_saguaro_cactus_1.mp4" type="video/mp4">
    </video>
      <br><em>Small saguaro cactus</em>
    </td>
    <td style="text-align: center;"> 
    <video width="320" height="240" autoplay controls muted loop style="object-fit: cover;">
    <source src="static/image/a car made out of sushi.mp4" type="video/mp4">
    </video>
      <br><em>A car made out of sushi</em> 
    </td> 
    <td style="text-align: center;">
    <video width="320" height="240" autoplay controls muted loop style="object-fit: cover;">
    <source src="static/image/an iron key.mp4" type="video/mp4">
    </video>
      <br><em>An iron key</em>
    </td>
    <td style="text-align: center;"> 
    <video width="320" height="240" autoplay controls muted loop style="object-fit: cover;">
    <source src="static/image/carnival mask.mp4" type="video/mp4">
    </video>
      <br><em>A gold glittery carnival mask</em> 
    </td>
  </tr>
</table>

<table style="border: none; width: 100%;">
  <tr>
    <td style="text-align: center;">
    <video width="320" height="240" autoplay controls muted loop style="object-fit: cover;">
    <source src="static/image/colorful_parrot.mp4" type="video/mp4">
    </video>
      <br><em>A colorful parrot on a tree branch</em>
    </td>
    <td style="text-align: center;"> 
    <video width="320" height="240" autoplay controls muted loop style="object-fit: cover;">
    <source src="static/image/feather_pen.mp4" type="video/mp4">
    </video>
      <br><em>An elegant feather-quill ink pen</em> 
    </td> 
    <td style="text-align: center;">
    <video width="320" height="240" autoplay controls muted loop style="object-fit: cover;">
    <source src="static/image/imperial_state_crown.mp4" type="video/mp4">
    </video>
      <br><em>An imperial state crown of england</em>
    </td>
    <td style="text-align: center;"> 
    <video width="320" height="240" autoplay controls muted loop style="object-fit: cover;">
    <source src="static/image/house_in_Tudor_style.mp4" type="video/mp4">
    </video>
      <br><em>A model of a house in Tudor style</em> 
    </td>
  </tr>
</table>

## Diverse Generation Results 

<table style="border: none;">
  <tr>
    <td style="text-align: center;">
    <video width="320" height="240" autoplay controls muted loop style="object-fit: cover;">
    <source src="static/image/A_blooming_potted_orchid_with_purple_flowers_1.mp4" type="video/mp4">
    </video>
      <br><em>A blooming potted orchid with purple flowers</em>
    </td>
    <td style="text-align: center;">
    <video width="320" height="240" autoplay controls muted loop style="object-fit: cover;">
    <source src="static/image/A_blooming_potted_orchid_with_purple_flowers_0.mp4" type="video/mp4">
    </video>    
      <br><em>A blooming potted orchid with purple flowers</em>
    </td>
  </tr>
  <tr>
    <td style="text-align: center;">
    <video width="320" height="240" autoplay controls muted loop style="object-fit: cover;">
    <source src="static/image/a_metal_wristwatch_1.mp4" type="video/mp4">
    </video>
      <br><em>A metal wristwatch</em>
    </td>
    <td style="text-align: center;">
    <video width="320" height="240" autoplay controls muted loop style="object-fit: cover;">
    <source src="static/image/a metal wristwatch.mp4" type="video/mp4">
    </video>    
      <br><em>A metal wristwatch</em>
    </td>
  </tr>
</table>

## Appearance Refinement Results

<table style="border: none;">
  <tr>
    <td style="text-align: center;">
    <video width="320" height="240" autoplay controls muted loop style="object-fit: cover;">
    <source src="static/image/983.mp4" type="video/mp4">
    </video>
      <br><em>Generated results with appearance ambiguity</em>
    </td>
    <td style="text-align: center;">
    <video width="320" height="240" autoplay controls muted loop style="object-fit: cover;">
    <source src="static/image/1000_raw.mp4" type="video/mp4">
    </video>    
      <br><em>Correct appearance result using our appearance modulation strategy</em>
    </td>
  </tr>
</table>


## Citation
```
@article{chen2024sculpt3d,
  title={Sculpt3D: Multi-View Consistent Text-to-3D Generation with Sparse 3D Prior},
  author={Chen, Cheng and Yang, Xiaofeng and Yang, Fan and Feng, Chengzeng and Fu, Zhoujie and Foo, Chuan-Sheng and Lin, Guosheng and Liu, Fayao},
  journal={arXiv preprint arXiv:2403.09140},
  year={2024}
}
```
