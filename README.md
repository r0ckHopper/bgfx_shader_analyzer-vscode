# bgfx_shader_analyzer-vscode

Language server support for bgfx shader files (`.sc`) in Visual Studio Code.

Based on [glsl_analyzer](https://github.com/nolanderc/glsl_analyzer), extended with bgfx-specific support.

## Features

- Completion
    - User-defined variables/functions
    - bgfx built-in uniforms (`u_view`, `u_proj`, `u_modelViewProj`, etc.)
    - bgfx macros (`SAMPLER2D`, `NUM_THREADS`, `BUFFER_RO`, `IMAGE2D_WO`, etc.)
    - bgfx utility functions (`texture2D`, `vec2_splat`, `mtxFromRows`, etc.)
    - Standard GLSL built-in types and functions
- Inline hover documentation
- Go-to-definition for `$input`/`$output` symbols and sampler variables
- Parsing of bgfx directives (`$input`, `$output`, `$raw`)
- Formatter that preserves bgfx directive structure
- Support for `#include`

## Requirements

Automatically downloads and installs the latest
[`bgfx_shader_analyzer`](https://github.com/r0ckHopper/bgfx_shader_analyzer) (Linux, Windows and macOS).

If your platform is not supported, or you want to build from source, follow the instructions
[here](https://github.com/r0ckHopper/bgfx_shader_analyzer). Then, set the `bgfx-shader-analyzer.path` setting to
the location of your executable.

## Known Limitations

- Platform-conditional code (`#ifdef BGFX_SHADER_LANGUAGE_HLSL` etc.) is not analyzed — GLSL interpretation is used by default
- bgfx macros are resolved semantically, not expanded textually
- `varying.def.sc` integration is not yet connected (types default to `vec4`)

## Experimental

This extension is experimental. Expect false positives on bgfx-specific preprocessor directives and macros. Report issues at [GitHub](https://github.com/r0ckHopper/bgfx_shader_analyzer-vscode/issues).
