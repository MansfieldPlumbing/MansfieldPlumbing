# Current work

**[Pwsh](https://github.com/MansfieldPlumbing/Pwsh)** — An Android app that
carries CoreCLR and System.Management.Automation, so PowerShell runs in-process
on the device and `.ps1` scripts are the application layer. One PowerShell
script builds the signed APK from pinned, hash-verified inputs, with no .NET
SDK, Android SDK, JDK or MSBuild. Preview.

**[Kokoro-Hexagon](https://github.com/MansfieldPlumbing/Kokoro-Hexagon)** —
Kokoro-82M text-to-speech on Qualcomm's Hexagon processor, written in
PowerShell. PowerShell lowers the model's graph and weights and emits the
Hexagon code at build time; the device runs the result. The target is a small
model-less Android app plus a separately verified model DLL. In development.
QNN, ONNX Runtime and PyTorch serve only as references; none is a build or
runtime dependency.

**[V340L-Enablement](https://github.com/MansfieldPlumbing/V340L-Enablement)** —
Windows enablement and verification for AMD Radeon Pro V340L cards: driver
package preparation, adapter discovery, DirectML operator probes and recorded
measurements. It also holds the postmortem of the closed multi-die llama.cpp
experiment.

**[DirectAI](https://github.com/MansfieldPlumbing/DirectAI)** — A Windows
ONNX Runtime/DirectML inference runtime with plugin, HTTP, named-pipe and CLI
hosts that PowerShell can load directly. Runs SD1.5 LCM with whole model stages
placed on separate GPUs. In development.

**[QuickPS](https://github.com/MansfieldPlumbing/QuickPS)** — PowerShell
scripts that call Windows graphics, audio and window APIs directly: Win32
windows, DXGI, Direct3D 12 with runtime HLSL compilation, DirectComposition,
WIC images, WASAPI capture and Media Foundation devices, plus camera matrices
and 3D shapes. No wrapper DLL, managed bridge or renderer framework. Windows
only. MIT.

**[Kinetics](https://github.com/MansfieldPlumbing/Kinetics)** — An interactive
lyric performance for an original track by Scott Mansfield, built in
TypeScript. Timed lyrics become one continuous typographic space: words form
spatial lockups and the camera travels between them in time with the audio.
[Live in the browser](https://mansfieldplumbing.github.io/kinetics/).
