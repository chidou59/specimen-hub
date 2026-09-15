# Architecture

## Overview

`specimen-hub` is a local-first PySide6 application for organizing experimental projects, specimens, observations, images, and mechanical-test data.

## Layering

```text
PySide6 views
  -> file/data controller
  -> project and specimen models
  -> JSON/files in a user-selected data root

Imported CSV/Excel/images
  -> import and image helpers
  -> mechanical analysis
  -> chart and comparison views
```

## Packages

- `main.py`: application bootstrap and global Qt styling.
- `config.py`: resource paths and the user's selected data root.
- `src/views/`: main window, project/sample views, dialogs, and charts.
- `src/controllers/file_manager.py`: persistence operations and file organization.
- `src/models/`: project and specimen domain structures.
- `src/utils/data_importer.py`: tabular data ingestion.
- `src/utils/mechanical_analysis.py`: derived mechanical metrics.
- `src/utils/image_helper.py`: image loading and conversion.
- `src/utils/template_manager.py`: reusable sample templates.

## Data boundary

User experiments live outside the source tree in the selected data root. The repository contains application code and documentation, never a user's project database or experimental attachments.
