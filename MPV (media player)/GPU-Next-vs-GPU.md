This page documents the known differences between `vo_gpu_next` and `vo_gpu` (that is, between `--vo=gpu-next` and `--vo=gpu`).

### Known limitations / missing options

There is currently no support for the libmpv / render API in `vo_gpu_next`.

#### Known issues

- https://github.com/mpv-player/mpv/labels/vo%3Agpu-next
- `--dscale-antiring` is not applied currently when using an orthogonal filter for quality reasons

#### Deliberate omissions

- `--sharpen`: Very low quality and easily replaced by (better) custom shaders (#9387, #9845)
- `ewa_lanczossoft`, `haasnsoft`: These were arbitrary filters to begin with and are easily replicated by tuning `ewa_lanczos`
- `--vf=format:light=...`: OOTFs are tied to the EOTF in `gpu-next`, and can no longer be adjusted independently
- `--gamma-factor` and `--gamma-auto`: considered deprecated by design, the new BPC logic handles this much better
- `--fbo-format`: libplacebo requires the use of floating point buffers (to store unnormalized linear light data), and there is no quality gain from going above rgba16f
- `--blend-subtitles=video`: libplacebo always renders subtitles during the final output pass, and never blends them directly onto video frames.
- `--tone-mapping-max-boost`: crutch for bad tone-mapping functions and lack of black point handling

### Differences in behavior

#### General differences

- `gpu-next` should be generally faster across the board, owing to refactors and rewrites of many key algorithms (EWA scaling, frame interpolation, color management, PRNG/debanding, etc.)
- `gpu-next` aggressively merges shader passes wherever possible, leading to a significant reduction in the number of full-screen draw calls required per frame; in addition to this it also more aggressively reuses internal frame caches
- `gpu-next`, unlike `gpu`, performs black point compensation during color management, leading to subtly different results for many of the tone mapping-related options
- `gpu-next` generally defaults to `bt.1886` instead of `gamma2.2` for the display output, due to the better/different black point handling
- `gpu-next` doesn't rotate/flip frames until the final output pass, whereas `gpu` applied this during the main scaling pass. This generally makes it more robust when combining custom user shaders with rotated videos

#### Differences in option behavior

- `ewa_lanczos` defaults to using radius 3.2383... in `gpu-next`, rather than the radius 3.0 of `gpu`.
- `--tone-mapping=auto`: picks `spline` (instead of `bt.2390`)
- `--tone-mapping=gamma`: scaling of the parameter has been changed slightly
- `--tone-mapping=bt.2390`: knee point is now tunable, defaulting to 1.0 instead of the hard-coded 0.50 from `gpu`
- `--tone-mapping=linear`: is now perceptually linear instead of linear light, use `linearlight` to get the old behavior back
- `--gamut-mapping-mode=auto`: picks `perceptual` instead of `clip`
- `--hdr-compute-peak`: `gpu-next` generally uses frame-exact results, rather than delaying detected peaks by a frame
- `--scale` can now be used directly on window functions, removing the need for `--scale-window` + `--scale=box` combo; in addition, a few new functions and presets are available while others have been removed

#### Custom shader support

- `TEXTURE_rot` is no longer needed (it still exists for compatibility, but it's defined as an identity matrix)
- The distinction between `MAIN` and `MAINPRESUB` no longer exists - either name can be used to refer to the same texture

### New features only supported by GPU Next

#### New functionality

- Support for Dolby Vision content (reshaping only)
- Support for GPU film grain application (AV1, H.274), see `--vd-lavc-film-grain`
- Significantly better dynamic tone mapping, and colorimetrically accurate gamut mapping

#### New options
- `--interpolation-preserve`
- `--lut`, `--image-lut`, `--target-lut`
- `--gamut-mapping-mode`: most gamut mapping modes
- `--target-contrast`
- `--target-colorspace-hint`: cross-platform HDR passthrough, with metadata forwarding and automatic tone-mapping
- `--tone-mapping=bt.2446a`
- `--tone-mapping=spline`
- `--tone-mapping=st2094-40`, `--tone-mapping=st2094-10`: HDR10+ and DV tone mapping curves
- `--tone-mapping-visualize`
- `--tone-mapping-param` for `--tone-mapping=bt.2390`
- `--inverse-tone-mapping`
- `--allow-delayed-peak-detect`
- `--hdr-peak-percentile`
- `--hdr-contrast-recovery`, `--hdr-contrast-smoothness`
- `--vd-lavc-film-grain=gpu/auto`
- `--glsl-shader-opts`
- `--corner-rounding`
- `--icc-use-luma`
- `--libplacebo-opts`
- `--hwdec=vulkan`

#### Custom shader support
- Support for custom, runtime-tunable shader parameters has been added
- Two new macros `linearize` and `delinearize` are available in all shader stages, resolving to GLSL functions for going back and forth between the video's native color space and linear light