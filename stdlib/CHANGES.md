# SysML Standard Library - Hokyo Modifications

Based on SysML-v2-Release commit 834a3daf073b1886244833d9341677eb9733d1e4 (January 8th, 2026)

## Changes

### 2026-01-08

- Flattened all standard libraries into the main stdlib folder
- Removed .meta.json and .project.json (these are ignored by our compiler anyway)
- Used simpler names for each library

### 2026-01-24

- kermlFunction/VectorFunctions.kerml incorrectly tries to import all ScalarFunctions. These ScalarFunctions collide with the defined members. The import was removed.

### 2026-01-29

- kerml/Occurrences.kerml InsideOf tries to redefine source and target which were already redefined by SpaceLink to be sourceOccurrence and targetOccurrence. Updated redefinition targets to match the names on SpaceLink which InsideOf directly inherits from. This may be reverted later if redefinition rules are updated to allow access to member by both provided name and name that is redefined.

### 2026-01-31

- kerml/Observation.kerml ChangeMonitor::AssignObservations attempts to redefine `observations` in nested feature startingAt. `observations` is a feature on ChangeMonitor, but not on startingAt. It has been commented out and removed.
- kerml/FeatureReferencingPerformances.kerml FeatureMonitorPerformance attempts to redefine local variable `monitoredFeature` but it is not inherited. Per spec (KerML 7.3.4.5), owned redefinitions must target features that would have been inherited on the owning type, but monitoredFeature is not inherited. Moved `beforeTimeSlice` and `afterSnapshot` out of monitoredOccurrence and update specializations to include monitoredFeature.
