---
layout: code_page
permalink: /btl/
title: BTL Model
description:
nav: true
nav_order: 2
---

## Bradely Terry Luce Model

<p align="center">
    <img src="/assets/BTL.jpg" alt="interface" width="760">
      <br>
</p>

- The BTL model is frequently used in sports to rank players within a league
- To identify the dominating factors that influence human judgement, we use BTL model to rank factors that characterize system outputs

    1. When one summary is favored over another, $ 𝑆_1^{(𝑛)}≻𝑆_2^{(𝑛)} $, we assume all of its factors win over those of the other summary
    2. If there are same factors appears in both summaries, we assume they cancel each other out and exclude them from list of factors
    3. We then represent the outcomes of these comparisons using a win-loss matrix $$ W: 𝑤_{𝑖,𝑗} (𝑖, 𝑗∈𝑀)$$
    4. The BTL model allows us to estimate the relative importance of these factors $ \(𝑝_{i})_{𝑖=1}^𝑀 $, which is iteratively updated (Eq. (1)) to maximize the data likelihood and then renormalized (Eq. (2))
    
    $$ 𝑝_𝑖^′=𝑊_𝑖 (\sum_{𝑗≠𝑖} \frac{𝑤_𝑖𝑗+𝑤_𝑗𝑖}{𝑝_𝑖+𝑝_𝑗 })^{−1}  (1)  $$
  
    $$  𝑝_𝑖=\frac{𝑝_𝑖^′}{\sum_{𝑗=1}^𝑀 𝑝_𝑗^′}  (2)  $$

<br>
## Influential Factors Ranking


<p align="center">
    <img src="/assets/factors_ranking.png" alt="interface" width="760">
      <br>
</p>

<br>

## Cross-domain Preferences Comparison

<div style="display: flex; align-items: center;">
    <img src="/assets/reddit-cnndm.jpg" alt="interface" width="360" style="margin-right: 20px;">
    <p>
        Factors impacting summarization tasks can vary across different source domains. For news summarization, which is shown in blue, lengthier summaries are often favored {<strong>len-{ch|tk}-xlong</strong>}, as is comprehensive coverage of the source content {<strong>{src|consec}-cov-high</strong>}. The style of the summary reflects that of the original article {<strong>style-aligned</strong>}, and off-focus content tends to have minimal impact than {<strong>off-focus-many</strong>}
    </p>
</div>
