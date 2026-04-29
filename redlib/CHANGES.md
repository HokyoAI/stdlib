# SysML Reduced Standard Library - Hokyo Modifications

Based on SysML-v2-Release commit 834a3daf073b1886244833d9341677eb9733d1e4 (January 8th, 2026)

## Changes

### 2026-03-19

- Flattened all standard libraries into the main stdlib folder
- Removed .meta.json and .project.json (these are ignored by our compiler anyway)
- Used simpler names for each library
- Removed all libraries except for Base, Collections, and ScalarValues

### 2026-04-29

- Added back metadata libraries (except ParametersOfInterestMetadata)
- Removed annotation element redefinition for ModelingMetadata to keep redlib self contained.