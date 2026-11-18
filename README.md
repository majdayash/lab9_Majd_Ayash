# Lab 9 – Profiling in Python (Majd Ayash)

Software Tools Lab – Fall 2026-2027

| Folder | Contents |
|---|---|
| `before_optimization/` | Original `profiler.py`, `profiler_lineprofiler.py`, `profiler_memoryprofiler.py`, `test_profiler.py`, raw tool outputs (`outputs/`), coverage HTML report (`htmlcov/index.html`) |
| `after_optimization/` | Same files with `fast_function` replaced by `optimized_fast_function` |
| `screenshots/` | Terminal screenshots of every tool, before and after optimization |
| `lab9_Majd_Ayash.docx` | Report with outputs, analysis and before/after comparison |

Optimization (as required by the lab): `fast_function`'s manual loop was replaced by `sum(i**2 for i in range(100))`. A timeit benchmark shows this is ~19% slower on Python 3.12 (see report, section 7.5).

## Run (inside either folder)
```bash
pip install line_profiler memory_profiler coverage
python -m cProfile -s time profiler.py
python profiler_lineprofiler.py
python -m memory_profiler profiler_memoryprofiler.py
coverage run -m unittest discover
coverage report -m
coverage html
```
