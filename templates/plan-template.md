---
description: "Implementation plan template for VR experiment development"
scripts:
  sh: scripts/bash/update-agent-context.sh __AGENT__
  ps: scripts/powershell/update-agent-context.ps1 -AgentType __AGENT__
---

# Implementation Plan: [EXPERIMENT]

**Branch**: `[###-experiment-name]` | **Date**: [DATE] | **Spec**: [link]
**Input**: Experiment specification from `/specs/[###-experiment-name]/spec.md`

## Execution Flow (/plan command scope)
```
1. Load experiment spec from Input path
   → If not found: ERROR "No experiment spec at {path}"
2. Fill Technical Context (scan for NEEDS CLARIFICATION)
   → Set VR Platform: Vizard + Sightlab
   → Detect Experiment Type (behavioral, psychophysics, social)
   → Set Structure Decision based on experiment type
3. Fill the Constitution Check section based on experimental best practices
4. Evaluate Constitution Check section
   → If violations exist: Document in Complexity Tracking
   → If no justification possible: ERROR "Simplify design first"
   → Update Progress Tracking: Initial Constitution Check
5. Execute Phase 0 → research.md (literature review, paradigm selection)
   → If NEEDS CLARIFICATION remain: ERROR "Resolve design questions"
6. Execute Phase 1 → stimuli/, protocols/, analysis-plan.md, quickstart.md
7. Re-evaluate Constitution Check
   → If new violations: Refactor design, return to Phase 1
   → Update Progress Tracking: Post-Design Constitution Check
8. Plan Phase 2 → Describe task generation approach (DO NOT create tasks.md)
9. STOP - Ready for /tasks command
```

**IMPORTANT**: The /plan command STOPS at step 8. Phase 2 is executed by /tasks command.

## Summary
[Extract from experiment spec: primary hypothesis + experimental approach from research]

## Technical Context
**VR Platform**: Vizard 7 + Sightlab 2.0
**Python Version**: 3.11+ (Vizard compatible)
**Primary Dependencies**: vizard, sightlab, numpy, pandas, scipy
**Data Storage**: [CSV/HDF5/SQLite or NEEDS CLARIFICATION]
**Analysis Tools**: [R/Python/JASP or NEEDS CLARIFICATION]
**VR Hardware**: [HMD model, tracking system or NEEDS CLARIFICATION]
**Experiment Type**: [behavioral/psychophysics/social/cognitive]
**Trial Structure**: [blocks × trials or NEEDS CLARIFICATION]
**Session Duration**: [minutes or NEEDS CLARIFICATION]
**Sample Size**: [N participants or NEEDS CLARIFICATION]

## Constitution Check
*GATE: Must pass experimental best practices before Phase 0*

### Scientific Integrity
- [ ] **Preregistration Ready**: Hypotheses, design, analysis plan locked
- [ ] **Power Adequate**: Sample size justified by power analysis
- [ ] **Validity Ensured**: Internal, external, construct validity addressed
- [ ] **Replicable**: Protocol sufficiently detailed for replication

### Ethical Standards
- [ ] **IRB Compliant**: Protocol aligns with ethics approval
- [ ] **Participant Safety**: VR comfort, breaks, stopping rules defined
- [ ] **Data Protection**: GDPR/HIPAA compliant storage and handling
- [ ] **Informed Consent**: Clear, comprehensive consent procedures

### Technical Rigor
- [ ] **Randomization**: Proper randomization/counterbalancing implemented
- [ ] **Timing Precision**: Frame-accurate presentation and response recording
- [ ] **Calibration**: Eye tracking, position tracking calibrated per participant
- [ ] **Data Quality**: Validation checks, outlier detection automated

## Project Structure

### Documentation (this experiment)
```
specs/[###-experiment]/
├── plan.md              # This file (/plan command output)
├── research.md          # Phase 0: Literature review, paradigm selection
├── protocols/           # Phase 1: Detailed experimental procedures
│   ├── main-task.md
│   ├── practice.md
│   └── calibration.md
├── stimuli/             # Phase 1: Stimulus specifications
│   ├── visual/
│   ├── audio/
│   └── environments/
├── analysis-plan.md     # Phase 1: Statistical analysis pipeline
├── quickstart.md        # Phase 1: Pilot testing protocol
└── tasks.md             # Phase 2: Development tasks (/tasks command)
```

### Source Code (repository root)
```
# VR Experiment Structure
src/
├── experiment/
│   ├── __init__.py
│   ├── config.py        # Experiment parameters
│   ├── main.py          # Main experiment loop
│   └── trials.py        # Trial logic
├── stimuli/
│   ├── loader.py        # Stimulus loading/caching
│   ├── generator.py     # Dynamic stimulus generation
│   └── assets/          # 3D models, textures
├── tracking/
│   ├── eye_tracker.py   # Eye tracking integration
│   ├── motion.py        # Motion capture
│   └── physio.py        # Physiological measures
├── data/
│   ├── logger.py        # Data collection
│   ├── validator.py     # Real-time validation
│   └── export.py        # Data export formats
└── analysis/
    ├── preprocess.py    # Data cleaning
    ├── statistics.py    # Statistical tests
    └── visualize.py     # Plots and figures

tests/
├── unit/                # Component tests
├── integration/         # System tests
└── pilot/               # Pilot participant data

data/                    # Experimental data (git-ignored)
├── raw/
├── processed/
└── figures/
```

**Structure Decision**: [Based on experiment type from Technical Context]

## Phase 0: Literature & Paradigm Research
1. **Review prior VR experiments** in domain:
   - Search for: "{construct} VR experiment"
   - Search for: "{paradigm} virtual reality"
   - Extract: Effect sizes, sample sizes, procedures

2. **Paradigm selection** based on:
   - Ecological validity vs. experimental control
   - VR affordances (3D space, embodiment, presence)
   - Participant comfort and cybersickness

3. **Technical feasibility** research:
   - Vizard/Sightlab examples for paradigm
   - Required tracking precision
   - Stimulus presentation timing

**Output**: research.md with paradigm justification and technical approach

## Phase 1: Experiment Design & Protocols
*Prerequisites: research.md complete*

1. **Generate stimulus specifications** → `stimuli/`:
   - 3D model requirements
   - Texture/material properties
   - Animation parameters
   - Environmental layout

2. **Create detailed protocols** → `protocols/`:
   - Instruction scripts
   - Practice trial sequence
   - Main experiment flow
   - Contingency procedures

3. **Design data structures** → `analysis-plan.md`:
   - Variable naming conventions
   - Data validation rules
   - Statistical test specifications
   - Figure generation plans

4. **Pilot testing protocol** → `quickstart.md`:
   - Setup checklist
   - Calibration procedures
   - Test run instructions
   - Troubleshooting guide

5. **Update agent file** (if applicable):
   - Add Vizard/Sightlab context
   - Include experiment-specific guidance
   - Update with recent design decisions

**Output**: stimuli/, protocols/, analysis-plan.md, quickstart.md

## Phase 2: Task Planning Approach
*This section describes what /tasks command will do - DO NOT execute during /plan*

**Task Generation Strategy**:
- Environment setup tasks (VR scene, lighting)
- Stimulus preparation tasks (3D assets, materials)
- Core experiment logic (trial control, randomization)
- Data collection implementation
- Pilot testing tasks
- Analysis script development

**Ordering Strategy**:
- Hardware setup before software
- Stimuli before trial logic
- Core experiment before data collection
- Testing before analysis

**Estimated Output**: 30-40 numbered tasks in tasks.md

**IMPORTANT**: Phase 2 is executed by /tasks command, NOT by /plan

## Phase 3+: Future Implementation
*These phases are beyond the scope of the /plan command*

**Phase 3**: Task execution (development sprints)
**Phase 4**: Pilot testing (5-10 participants)
**Phase 5**: Refinement based on pilot data
**Phase 6**: Full data collection
**Phase 7**: Analysis and publication

## Complexity Tracking
*Fill ONLY if Constitution Check has violations that must be justified*

| Violation | Why Needed | Simpler Alternative Rejected Because |
|-----------|------------|-------------------------------------|
| [e.g., Complex randomization] | [counterbalancing need] | [would introduce confounds] |

## Progress Tracking
*This checklist is updated during execution flow*

**Phase Status**:
- [ ] Phase 0: Research complete (/plan command)
- [ ] Phase 1: Design complete (/plan command)
- [ ] Phase 2: Task planning complete (/plan command - describe approach only)
- [ ] Phase 3: Tasks generated (/tasks command)
- [ ] Phase 4-7: Implementation and data collection

**Gate Status**:
- [ ] Initial Constitution Check: PASS
- [ ] Post-Design Constitution Check: PASS
- [ ] All NEEDS CLARIFICATION resolved
- [ ] Complexity deviations documented

---
*Based on Experimental Psychology Best Practices - See `/memory/constitution.md`*