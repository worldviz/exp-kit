---
description: Execute the VR experiment implementation planning workflow to generate design artifacts.
scripts:
  sh: scripts/bash/setup-plan.sh --json
  ps: scripts/powershell/setup-plan.ps1 -Json
---

Given the VR implementation details provided as an argument, do this:

1. Run `{SCRIPT}` from the repo root and parse JSON for EXPERIMENT_SPEC, IMPL_PLAN, SPECS_DIR, BRANCH. All future file paths must be absolute.
2. Read and analyze the experiment specification to understand:
   - Research questions and hypotheses
   - Experimental design (IVs, DVs, conditions)
   - Participant requirements and sample size
   - Materials and stimuli requirements
   - Procedure and data collection plan
   - Statistical analysis approach

3. Read the constitution at `/memory/constitution.md` to understand experimental best practices.

4. Execute the implementation plan template for VR experiments:
   - Load `/templates/plan-template.md` (already copied to IMPL_PLAN path)
   - Set Input path to EXPERIMENT_SPEC
   - Configure for Vizard 7 + Sightlab 2.0 platform
   - Run the Execution Flow (main) function steps 1-8
   - Follow experimental psychology gates and checks
   - Generate VR-specific artifacts in $SPECS_DIR:
     * Phase 0: research.md (literature review, paradigm selection)
     * Phase 1: protocols/, stimuli/, analysis-plan.md, quickstart.md
   - Consider VR-specific factors from arguments: {ARGS}
     * Hardware requirements (HMD model, tracking)
     * Cybersickness mitigation
     * Calibration procedures
     * Presence and immersion factors
   - Update Progress Tracking as you complete each phase

5. Verify experimental rigor:
   - Check power analysis adequacy
   - Ensure randomization/counterbalancing planned
   - Confirm IRB compliance considerations
   - Validate pilot testing protocol

6. Report results with branch name, file paths, and readiness for task generation.

Focus on creating a reproducible, scientifically rigorous VR experiment implementation.
