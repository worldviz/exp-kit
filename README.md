# ExpKit: Experimental Psychology VR Toolkit

**Build rigorous VR experiments with AI-assisted specification-driven development**

ExpKit is a specialized fork of [spec-kit](https://github.com/github/spec-kit) designed specifically for experimental psychologists building VR studies with [Vizard](https://www.worldviz.com/vizard) and [Sightlab](https://www.worldviz.com/sightlab). It provides AI-powered assistance for experimental design, implementation planning, and task management while maintaining scientific rigor and reproducibility.

## ✨ Features

- 🧪 **Experimental Design Templates** - Structured templates for hypotheses, IVs/DVs, power analysis, and protocols
- 🥽 **VR-Specific Planning** - Built for Vizard/Sightlab with cybersickness mitigation and calibration protocols
- 📊 **Statistical Rigor** - Enforces power analysis, preregistration, and proper randomization
- 🤖 **AI-Assisted Workflow** - Works with Claude, Copilot, Gemini, Cursor, or Qwen for intelligent assistance
- ✅ **Task Management** - Generates detailed implementation tasks specific to VR experiments
- 🔬 **Open Science Ready** - Encourages preregistration, data sharing, and reproducibility

## 🚀 Quick Start

### 1. Install ExpKit

```bash
uvx --from git+https://github.com/worldviz/exp-kit.git expkit init my-experiment
```

Or install in current directory:
```bash
uvx --from git+https://github.com/worldviz/exp-kit.git expkit init --here
```

### 2. Design Your Experiment

Use the **`/specify`** command to describe your research question and hypotheses:

```
/specify Investigate whether embodied perspective-taking in VR reduces implicit bias
compared to traditional perspective-taking exercises. Participants will either
embody an outgroup member in VR or watch a video from their perspective.
```

### 3. Plan VR Implementation

Use the **`/plan`** command to specify your VR setup and technical approach:

```
/plan The experiment uses Vizard 7 with Sightlab 2.0 for eye tracking.
We'll use a Meta Quest Pro for high-resolution eye tracking. Stimuli are
photorealistic avatars. Between-subjects design with n=60 (30 per condition).
```

### 4. Generate Development Tasks

Use **`/tasks`** to create an actionable task list for building your experiment:

```
/tasks Generate all tasks needed to implement this implicit bias VR study,
including IRB materials, pilot testing, and analysis scripts.
```

## 📋 Prerequisites

### Required Software
- Python 3.11+
- Git
- [uv](https://docs.astral.sh/uv/) for package management
- Your preferred AI coding assistant (Claude Code, GitHub Copilot, etc.)

### VR Development Stack
- [Vizard 7](https://www.worldviz.com/vizard) - VR development platform
- [Sightlab 2.0](https://www.worldviz.com/sightlab) - VR experiment framework
- Compatible VR hardware (Meta Quest, HTC Vive, etc.)

## 🔬 Experimental Workflow

ExpKit guides you through a rigorous experimental development process:

1. **Specification** (`/specify`) - Define hypotheses, design, and measures
2. **Planning** (`/plan`) - Create protocols, stimuli specs, and analysis plans
3. **Tasks** (`/tasks`) - Generate concrete implementation tasks
4. **Development** - Build experiment following generated tasks
5. **Pilot Testing** - Validate with 5-10 participants
6. **Refinement** - Address issues from pilot
7. **Data Collection** - Run full experiment
8. **Analysis** - Execute preregistered analyses

## 📚 Templates Structure

ExpKit provides specialized templates for experimental psychology:

```
templates/
├── spec-template.md       # Experimental design specification
├── plan-template.md       # VR implementation planning
├── tasks-template.md      # Development task generation
└── commands/
    ├── specify.md         # Research question → experiment spec
    ├── plan.md           # Spec → VR implementation plan
    └── tasks.md          # Plan → actionable tasks
```

## 🎯 Key Principles

ExpKit enforces experimental best practices through its [constitution](memory/constitution.md):

- **Scientific Integrity** - Preregistered hypotheses and analyses
- **Replicability** - Detailed protocols for independent replication
- **Statistical Rigor** - Mandatory power analysis and effect size justification
- **Participant Welfare** - VR comfort protocols and safety measures
- **Open Science** - Default to sharing data, materials, and code
- **VR Validity** - Leverage VR's unique affordances appropriately

## 🛠️ CLI Reference

### Commands

| Command     | Description                                                    |
|-------------|----------------------------------------------------------------|
| `init`      | Initialize a new ExpKit project from templates                 |
| `check`     | Check for installed tools                                      |

### `expkit init` Arguments & Options

| Argument/Option        | Type     | Description                                                                  |
|------------------------|----------|------------------------------------------------------------------------------|
| `<project-name>`       | Argument | Name for your new project directory (optional if using `--here`)            |
| `--ai`                 | Option   | AI assistant to use: `claude`, `gemini`, `copilot`, `cursor`, or `qwen`     |
| `--script`             | Option   | Script type: `sh` (bash/zsh) or `ps` (PowerShell)                          |
| `--ignore-agent-tools` | Flag     | Skip checks for AI agent tools                                             |
| `--no-git`             | Flag     | Skip git repository initialization                                          |
| `--here`               | Flag     | Initialize in current directory                                            |

## 📖 Documentation

For detailed guides and examples:

- [Complete ExpKit Methodology](./spec-driven.md)
- [VR Experiment Best Practices](./docs/vr-guidelines.md)
- [Contributing](CONTRIBUTING.md)

## 🤝 Contributing

ExpKit is open source and welcomes contributions! Key areas:
- Additional experimental paradigm templates
- Integration with other VR platforms
- Statistical analysis pipelines
- IRB template libraries

## 📄 License

This project is licensed under the MIT License - see [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Original [spec-kit](https://github.com/github/spec-kit) by GitHub
- [WorldViz](https://www.worldviz.com) for Vizard and Sightlab
- The open science and reproducibility movement in psychology

## 🔗 Links

- **Repository**: https://github.com/worldviz/exp-kit
- **Issues**: https://github.com/worldviz/exp-kit/issues
- **Original spec-kit**: https://github.com/github/spec-kit

---

*ExpKit: Bringing specification-driven development to experimental psychology*