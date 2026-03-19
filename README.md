## Focus

Windows-native inference infrastructure. The work is about eliminating the overhead between ML models and the hardware they run on — zero-copy memory transports, KMDF drivers, TensorRT engine construction, PCIe fabric management.

Most of the stack that makes this possible is invisible by design.

---

## Projects

**[DirectPort-SDK](https://github.com/MansfieldPlumbing/DirectPort-SDK)**
NT kernel object-based GPU IPC. Shared VRAM between processes via NT named handles and DX12 fences. Hardware-synchronized push architecture — the producer signals a GPU queue wait, not a CPU semaphore, so the consumer unblocks at PCIe crossbar latency (~170ns) rather than through the OS scheduler (1–15ms). D3D11 lacks the API to resolve NT handle strings directly; the SDK keeps a single D3D12 device alive purely as a name resolver, letting D3D11 own the actual resource. No polling, no copies.

**[DirectPort-Legacy](https://github.com/MansfieldPlumbing/DirectPort-Legacy)**
Adapter layer that converts DirectPort's push model into a pull interface for applications that can't be modified. The transport primitive underneath is unchanged — the adapter absorbs the impedance mismatch at the boundary, not inside the pipeline.

**[VirtuaCam](https://github.com/MansfieldPlumbing/VirtuaCam)**
Multi-process zero-copy GPU video broker with a Media Foundation COM source. Producer applications share D3D11 textures and fences via NT handles; a central broker multiplexes feeds from multiple producers into a composited output (single source or PIP grid) and delivers frames into the Media Foundation pipeline as a system-registered virtual camera. All inter-process frame transfers stay on the GPU. WASAPI loopback capture included.

**[RIFE_TRT](https://github.com/MansfieldPlumbing/RIFE_TRT)**
RIFE 4.9 frame interpolation on TensorRT. 2x/4x/8x frame rate multiplication at ~28ms per frame pair on RTX 3090. Zero-copy in-memory pipeline: C# unsafe `Parallel.For` handles real-time CHW transposition from packed RGB, a C++ DLL drives the async CUDA execution context, audio is stream-copied via a single FFmpeg mux pass at the end. No Python at runtime.

**[Depth_TRT](https://github.com/MansfieldPlumbing/Depth_TRT)**
Depth Anything V2 on TensorRT. C# NativeAOT orchestrator with unsafe `Parallel.For` + `LockBits` for real-time CHW tensor transposition. ImageNet normalization baked into the unmanaged C++ inference bridge. No Python at runtime.

**[Demucs_v4_TRT](https://github.com/MansfieldPlumbing/Demucs_v4_TRT)**
HTDemucs v4 on TensorRT. STFT/ISTFT internalized inside the traced graph to preserve the dual-path time/frequency architecture and achieve full kernel fusion across both branches. ~5 seconds end-to-end on RTX 3090 for a 3-minute track. No Python at runtime. Published on [HuggingFace](https://huggingface.co/MansfieldPlumbing/Demucs_v4_TRT).

**[v340l-windows-enablement](https://github.com/MansfieldPlumbing/v340l-windows-enablement)**
Custom KMDF driver and userspace daemon to activate the dual-die AMD Radeon Pro V340L on Windows. The card requires Microsemi Switchtec PCIe fabric initialization and a software SR-IOV mailbox implementation before the GPU silicon responds. No prior Windows activation of this card exists. Hardware validation in progress.

---

[HuggingFace](https://huggingface.co/MansfieldPlumbing) · [YouTube](https://youtube.com/hacktheplanet)
