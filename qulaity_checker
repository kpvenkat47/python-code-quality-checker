"""
Python Code Quality Checker
============================
CLI tool to run black, isort, flake8, pylint, and mypy
on any Python file in one command.

Usage:
    python quality_checker.py your_script.py

Author: Pitchaiah Venkat K
"""

import os
import sys
import subprocess
import time


def run_command(command: str) -> int:
    """Run a shell command, print output, and return exit code."""
    print(f"\n{'='*50}")
    print(f"RUNNING : {command}")
    print('='*50)

    start = time.perf_counter()
    result = subprocess.run(
        command,
        shell=True,
        capture_output=True,
        text=True,
        check=False
    )
    elapsed = time.perf_counter() - start

    if result.stdout:
        print(result.stdout)
    if result.stderr:
        print(result.stderr)

    status = "PASS" if result.returncode == 0 else "FAIL"
    print(f"{status} | Time: {elapsed:.2f}s")

    return result.returncode


def main() -> None:
    """Entry point — validate input and run all quality checks."""
    if len(sys.argv) < 2:
        print("Please provide the Python file to check.")
        print("Usage: python quality_checker.py your_script.py")
        sys.exit(1)

    file_to_check = sys.argv[1]

    if not os.path.isfile(file_to_check):
        print(f"File not found: {file_to_check}")
        sys.exit(1)

    print(f"\n Running quality checks on: {file_to_check}\n")

    commands = {
        "isort":  f"isort {file_to_check}",
        "black":  f"black {file_to_check}",
        "flake8": f"flake8 {file_to_check}",
        "pylint": f"pylint {file_to_check}",
        "mypy":   f"mypy {file_to_check}",
    }

    results: dict[str, int] = {}
    for tool, cmd in commands.items():
        results[tool] = run_command(cmd)

    # Summary
    print(f"\n{'='*50}")
    print(" SUMMARY")
    print('='*50)
    all_passed = True
    for tool, code in results.items():
        icon = "PASS" if code == 0 else "FAIL"
        print(f"  {icon}  {tool}")
        if code != 0:
            all_passed = False

    print()
    if all_passed:
        print("ALL CHECKS PASSED — code is clean!")
    else:
        print("Some checks failed — review the output above.")
    print('='*50)


if __name__ == "__main__":
    main()


# ─── TOOL REFERENCE ───────────────────────────────────
# isort   → Sorts and organizes your imports automatically
# black   → Formats code style consistently (PEP 8)
# flake8  → Checks PEP 8 style + basic errors (doesn't fix)
# pylint  → Deep code inspector — errors, warnings, suggestions
# mypy    → Type checker — validates your type hints/annotations
#
# Formatters (black, isort) → change your code automatically
# Linters (flake8, pylint)  → report issues, don't change code
# Type checker (mypy)       → validates type hints only
