# Current work

**[Pwsh](https://github.com/MansfieldPlumbing/Pwsh)** — Runs PowerShell on
Android. One PowerShell script builds the app from pinned, hash-verified
inputs, with no .NET SDK, Android SDK or MSBuild. Inside the app, PowerShell
runs in-process on CoreCLR.

**[Kokoro-Hexagon](https://github.com/MansfieldPlumbing/Kokoro-Hexagon)** —
Kokoro-82M is an open text-to-speech model. This project runs it on Qualcomm's
Hexagon DSP, with the code written in PowerShell. In development. Qualcomm's
QNN runtime is used only as a reference to check results.

**[V340L-Emancipated](https://github.com/MansfieldPlumbing/V340L-Emancipated)**
— Machine-learning compute on the AMD Radeon Pro V340L (four GPU dies per card)
under Windows, using DirectML and Direct3D 12. It hooks the compute path of
stock ggml, the tensor library behind llama.cpp, and is driven from PowerShell
with no compiler or build step. In development.

**[QuickPS](https://github.com/MansfieldPlumbing/QuickPS)** — Small PowerShell
building blocks for Windows graphics and native APIs: windows, Direct3D 12
rendering, DirectComposition, audio capture, camera and 3D geometry. They call
Windows directly, with no wrapper DLL or renderer framework.

**[Kinetics](https://github.com/MansfieldPlumbing/Kinetics)** — An interactive
lyric performance for an original song, built in TypeScript. The lyrics are laid
out across a large 2D space and a camera moves between them in time with the
music. [Live in the browser](https://mansfieldplumbing.github.io/kinetics/).
