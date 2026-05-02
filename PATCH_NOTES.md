# Fork notes

Fork of [ml-jku/clamp](https://github.com/ml-jku/clamp).

## Patch

Removed unused `import pkg_resources` from `setup.py`. Modern setuptools (≥70) no longer ships `pkg_resources` in the isolated build environment, which made `pip`/`uv` build-isolation fail with `ModuleNotFoundError: No module named 'pkg_resources'`. The import was unused in the original `setup.py`, so dropping it is safe.

Used by [chembertoid](https://github.com/OstarkovSN/chembertoid) (CVPR 2026 paper codebase).
