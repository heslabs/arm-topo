# arm-topo

---
### Github
https://github.com/arm/topo

---
### Install topo - Linux and macOS

```
curl -fsSL https://raw.githubusercontent.com/arm/topo/refs/heads/main/scripts/install.sh | sh
```

---
### Getting Started

```
topo setup-keys --target ssh://demo@192.168.52.56
topo health --target demo@192.168.52.56
```


#### 1. Check that everything is ready

```
topo health --target demo@192.168.52.56
```

**Log message:** 
```
Host
----
Topo: ✅ (topo)
SSH: ✅ (ssh)
Container Engine: ✅ (docker)

Target
------
Connectivity: ✅
Container Engine: ❌ (ssh command to ssh://demo@192.168.52.56 failed: exit status 1 | stderr: errors pretty printing info
)
  → Ensure current user can run docker commands
Hardware Info: ✅ (lscpu)
Subsystem Driver (remoteproc): ℹ (no remoteproc devices found)
```


#### 2. Find a template

```
topo templates --target [user@]host
topo templates --target demo@192.168.52.56
```

**Log message:** 
```✅ Hello World | https://github.com/Arm-Examples/topo-welcome.git | main
  A minimal "Hello, World" web app for validating a Topo setup and deployment.
  It runs a single service that exposes a web page on the target,
  with the greeting text customizable via the GREETING_NAME parameter.

❌ Lightbulb Moment | https://github.com/Arm-Examples/topo-lightbulb-moment.git | main
  Features: remoteproc-runtime
  Reads a switch over GPIO pins on an M class cpu, reports switch state over
  Remoteproc Message, then a web application on the A class reads this and
  displays a lightbulb in either the on or off state. The lightbulb state is
  described by an LLM in any user-specified style.

✅ Topo CPU AI Chat | https://github.com/Arm-Examples/topo-cpu-ai-chat.git | main
  Features: SVE, NEON
  Complete LLM chat application optimized for Arm CPU inference.

  This project demonstrates running large language models on CPU
  using llama.cpp compiled with Arm baseline optimizations and
  accelerated using NEON SIMD and SVE (when supported and enabled).

  The stack includes:
  - llama.cpp server with Arm NEON optimizations (SVE optional)
  - Quantized Qwen3.5-0.8B model bundled in the image
  - Simple web-based chat interface
  - No GPU required - pure CPU inference

  Perfect for demos and testing! The bundled Qwen3.5-0.8B model allows the
  project to run immediately without downloading additional models.

  Ideal for testing LLM workloads on Arm hardware without GPU dependencies,
  showcasing how far you can push NEON acceleration. Rebuild with SVE enabled
  when wider vectors are available.

✅ SIMD Visual Benchmark | https://github.com/Arm-Examples/topo-simd-visual-benchmark.git | main
  Features: NEON, SVE
  Visual demonstration of SIMD performance benefits on Arm processors.
  Compare scalar (no SIMD), NEON (128-bit), and SVE (scalable vector)
  implementations running identical image processing workloads side-by-side.

  This demo shows real hardware acceleration through three C++ services
  compiled with different architecture flags, processing the same box blur
  algorithm on images. Performance differences are measured in real-time
  and displayed in an interactive web dashboard.

  Perfect for demonstrating to non-technical audiences the concrete benefits
  of SIMD optimizations, with visual results and quantified speedups.
```


