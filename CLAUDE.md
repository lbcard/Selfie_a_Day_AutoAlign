# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Python-based tool for processing "Selfie a Day" photo collections. The project automatically prepares and aligns facial photos for timelapse video creation.

**Current State**: Early development - main functionality is partially implemented but incomplete.

## Architecture

The project consists of three main Python modules:

1. **fileprepper.py** - Handles EXIF-based file renaming and organization
   - Extracts DateTimeOriginal from EXIF metadata 
   - Renames files with date-based naming convention (YYYY-MM-DD_HH-MM-SS.jpg)
   - Moves processed files to a `renamed/` subdirectory

2. **facealigner.py** - Placeholder for facial alignment using OpenCV
   - Will detect eyes and align images to consistent coordinates
   - Will handle scaling and cropping for uniform output

3. **Selfie_a_Day_AutoAlign.py** - Main entry point (currently placeholder)
   - Will orchestrate the full processing pipeline

## Core Processing Logic

- **One photo per day**: When multiple photos exist for the same day, select the best one (focus-based selection)
- **Metadata-driven**: EXIF DateTimeOriginal is the source of truth, not filenames
- **Late night handling**: Photos taken in early morning hours may belong to the previous day if that day is missing photos
- **Color normalization**: Balance lighting and colors across different shooting conditions
- **Non-destructive**: Always work on copies, preserve originals

## Dependencies

The project uses:
- PIL (Python Imaging Library) for image processing and EXIF data extraction
- OpenCV (planned) for facial detection and alignment
- Standard library modules: os

## Development Commands

This is a pure Python project with no build system configured. Run files directly:

```bash
python fileprepper.py
python facealigner.py
python Selfie_a_Day_AutoAlign.py
```

Install dependencies manually as needed:
```bash
pip install Pillow opencv-python
```

## Planned Features

- Recursive folder processing
- JSON configuration file for output video settings
- Multiple output format generation in single run
- Date overlay on video frames
- JSON summary report with processing statistics
- Video encoding capabilities