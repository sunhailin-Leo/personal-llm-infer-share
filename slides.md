---
author: sunhailin-Leo
# You can also start simply with 'default'
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://cover.sli.dev
# some information about your slides (markdown enabled)
title: 浅谈大模型推理引擎
info: |
  ## Slidev Starter Template
  围绕 Attention 优化以及 PD 分离架构

  Learn more at [Sli.dev](https://sli.dev)
# apply unocss classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
---

# 浅谈大模型推理引擎优化

围绕 Attention 优化以及 PD 分离架构（主讲人：孙海林）

<div @click="$slidev.nav.next" class="mt-12 py-1" hover:bg="white op-10">
  Press Space for next page <carbon:arrow-right />
</div>

<div class="abs-br m-6 text-xl">
  <button @click="$slidev.nav.openInEditor" title="Open in Editor" class="slidev-icon-btn">
    <carbon:edit />
  </button>
  <a href="https://github.com/sunhailin-Leo" target="_blank" class="slidev-icon-btn">
    <carbon:logo-github />
  </a>
</div>

<!--
本次分享主要围绕月之暗面的 PD 分离架构，以及 FlashAttention 的优化，还有一些 GPU 底层相关的技术面分享
-->

---
transition: fade-out
---

# 推理引擎优化方向

细方向很多，但先挑重点来说

- 📝 **Attention 优化** - implement sparse or merged attention to reduce computation and improve efficiency.
- 🎨 **Weight Quantize 优化** - reduce storage and computation cost.
- 🧑‍💻 **KV Cache 优化** - minimize redundancy, accelerate inference.
- 🤹 **Content/Prompt KV Cache 优化** - optimize context/prompt cache, improve efficiency.
- 🎥 **Parallel Decoding/Sampling 优化** - parallel threading, speed up generation.
- 📤 **GPU Infra 优化** - enhance gpu utilization, maximize performance.
- 🛠 **GEMM/Tensor Cores/WMMA 并行优化** - accelerate matrix ops, boost efficiency.
  <br>
  <br>

<!--
优化方向很多，目前还在发展中，所以挑几个重点的来说就好了
-->

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Here is another comment.
-->

---
layout: two-cols
layoutClass: gap-16
hideInToc: true
---

# 目录

分享点：
* PD 分离架构
* FlashAttention 的性能提升
* GPU 和推理服务评价的相关知识和指标定义

::right::

<Toc text-sm minDepth="1" maxDepth="1" />

---
layout: image-right
image: img.png
backgroundSize: 46em
src: ./pages/01-sre/p0.md
---

---
layout: image-right
image: img.png
backgroundSize: 46em
hideInToc: true
src: ./pages/01-sre/p1.md
---

---
layout: image-right
image: img.png
hideInToc: true
backgroundSize: 46em
src: ./pages/01-sre/p2.md
---

---
layout: image-left
image: img-1.png
backgroundSize: 32em 50%
transition: fade-out
src: ./pages/02-gpu/p0.md
---

---
layout: image-left
image: img-2.png
hideInToc: true
backgroundSize: 27em 100%
src: ./pages/02-gpu/p1.md
---

---
layout: image-left
image: img-3.png
backgroundSize: 28em 60%
hideInToc: true
src: ./pages/02-gpu/p2.md
---

---
layout: image-left
image: img-4.png
backgroundSize: 30em 95%
src: ./pages/02-gpu/p3.md
---

---
hideInToc: true
src: ./pages/02-gpu/p4.md
---

---
transition: fade-out
src: ./pages/02-gpu/p5.md
---

---
transition: slide-up
level: 1
src: ./pages/03-vllm/p0.md
---

---
transition: slide-up
layout: image-left
image: img-5.png
backgroundSize: 30em 55%
hideInToc: true
src: ./pages/03-vllm/p1.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/03-vllm/p2.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/03-vllm/p3.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/03-vllm/p4.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/03-vllm/p5.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/03-vllm/p6.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/03-vllm/p7.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/03-vllm/p8.md
---

---
transition: fade-out
hideInToc: true
src: ./pages/03-vllm/p9.md
---

---
transition: slide-up
src: ./pages/04-trtllm/p0.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/04-trtllm/p1.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/04-trtllm/p2.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/04-trtllm/p3.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/04-trtllm/p4.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/04-trtllm/p5.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/04-trtllm/p6.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/04-trtllm/p7.md
---

---
transition: fade-out
hideInToc: true
src: ./pages/04-trtllm/p8.md
---

---
transition: slide-up
src: ./pages/05-flashattention/p0.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/05-flashattention/p1.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/05-flashattention/p2.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/05-flashattention/p3.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/05-flashattention/p4.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/05-flashattention/p5.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/05-flashattention/p6.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/05-flashattention/p7.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/05-flashattention/p8.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/05-flashattention/p9.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/05-flashattention/p10.md
---

---
transition: fade-out
hideInToc: true
src: ./pages/05-flashattention/p11.md
---

---
transition: slide-up
src: ./pages/06-pd分离/p0.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/06-pd分离/p1.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/06-pd分离/p2.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/06-pd分离/p3.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/06-pd分离/p4.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/06-pd分离/p5.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/06-pd分离/p6.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/06-pd分离/p7.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/06-pd分离/p8.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/06-pd分离/p9.md
---

---
transition: slide-up
hideInToc: true
src: ./pages/06-pd分离/p10.md
---

---
transition: fade-out
hideInToc: true
src: ./pages/06-pd分离/p11.md
---

---
transition: slide-up
src: ./pages/07-总结/p0.md
---

---
layout: center
class: text-center
---

# 谢谢观看

[GitHub](https://github.com/sunhailin-Leo) · [知乎](https://www.zhihu.com/people/sunhailin)

<PoweredBySlidev mt-10 />
