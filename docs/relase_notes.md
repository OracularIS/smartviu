# SmartViu Release Updates

1. Version 1.0 – Core Launch
2. Version 1.0.1 – Hotfix: Export Functionality
3. Version 2.0 – React Refactor & Performance Enhancements

## Version 1.0 – Core Launch

**Date:** 23rd April, 2025

### Summary
Initial rollout of SmartViu, delivering the core reporting engine and foundational UI components.

### Key Features

- Configurable reports with filters, actions, and data visualizations
- Role-based access controls
- Integration with backend Smart IS systems
- Fully interactive SmartViu screens for WMS users

This version laid the groundwork for all future enhancements.

## Version 1.0.1 – Hotfix: Export Functionality

**Date:** 18th July, 2025

### Summary 

Resolved a CSV export issue where special characters caused formatting problems.

### Fixes

- Exported CSV files now handle special characters in column names and data values correctly
- No impact to other modules; hotfix deployable without db load

**Note:**
This fix was safely applied without requiring a db load or affecting any customizations in live environments.

## Version 2.0 – Code Refactor & smart-is.ai Dependency Removal

**Date:** 1st August,2025

### Summary

This release focuses on backend optimization and codebase simplification. SmartViu has undergone a structural upgrade to improve performance and maintainability by refactoring core logic and removing unnecessary dependencies.

### Improvements

- Major codebase refactoring to improve maintainability and performance
- Removed dependency on Smart-is.ai for a cleaner and more independent architecture
- Reduced external dependency footprint
- Foundation set for smoother scaling and future development

This release maintains full backward compatibility while bringing modern UI standards to the SmartViu platform.