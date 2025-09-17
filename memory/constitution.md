# ExpKit Experimental Psychology Constitution

## Core Principles

### I. Scientific Integrity (NON-NEGOTIABLE)
Every experiment must adhere to the scientific method with testable hypotheses, controlled variables, and falsifiable predictions. No exploratory fishing expeditions without explicit acknowledgment. Pre-registration of hypotheses and analysis plans is mandatory before data collection begins.

### II. Replicability First
All experimental protocols must be documented with sufficient detail for independent replication. This includes exact stimulus parameters, timing specifications, randomization seeds, and analysis code. Version control everything: stimuli, code, data, and analysis scripts.

### III. Statistical Rigor
Power analysis is mandatory before participant recruitment. Effect size estimates must be justified from pilot data or literature. Multiple comparisons require appropriate corrections. Report all analyses conducted, not just significant results.

### IV. Participant Welfare
Participant comfort and safety supersede all other experimental considerations. VR experiments must include:
- Cybersickness monitoring and mitigation protocols
- Regular breaks (minimum every 20 minutes)
- Clear stopping procedures participants can invoke at any time
- Post-experiment wellness checks

### V. Open Science Commitment
Default to open data, open materials, and open code unless restricted by IRB or participant privacy. Use standardized data formats (BIDS for neuroimaging, Psych-DS for behavioral). Preregister on OSF or AsPredicted. Share negative results.

### VI. VR-Specific Validity
Leverage VR's unique affordances (3D space, embodiment, presence) rather than replicating 2D paradigms. Validate that VR adds ecological validity or experimental control. Monitor and report presence/immersion metrics. Account for individual differences in VR experience.

### VII. Measurement Precision
Behavioral timing must be frame-accurate (not input-device limited). Eye tracking requires per-participant calibration verification. Motion tracking needs documented precision specifications. Physiological measures require noise assessment.

## Technical Standards

### Vizard/Sightlab Requirements
- Maintain 90Hz minimum frame rate for comfort
- Log frame drops and timing violations
- Implement predictive tracking for low latency
- Use Sightlab's built-in data validation
- Document all hardware specifications

### Data Quality Gates
- Real-time data validation during collection
- Automated outlier detection (but preserve raw data)
- Minimum 95% valid trial requirement
- Backup data streams (redundant logging)

### Code Standards
- Modular experiment structure (separate stimulus, trial, analysis)
- Configuration files for all parameters (no magic numbers)
- Comprehensive error handling and logging
- Unit tests for critical functions
- Comments explaining the "why" not just "what"

## Ethical Requirements

### IRB Compliance
- No data collection before IRB approval
- Informed consent must be genuinely informed (VR-specific risks explained)
- Vulnerable populations require additional safeguards
- Data de-identification from point of collection

### Data Protection
- GDPR/HIPAA compliance as applicable
- Separate linkage files from data
- Encryption for sensitive data at rest and in transit
- Clear data retention and deletion policies
- No behavioral data on cloud services without encryption

## Experimental Workflow

### Phase Gates (Must Pass Before Proceeding)
1. **Design Gate**: Power analysis complete, hypotheses preregistered
2. **Implementation Gate**: Pilot data validates timing and measures
3. **Collection Gate**: First 5 participants show data quality meets standards
4. **Analysis Gate**: Preregistered analyses run before exploratory
5. **Dissemination Gate**: All supplementary materials prepared for sharing

### Pilot Testing Requirements
- Minimum 5 pilot participants (not authors)
- Full protocol run including analysis pipeline
- Document and resolve all issues before main study
- Pilot data may not be included in main analysis

## Quality Checklists

### Pre-Experiment Checklist
- [ ] Hypotheses are specific and directional
- [ ] Power analysis completed with justification
- [ ] VR hardware tested and calibrated
- [ ] Cybersickness protocols in place
- [ ] Data quality checks automated
- [ ] Preregistration submitted

### Post-Experiment Checklist
- [ ] All preregistered analyses completed
- [ ] Exploratory analyses clearly labeled
- [ ] Data and materials prepared for sharing
- [ ] Participant feedback incorporated
- [ ] Equipment issues documented

## Governance

This constitution supersedes all other practices and cannot be overridden by expedience or convenience. Violations must be explicitly documented with justification and approval from PI/ethics board.

Amendments to this constitution require:
1. Documented rationale for change
2. Review of impact on ongoing studies
3. Version control with clear transition date
4. Communication to all team members

The constitution is enforced through:
- Automated checks in analysis pipelines
- Code review requirements
- Preregistration as external commitment
- Regular lab audits of compliance

**Version**: 1.0.0 | **Ratified**: 2024-01-17 | **Last Amended**: 2024-01-17

---

*For VR-specific experimental guidance, see Vizard/Sightlab documentation*
*For statistical standards, refer to APA or field-specific guidelines*