# Experiment Specification: [EXPERIMENT NAME]

**Experiment Branch**: `[###-experiment-name]`
**Created**: [DATE]
**Status**: Draft
**Input**: Research question: "$ARGUMENTS"

## Execution Flow (main)
```
1. Parse research question from Input
   → If empty: ERROR "No research question provided"
2. Extract key concepts from description
   → Identify: constructs, populations, contexts, measures
3. For each unclear aspect:
   → Mark with [NEEDS CLARIFICATION: specific question]
4. Fill Experimental Design section
   → If no clear hypothesis: ERROR "Cannot determine research hypothesis"
5. Generate Methodology
   → Each measure must be validated
   → Mark ambiguous procedures
6. Identify Data Requirements (sample size, measures)
7. Run Review Checklist
   → If any [NEEDS CLARIFICATION]: WARN "Design has uncertainties"
   → If ethics issues found: ERROR "Address ethical concerns"
8. Return: SUCCESS (experiment ready for planning)
```

---

## ⚡ Quick Guidelines
- ✅ Focus on WHAT you're testing and WHY (hypothesis-driven)
- ❌ Avoid implementation details (no VR specifics, code structure)
- 🧪 Written for research review, not developers
- 📊 Statistical power and validity are paramount

### Section Requirements
- **Mandatory sections**: Must be completed for every experiment
- **Optional sections**: Include only when relevant to the design
- When a section doesn't apply, remove it entirely (don't leave as "N/A")

### For AI Generation
When creating this spec from a research prompt:
1. **Mark all ambiguities**: Use [NEEDS CLARIFICATION: specific question] for any assumption
2. **Don't guess**: If the prompt doesn't specify something (e.g., "memory study" without paradigm), mark it
3. **Think like a reviewer**: Every vague hypothesis should fail the "testable and falsifiable" checklist
4. **Common underspecified areas**:
   - Effect sizes and power analysis
   - Inclusion/exclusion criteria
   - Randomization and counterbalancing
   - Control conditions
   - Confounding variables
   - Data quality checks

---

## Research Questions & Hypotheses *(mandatory)*

### Primary Research Question
[What specific question does this experiment answer?]

### Hypotheses
1. **H1**: [Primary hypothesis with predicted direction of effect]
2. **H2**: [Secondary hypothesis if applicable]
3. **H0**: [Null hypothesis to be tested against]

### Theoretical Framework
[Brief description of the theoretical background and prior findings]

## Experimental Design *(mandatory)*

### Design Type
- **Structure**: [e.g., 2x3 mixed factorial, within-subjects, between-groups]
- **Independent Variables**:
  - **IV1**: [Name] - Levels: [list levels] - Type: [within/between]
  - **IV2**: [Name] - Levels: [list levels] - Type: [within/between]
- **Dependent Variables**:
  - **DV1**: [Name] - Measure: [how measured] - Unit: [unit of measurement]
  - **DV2**: [Name] - Measure: [how measured] - Unit: [unit of measurement]
- **Control Variables**: [Variables held constant or measured for covariance]
- **Confounds to Address**: [Potential confounds and mitigation strategies]

### Randomization & Counterbalancing
- **Random Assignment**: [How participants are assigned to conditions]
- **Counterbalancing**: [Order effects and how they're controlled]
- **Blinding**: [Single-blind, double-blind, or open-label]

## Participants *(mandatory)*

### Sample Size
- **Target N**: [Total sample size]
- **Per Condition**: [N per experimental condition]
- **Power Analysis**: [NEEDS CLARIFICATION: effect size, alpha, power]
  - Effect size (d/f/r): [expected effect]
  - Alpha level: [typically 0.05]
  - Power: [typically 0.80]
  - Software used: [e.g., G*Power, R pwr package]

### Recruitment
- **Population**: [Target population description]
- **Recruitment Method**: [How participants will be recruited]
- **Compensation**: [Payment/credit amount and structure]

### Inclusion/Exclusion Criteria
**Include**:
- [Criterion 1, e.g., "Age 18-65"]
- [Criterion 2, e.g., "Normal or corrected vision"]

**Exclude**:
- [Criterion 1, e.g., "History of neurological disorders"]
- [Criterion 2, e.g., "VR sickness susceptibility"]

## Materials & Stimuli *(mandatory)*

### Experimental Stimuli
- **Stimulus Set 1**: [Description, number of items, properties]
- **Stimulus Set 2**: [Description, number of items, properties]
- **Presentation Parameters**: [Duration, ISI, randomization]

### Equipment Requirements
- **Display**: [VR headset model, resolution, field of view]
- **Tracking**: [Eye tracking, motion capture, physiological sensors]
- **Response Collection**: [Controllers, buttons, voice, etc.]
- **Environment**: [Physical space requirements, lighting conditions]

### Measures & Instruments
- **Primary Measure**: [Name, validation info, scoring method]
- **Secondary Measures**: [Questionnaires, scales, behavioral metrics]
- **Manipulation Checks**: [How to verify IVs were perceived as intended]

## Procedure *(mandatory)*

### Timeline
1. **Consent & Demographics** (X min)
2. **Pre-test Measures** (X min)
3. **Equipment Setup & Calibration** (X min)
4. **Practice Trials** (X trials, X min)
5. **Experimental Blocks** (X blocks × X trials, X min)
6. **Post-test Measures** (X min)
7. **Debrief** (X min)
**Total Duration**: [X minutes]

### Detailed Protocol
1. **Welcome & Consent**:
   - [Specific consent procedures]
   - [NEEDS CLARIFICATION: IRB protocol number?]

2. **Baseline/Calibration**:
   - [Equipment setup steps]
   - [Comfort adjustments]
   - [Calibration procedures]

3. **Instructions**:
   - [Exact instructions to participants]
   - [Comprehension checks]

4. **Trial Structure**:
   - [Detailed description of a single trial]
   - [Timing of each trial component]
   - [Response window and feedback]

5. **Breaks & Fatigue Management**:
   - [Rest period schedule]
   - [Cybersickness monitoring]

## Data Collection Plan *(mandatory)*

### Data Types
- **Behavioral**: [RT, accuracy, choices, paths, etc.]
- **Physiological**: [Eye tracking, EEG, HR, etc.]
- **Self-Report**: [Questionnaire responses, ratings]
- **Process Data**: [Time stamps, system events, calibration quality]

### Data Structure
- **Trial-Level Data**: [Variables recorded per trial]
- **Block-Level Data**: [Aggregate measures per block]
- **Session-Level Data**: [Summary statistics, metadata]

### Quality Assurance
- **Data Validation**: [Range checks, outlier detection]
- **Missing Data Plan**: [How to handle missing/invalid responses]
- **Backup Procedures**: [Data redundancy and recovery plans]

## Statistical Analysis Plan *(mandatory)*

### Primary Analyses
- **Test 1**: [Statistical test] for [hypothesis]
  - Assumptions to check: [list assumptions]
  - Effect size measure: [Cohen's d, η², etc.]
- **Test 2**: [Statistical test] for [hypothesis]

### Secondary Analyses
- **Exploratory**: [Planned exploratory analyses]
- **Covariates**: [Variables to include as covariates]

### Data Processing Pipeline
1. **Cleaning**: [Outlier criteria, exclusion rules]
2. **Transformation**: [Any data transformations needed]
3. **Aggregation**: [How trials are aggregated]
4. **Software**: [R, Python, SPSS, etc. with packages]

## Ethics & Safety *(mandatory)*

### Ethical Considerations
- **IRB Status**: [NEEDS CLARIFICATION: Approval number or pending]
- **Informed Consent**: [Key elements of consent]
- **Data Privacy**: [Anonymization, storage, sharing plan]
- **Risk Level**: [Minimal risk or greater than minimal]

### Safety Protocols
- **VR-Specific Risks**: [Cybersickness mitigation, break protocols]
- **Adverse Events**: [Monitoring and response procedures]
- **Stopping Rules**: [Criteria for pausing/stopping experiment]
- **Emergency Procedures**: [Contact info, escalation path]

---

## Review & Acceptance Checklist
*GATE: Must pass before implementation phase*

### Scientific Rigor
- [ ] Hypotheses are specific, testable, and falsifiable
- [ ] Power analysis completed with justified parameters
- [ ] Design controls for identified confounds
- [ ] Randomization/counterbalancing adequate
- [ ] Statistical plan aligns with hypotheses

### Feasibility
- [ ] Timeline realistic for recruitment goals
- [ ] Equipment and software requirements specified
- [ ] Budget and resources adequate
- [ ] Pilot testing planned

### Ethics & Compliance
- [ ] No [NEEDS CLARIFICATION] markers remain
- [ ] IRB approval obtained or application ready
- [ ] Data management plan compliant with regulations
- [ ] Participant safety protocols established

### Reproducibility
- [ ] Protocol sufficiently detailed for replication
- [ ] Stimuli and materials documented
- [ ] Analysis code plan specified
- [ ] Preregistration planned (OSF, AsPredicted)

---

## Execution Status
*Updated by main() during processing*

- [ ] Research question parsed
- [ ] Key concepts extracted
- [ ] Ambiguities marked
- [ ] Hypotheses defined
- [ ] Design specified
- [ ] Power analysis completed
- [ ] Procedure detailed
- [ ] Analysis plan created
- [ ] Ethics reviewed
- [ ] Checklist passed

---