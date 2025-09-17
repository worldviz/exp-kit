---
description: Create or update the experiment specification from a research question or hypothesis.
scripts:
  sh: scripts/bash/create-new-experiment.sh --json "{ARGS}"
  ps: scripts/powershell/create-new-experiment.ps1 -Json "{ARGS}"
---

Given the research question or hypothesis provided as an argument, do this:

1. Run the script `{SCRIPT}` from repo root and parse its JSON output for BRANCH_NAME and SPEC_FILE. All file paths must be absolute.
2. Load `templates/spec-template.md` to understand required experimental design sections.
3. Write the specification to SPEC_FILE using the template structure, focusing on:
   - Research questions and hypotheses (must be testable and falsifiable)
   - Experimental design (IVs, DVs, controls, confounds)
   - Participant requirements and power analysis
   - Materials and stimuli needed for VR presentation
   - Detailed procedure and timeline
   - Data collection and analysis plan
   - Ethics and safety considerations
4. Mark any ambiguous aspects with [NEEDS CLARIFICATION: specific question]
5. Apply experimental psychology best practices:
   - Ensure adequate statistical power
   - Control for confounding variables
   - Plan for randomization/counterbalancing
   - Consider VR-specific factors (cybersickness, presence, immersion)
6. Report completion with branch name, spec file path, and readiness for implementation planning.

Note: The script creates and checks out the new branch and initializes the spec file before writing.
Focus on scientific rigor and reproducibility throughout the specification.
