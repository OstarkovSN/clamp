# Fork notes

Fork of [ml-jku/clamp](https://github.com/ml-jku/clamp).

## Patches

1. Removed unused `import pkg_resources` from `setup.py`. Modern setuptools (≥70) no longer ships `pkg_resources` in the isolated build environment, which made `pip`/`uv` build-isolation fail with `ModuleNotFoundError: No module named 'pkg_resources'`. The import was unused in the original `setup.py`, so dropping it is safe.
2. Pinned the `clip` git dependency to `openai/CLIP@d05afc4` (post-#529), the first revision after OpenAI's own `pkg_resources` cleanup. The original unpinned `clip@git+...` resolved to a stale commit (`dcba3cb`) that fails to build under modern uv.

Used by [chembertoid](https://github.com/OstarkovSN/chembertoid) (CVPR 2026 paper codebase).
