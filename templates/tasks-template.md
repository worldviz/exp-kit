# Tasks: [EXPERIMENT NAME]

**Input**: Design documents from `/specs/[###-experiment-name]/`
**Prerequisites**: plan.md (required), research.md, protocols/, stimuli/, analysis-plan.md

## Execution Flow (main)
```
1. Load plan.md from experiment directory
   → If not found: ERROR "No implementation plan found"
   → Extract: VR platform (Vizard/Sightlab), dependencies
2. Load optional design documents:
   → stimuli/: Extract 3D assets → asset preparation tasks
   → protocols/: Each protocol → implementation task
   → analysis-plan.md: Extract analyses → script tasks
3. Generate tasks by category:
   → Setup: Vizard environment, Sightlab config
   → Stimuli: 3D models, textures, environments
   → Core: Trial logic, randomization, data logging
   → Testing: Pilot protocol, validation checks
   → Analysis: Preprocessing, statistics, visualization
4. Apply task rules:
   → Different modules = mark [P] for parallel
   → Same file = sequential (no [P])
   → Hardware before software
   → Stimuli before trials
5. Number tasks sequentially (T001, T002...)
6. Generate dependency graph
7. Create parallel execution examples
8. Validate task completeness:
   → All stimuli have loading tasks?
   → All protocols implemented?
   → All measures collected?
9. Return: SUCCESS (tasks ready for execution)
```

## Format: `[ID] [P?] Description`
- **[P]**: Can run in parallel (different files, no dependencies)
- Include exact file paths in descriptions

## Path Conventions
- **Experiment code**: `src/experiment/`, `src/stimuli/`, `src/tracking/`
- **Analysis code**: `src/analysis/`
- **Test code**: `tests/unit/`, `tests/integration/`, `tests/pilot/`
- **Data**: `data/raw/`, `data/processed/` (git-ignored)

## Phase 3.1: Environment Setup
- [ ] T001 Install Vizard 7 and verify license activation
- [ ] T002 Install Sightlab 2.0 and configure for experiment type
- [ ] T003 [P] Set up Python virtual environment with dependencies
- [ ] T004 [P] Configure VR hardware (HMD, trackers, controllers)
- [ ] T005 Test VR tracking space and boundaries

## Phase 3.2: Stimulus Preparation
- [ ] T006 [P] Create/import 3D models in src/stimuli/assets/models/
- [ ] T007 [P] Design textures/materials in src/stimuli/assets/textures/
- [ ] T008 [P] Build virtual environment in src/stimuli/assets/environments/
- [ ] T009 Implement stimulus loader in src/stimuli/loader.py
- [ ] T010 Create stimulus generator for dynamic content in src/stimuli/generator.py
- [ ] T011 Test stimulus presentation timing and rendering

## Phase 3.3: Core Experiment Implementation
- [ ] T012 Define experiment configuration in src/experiment/config.py
- [ ] T013 Implement trial logic in src/experiment/trials.py
- [ ] T014 Create main experiment loop in src/experiment/main.py
- [ ] T015 [P] Implement randomization/counterbalancing
- [ ] T016 [P] Add instruction screens and participant prompts
- [ ] T017 Create practice trial sequence
- [ ] T018 Implement break/pause functionality

## Phase 3.4: Tracking & Data Collection
- [ ] T019 [P] Set up eye tracking in src/tracking/eye_tracker.py
- [ ] T020 [P] Configure motion tracking in src/tracking/motion.py
- [ ] T021 [P] Implement physiological monitoring in src/tracking/physio.py (if applicable)
- [ ] T022 Create data logger in src/data/logger.py
- [ ] T023 Implement real-time validation in src/data/validator.py
- [ ] T024 Add data export functionality in src/data/export.py
- [ ] T025 Test data integrity and backup procedures

## Phase 3.5: Calibration & Quality Control
- [ ] T026 Create eye tracking calibration routine
- [ ] T027 Implement position tracking verification
- [ ] T028 Add participant comfort checks (IPD, height adjustment)
- [ ] T029 Create pre-experiment hardware tests
- [ ] T030 Implement cybersickness monitoring

## Phase 3.6: Pilot Testing Protocol
- [ ] T031 Create pilot participant consent forms
- [ ] T032 Run pilot test with 3 lab members
- [ ] T033 Analyze pilot data for timing issues
- [ ] T034 Check data completeness and quality
- [ ] T035 Refine based on pilot feedback
- [ ] T036 Document known issues and solutions

## Phase 3.7: Analysis Pipeline
- [ ] T037 [P] Implement data preprocessing in src/analysis/preprocess.py
- [ ] T038 [P] Create statistical tests in src/analysis/statistics.py
- [ ] T039 [P] Build visualization scripts in src/analysis/visualize.py
- [ ] T040 Generate power analysis validation
- [ ] T041 Create automated analysis report template
- [ ] T042 Test analysis pipeline with simulated data

## Phase 3.8: Documentation & Deployment
- [ ] T043 [P] Write participant instruction guide
- [ ] T044 [P] Create experimenter protocol document
- [ ] T045 [P] Document troubleshooting procedures
- [ ] T046 Prepare IRB submission materials
- [ ] T047 Set up data backup and versioning
- [ ] T048 Create experiment preregistration

## Dependencies
- Environment (T001-T005) before all implementation
- Stimuli (T006-T011) before trials (T012-T018)
- Core implementation before tracking (T019-T025)
- Calibration (T026-T030) requires tracking
- Pilot testing (T031-T036) requires full implementation
- Analysis (T037-T042) can parallel documentation (T043-T048)

## Parallel Example
```
# Launch T006-T008 together (different asset types):
Task: "Create 3D models in src/stimuli/assets/models/"
Task: "Design textures in src/stimuli/assets/textures/"
Task: "Build environment in src/stimuli/assets/environments/"

# Launch T037-T039 together (independent analysis scripts):
Task: "Implement preprocessing in src/analysis/preprocess.py"
Task: "Create statistical tests in src/analysis/statistics.py"
Task: "Build visualizations in src/analysis/visualize.py"
```

## Notes
- [P] tasks = independent modules, no shared dependencies
- Test each component before integration
- Maintain experiment log for issues/solutions
- Version control all configuration changes

## Task Generation Rules
*Applied during main() execution*

1. **From Stimuli Specs**:
   - Each stimulus type → preparation task [P]
   - Complex stimuli → generator implementation

2. **From Protocols**:
   - Each protocol phase → implementation task
   - Contingencies → error handling tasks

3. **From Analysis Plan**:
   - Each statistical test → analysis task [P]
   - Each figure → visualization task [P]

4. **Ordering**:
   - Hardware → Software → Stimuli → Logic → Testing → Analysis
   - Respect Vizard/Sightlab dependencies

## Validation Checklist
*GATE: Checked by main() before returning*

- [ ] All stimuli have preparation tasks
- [ ] All protocols have implementation tasks
- [ ] All measures have collection tasks
- [ ] Pilot testing included before full deployment
- [ ] Each task specifies exact file path
- [ ] Parallel tasks truly independent
- [ ] Vizard/Sightlab compatibility verified