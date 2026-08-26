# I fix the pipes.

I work at the boundaries between **models, runtimes, operating systems, drivers, and hardware**.

When the existing stack adds copies, scheduler hops, unsupported hardware, unnecessary process boundaries, or an abstraction that prevents the machine from doing what it can actually do, I build the missing piece.

Most of that work is invisible when it is working correctly.

## Systems

**[AndroidSMA](https://github.com/MansfieldPlumbing/AndroidSMA)**
Persistent `System.Management.Automation` hosted in-process as an Android application runtime. PowerShell owns live application state while operating directly on Android objects, Binder IPC, native presentation, and Qualcomm QNN/Hexagon execution. Physical-device work includes 119–120 Hz presentation and QNN graphs executed on SM8550 Hexagon HTP.

**[DirectPort-SDK](https://github.com/MansfieldPlumbing/DirectPort-SDK)**
NT object-based GPU IPC for shared VRAM between processes. D3D12 fences provide hardware synchronization without polling, CPU semaphores, copies, or scheduler-mediated wakeups. A minimal D3D12 device resolves named NT resources while D3D11 remains the resource owner.

**[DirectPort-Legacy](https://github.com/MansfieldPlumbing/DirectPort-Legacy)**
Compatibility boundary for applications built around pull semantics. The adapter absorbs the impedance mismatch without weakening DirectPort's push transport underneath.

**[VirtuaCam](https://github.com/MansfieldPlumbing/VirtuaCam)**
Zero-copy multi-process GPU video broker and Media Foundation virtual-camera source. Producers share D3D11 textures and fences through NT handles; composition and inter-process frame transport remain on the GPU.

## Inference

**[Demucs_v4_TRT](https://github.com/MansfieldPlumbing/Demucs_v4_TRT)**
HTDemucs v4 on TensorRT with STFT/ISTFT internalized into the graph, preserving the dual time/frequency architecture while allowing fusion across the complete inference path. Approximately 5 seconds end-to-end for a 3-minute track on RTX 3090. No Python at runtime.

**[RIFE_TRT](https://github.com/MansfieldPlumbing/RIFE_TRT)**
RIFE 4.9 frame interpolation on TensorRT. Native C++ CUDA execution with an unsafe C# memory path for real-time tensor layout conversion. 2×/4×/8× interpolation without Python or intermediate frame files.

**[Depth_TRT](https://github.com/MansfieldPlumbing/Depth_TRT)**
Depth Anything V2 on TensorRT using a NativeAOT C# orchestrator and unmanaged inference bridge. Preprocessing and tensor conversion stay in the native Windows pipeline. No Python at runtime.

## Hardware

**[v340l-windows-enablement](https://github.com/MansfieldPlumbing/v340l-windows-enablement)**
Windows enablement work for the dual-die AMD Radeon Pro V340L. The board requires Switchtec PCIe-fabric initialization and SR-IOV/GFMS control before the GPU silicon becomes usable. Work includes KMDF and userspace control-plane components.

---

[HuggingFace](https://huggingface.co/MansfieldPlumbing) · [YouTube](https://youtube.com/hacktheplanet)
