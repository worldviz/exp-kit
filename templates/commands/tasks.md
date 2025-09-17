---
description: Generate actionable, dependency-ordered tasks.md for VR experiment development based on design artifacts.
scripts:
  sh: scripts/bash/check-task-prerequisites.sh --json
  ps: scripts/powershell/check-task-prerequisites.ps1 -Json
---

Given the VR experiment context provided as an argument, do this:

1. Run `{SCRIPT}` from repo root and parse EXPERIMENT_DIR and AVAILABLE_DOCS list. All paths must be absolute.
2. Load and analyze available design documents:
   - Always read plan.md for Vizard/Sightlab configuration
   - IF EXISTS: Read protocols/ for experimental procedures
   - IF EXISTS: Read stimuli/ for 3D asset requirements
   - IF EXISTS: Read research.md for paradigm decisions
   - IF EXISTS: Read analysis-plan.md for statistical tests
   - IF EXISTS: Read quickstart.md for pilot protocol

3. Generate VR experiment tasks following the template:
   - Use `/templates/tasks-template.md` as the base
   - Create tasks specific to VR experiment development:
     * **Environment Setup**: Vizard/Sightlab install, VR hardware config
     * **Stimulus Preparation [P]**: 3D models, textures, environments
     * **Core Implementation**: Trial logic, randomization, data logging
     * **Tracking Setup [P]**: Eye tracking, motion capture, physio
     * **Calibration**: Per-participant calibration routines
     * **Pilot Testing**: Run pilots, analyze data, refine
     * **Analysis Pipeline [P]**: Preprocessing, statistics, visualization
     * **Documentation [P]**: IRB materials, protocols, preregistration

4. VR-specific task generation rules:
   - Each stimulus type → asset preparation task [P]
   - Each protocol phase → implementation task
   - Each tracking modality → setup task [P]
   - Each statistical test → analysis script [P]
   - Hardware setup must precede software
   - Calibration requires tracking to be ready

5. Order tasks by experimental workflow:
   - Hardware setup before software
   - Stimuli before trial implementation
   - Core experiment before tracking integration
   - Full implementation before pilot testing
   - Pilot testing before full data collection
   - Data collection before analysis

6. Include VR-specific considerations from {ARGS}:
   - Cybersickness mitigation checkpoints
   - Frame rate optimization tasks
   - Presence/immersion validation
   - Equipment sanitization protocols

7. Create EXPERIMENT_DIR/tasks.md with:
   - Experiment name from implementation plan
   - Numbered tasks (T001-T048 typical range)
   - Vizard/Sightlab specific file paths
   - VR hardware dependencies noted
   - Pilot-test-refine cycle explicit

Each task must be specific to VR experimental psychology, executable by someone familiar with Vizard/Sightlab.
