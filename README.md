# Current work

**[Pwsh](https://github.com/MansfieldPlumbing/Pwsh)** — PowerShell on Android,
built by one PowerShell script (`setup.ps1`) from pinned, hash-verified inputs:
no .NET SDK, Android SDK, JDK or MSBuild. The signed APK contains no DEX.
`NativeActivity` loads an emitted native host that starts CoreCLR, serves
IL-only assemblies in place from an emitted store, opens a runspace on the main
thread and runs `Profile.ps1`. The 91-assembly payload is proven on the x86_64
emulator, a Galaxy S23 (arm64) and an arm32 device. A console model passes its
63 conformance vectors on all three; it is a probe, not yet the integrated
terminal. The command-assembly payload has not passed its device gate.

**[Kokoro-Hexagon](https://github.com/MansfieldPlumbing/Kokoro-Hexagon)** —
Kokoro-82M speech on Qualcomm Hexagon, authored in PowerShell. Not yet an
end-to-end synthesizer. Done so far: all 548 FP32 tensors extracted from the
pinned checkpoint without PyTorch and read back from a managed DLL; a
phoneme-contract DLL; a directly emitted V73 HVX kernel test passing on SM8550
and SM8635; and a model-less APK that launches on both devices. The full graph
and live speech are not done.

**[V340L-Emancipated](https://github.com/MansfieldPlumbing/V340L-Emancipated)**
— No-build PowerShell, DirectML and D3D12 compute for the AMD Radeon Pro V340L
on Windows. Verified: DirectML devices and an exact FP16 GEMM on all four dies;
a decoded stock ggml `GGML_OP_MUL_MAT` executed through DirectML on each die by
intercepting `graph_compute`; four in-memory V340 devices registered with stock
ggml; bytes moved across adjacent dies through a shared host allocation. Not
yet: a complete llama layer or any model throughput measurement.

**[QuickPS](https://github.com/MansfieldPlumbing/QuickPS)** — Win32, DXGI,
D3D12, runtime HLSL compilation, DirectComposition, WIC, WASAPI capture, Media
Foundation device enumeration, camera matrices and indexed geometry, bound
directly from PowerShell. No wrapper DLL, managed bridge or renderer framework.
Windows only; MIT licensed.

**[Kinetics](https://github.com/MansfieldPlumbing/Kinetics)** — An interactive
lyric performance for an original track: timed lyrics and choreography become a
positioned scene graph and a camera path on a canvas stage, with presentation,
karaoke, math, debug and orthographic views. TypeScript, static site,
[live here](https://mansfieldplumbing.github.io/kinetics/). The choreography is
authored in source; there is no keyframe editor.
