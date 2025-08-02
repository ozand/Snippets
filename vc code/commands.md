0. удали выполненные блоки (не отдельные задачи, а есди выполнены все задачи в блоке)
1. актуализируй #sym:# Implementation Plan: excel2json Project:
- отметить выполненные
-  добавь если требуется новые задачи
2. Продолжи разработку в соответсвие с планом (не задавай вопросы, сразу приступай)


---
use mcp Sequential Thinking for "Try breaking down the task into smaller steps"


orchestrate subtasks in the appropriate modes sequentially



(logsec-kg) PS T:\Code\python\Tools\logsec_knowledge_graf> uv run ruff check . --fix && uv run ruff format . && uv run mypy && uv run pytest ; "(Roo/PS Workaround: 1)" > $null ; start-sleep -milliseconds 10
All checks passed!
13 files left unchanged
Success: no issues found in 10 source files
================================================================================= test session starts =================================================================================
platform win32 -- Python 3.13.3, pytest-8.4.1, pluggy-1.6.0
benchmark: 5.1.0 (defaults: timer=time.perf_counter disable_gc=False min_rounds=5 min_time=0.000005 max_time=1.0 calibration_precision=10 warmup=False warmup_iterations=100000)
rootdir: T:\Code\python\Tools\logsec_knowledge_graf
configfile: pyproject.toml
plugins: respx-0.22.0, anyio-4.8.0, dash-2.18.2, asyncio-0.23.5, benchmark-5.1.0, cov-6.0.0, mock-3.14.0, recording-0.13.2, timeout-2.3.1, xdist-3.6.1
asyncio: mode=Mode.STRICT
collected 5 items                                                                                                                                                                      

tests\test_converter.py ....                                                                                                                                                     [ 80%]
tests\test_db_manager.py .                                                                                                                                                       [100%]

================================================================================== 5 passed in 0.07s ================================================================================== 
(logsec-kg) PS T:\Code\python\Tools\logsec_knowledge_graf> uv run ruff check . --fix && uv run ruff format . && uv run mypy && uv run pytest ; "(Roo/PS Workaround: 1)" > $null ; start-