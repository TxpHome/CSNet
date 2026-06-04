# Degradation-Aware Channel Activation for Multi-Degradation Image Restoration


## Abstract

The goal of multi-degradation (also referred to as multi-task or all-in-one) image restoration is to address multiple types of image degradations using a single model. Owing to the divergence among degradation characteristics, directly applying models designed for specific restoration tasks to the multi-degradation scenario often leads to performance degradation. Therefore, incorporating prior knowledge of degradations has become a key strategy for enhancing performance. Existing approaches include implicit prompts (e.g., PromptIR), learnable dynamic prompts (e.g., DPPD), textual prompts (e.g., InstructIR), frequency-domain discrepancies (e.g., AdaIR), and features derived from large pre-trained models (e.g., Perceive-IR). Although these methods have demonstrated promising results, they still suffer from the following limitations:

  **► Limitation-1**: Existing methods mainly operate at the prompt, task, or expert level, while overlooking fine-grained channel-level characteristics of image features. Consequently, degradation-specific responses are insufficiently disentangled, leading to redundant and entangled feature representations.
  
  **► Limitation-2**: Most existing guidance mechanisms rely on soft modulation strategies, such as attention-based reweighting or prompt conditioning. Although these methods can alleviate degradation interference to some extent, they do not explicitly model channel-wise suppression, leaving residual cross-degradation interference in the learned representations.
  
  **► Limitation-3**: Existing studies primarily utilize guidance features for degradation discrimination, prompt conditioning, or expert routing. However, the intrinsic role of degradation-aware guidance in shaping feature representations has not been thoroughly explored. In particular, it remains unclear how degradation cues can be leveraged to selectively activate informative channels and facilitate more effective restoration.
  

To address the aforementioned challenges, we propose a novel Degradation-Aware Channel Activation framework, termed DACA-IR, for multi-degradation image restoration. The framework incorporates an explicit degradation-aware prompting mechanism that extracts degradation-related cues from degraded images and provides adaptive guidance for restoration. Furthermore, we introduce a degradation-aware channel activation strategy that dynamically activates informative channels while suppressing degradation-irrelevant responses into a silent state. By explicitly regulating channel-wise activation patterns, the proposed framework effectively alleviates feature entanglement across different degradations and promotes more discriminative feature representations, leading to improved restoration performance.

  **For Limitation-1**: We explicitly investigate channel-wise feature interactions under different degradations and develop a degradation-aware channel activation framework that performs adaptive feature regulation directly in the channel space, rather than at the prompt, task, or expert level.

  **For Limitation-2**: Unlike existing prompt-guided fusion strategies based on channel attention or spatial attention, we introduce an adaptive channel activation mechanism that selectively activates informative channels while driving degradation-irrelevant channels into a silent state, thereby reducing feature entanglement across different degradations.



<!-- <p align="center">
  <img src="./images/Prompt_generation.png" alt="">
</p> -->

  **For Limitation-3**: we further investigate the underlying role of degradation-aware guidance in feature learning. Experimental analyses reveal that channel activation exhibits distinct behaviors across network depths: in shallow layers, degradation cues primarily enhance texture and detail representations, whereas in deeper layers they strengthen degradation-discriminative representations, providing a clearer understanding of how degradation prompts contribute to image restoration.


<!-- <p align="center">
  <img src="./images/NEt-work.png" alt="">
</p> -->





<details>
<summary><b>Quantitative Comparison with SOTA (click to expand)</b></summary>
<br>

<p align="center">
  <img src="images/3D.png" alt="">
</p>

<p align="center">
  <img src="images/5D.png" alt="">
</p>

<p align="center">
  <img src="images/CDD-11.png" alt="">
</p>

</details>



<details>
<summary><b>Additional Visual Comparison Results (click to expand)</b></summary>
<br>

<p align="center">
  <img src="images/Dehaze3D_supp.png" alt="">
</p>

<p align="center">
  <img src="images/Denoise3D_supp.png" alt="">
</p>

<p align="center">
  <img src="images/Derain3D_supp.png" alt="">
</p>

<p align="center">
  <img src="images/supp_deblur_lol.png" alt="">
</p>

<p align="center">
  <img src="images/supp_haze_rain.png" alt="">
</p>

<p align="center">
  <img src="images/supp_haze_snow.png" alt="">
</p>


<p align="center">
  <img src="images/supp_low_haze.png" alt="">
</p>

<p align="center">
  <img src="images/supp_low_rain.png" alt="">
</p>

<p align="center">
  <img src="images/supp_low_snow.png" alt="">
</p>

</details>






