---
layout: page
title: TaskTinyVLMs
description: Fintuning efficient VLMs for embodied tasks
img: assets/img/basic_example.png
# redirect: https://unsplash.com
importance: 1
category: work
---

### Abstract
This study addresses the critical challenge of deploying large vision-language models (VLMs) for real-time embodied task planning. While VLMs demonstrate strong multimodal reasoning capabilities, they consistently fail to achieve high-accuracy task planning or real-time inference in embodied scenarios requiring dynamic environment interaction. To bridge this gap, we propose an efficient fine-tuning framework for lightweight VLMs (e.g., Qwen2-VL-7B) on the EmbodiedBench benchmark. We introduce an automated data collection framework where GPT-4o with CoT-optimized prompts generates complexity-tiered tasks and related evaluation functions to gather environment-interaction trajectories; and a parameter optimization analysis through systematic experimentation that determines optimal training configurations, enabling lightweight VLMs to match commercial model performance. Extensive experiments demonstrate that our fine-tuned 7B model achieves near-parity with GPT-4o while drastically reducing inference overhead.

<section class="hero is-small is-light">
  <div class="hero-body">
    <div class="container">
      <h2 class="title">Technical Report</h2>
      <iframe src="{{ '/assets/pdf/tinyvlms.pdf' | relative_url }}" width="100%" height="550"></iframe>
      </div>
    </div>
</section>