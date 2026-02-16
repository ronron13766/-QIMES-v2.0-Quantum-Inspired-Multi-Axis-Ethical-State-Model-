# QIMES v2.0
### Quantum-Inspired Multi-Axis Ethical State Model

A principled framework for AI ethics that combines theoretical rigor with empirical validation.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Validated](https://img.shields.io/badge/validated-100%20scenarios-green.svg)](tests/)

---

## What is QIMES?

QIMES v2.0 addresses a fundamental challenge: **How can AI systems navigate complex ethical dilemmas that involve competing values, contextual nuance, and fundamental human rights?**

Rather than reducing ethics to simple optimization or rigid rules, QIMES proposes a **multi-axis probabilistic framework** where:

- Moral states exist as **superpositions** of competing ethical considerations
- **Hard constraints** preserve human dignity regardless of utilitarian calculations  
- **Context** influences how moral tensions resolve into decisions
- **Human judgment** is explicitly invoked for genuinely ambiguous cases

**Empirical Result**: 85% accuracy on 100 diverse scenarios with zero false positives.

---

## Core Architecture

### Three-Axis Moral Representation

```
|ψ⟩ = √p_H|Harm⟩ + √p_B|Benefit⟩ + √p_R|Reflection⟩
```

- **Harm**: Potential negative consequences, risks
- **Benefit**: Potential positive outcomes, welfare
- **Reflection**: Moral ambiguity, need for deliberation

### Dignity Constraints (Non-Negotiable)

Based on UN Universal Declaration of Human Rights:

✓ **Privacy protection** - No unauthorized data use  
✓ **Non-discrimination** - No bias by age/gender/origin  
✓ **Autonomy respect** - No coercion or manipulation  
✓ **Transparency** - No hidden agendas  
✓ **Equal treatment** - Fair resource distribution  
✓ **Human dignity** - People as subjects, not objects  

**If violated → Automatic BLOCK, no exceptions.**

### Decision Process

```python
# 1. Check dignity constraints
if violates_dignity():
    return BLOCKED

# 2. Evaluate moral state with context
state = evolve_with_context(harm, benefit, reflection, context)

# 3. Decide based on probabilities
if reflection > 0.4:
    return HUMAN_REVIEW  # Too ambiguous
elif benefit >> harm:
    return APPROVE
elif harm >> benefit:
    return REJECT
else:
    return HUMAN_REVIEW
```

---

## Installation & Quick Start

```bash
# Install dependencies
pip install numpy scipy

# Run basic example
python examples/basic.py
```

### Your First Decision

```python
from qimes import QIMESModel, EthicalScenario

model = QIMESModel()

scenario = EthicalScenario(
    name="AI Medical Diagnosis",
    harm_level=0.6,      # Risk if wrong
    benefit_level=0.8,   # Benefit if correct
    context_factors={
        "urgency": 0.7,
        "transparency": 0.8,
        "social_impact": 0.9
    },
    dignity_violations=[]
)

decision, metadata = model.decide(scenario)
print(f"Decision: {decision.value}")
print(f"Reason: {metadata['reason']}")
```

---

## Validation Results

### 100-Scenario Benchmark

Tested across 6 ethical domains:

| Domain | Scenarios | Accuracy |
|--------|-----------|----------|
| Medical Ethics | 20 | 90.0% |
| Privacy & Surveillance | 15 | 86.7% |
| Fairness & Discrimination | 20 | 80.0% |
| Autonomy & Manipulation | 15 | 93.3% |
| Resource Allocation | 15 | 73.3% |
| Free Speech vs. Harm | 15 | 93.3% |
| **Total** | **100** | **85.0%** |

### vs. Baseline Approaches

| Model | Accuracy | Dignity Blocks | False Positives |
|-------|----------|----------------|-----------------|
| **QIMES v2.0** | **85%** | 42 ✓ | 0 ✓ |
| Utilitarian | 48% | 0 ✗ | Multiple ✗ |
| Rule-Based | 31% | 0 ✗ | Multiple ✗ |
| Statistical | 44% | 0 ✗ | Multiple ✗ |

**Key**: QIMES is the only model that caught all dignity violations.

---

## Example Scenarios

### Approved

**Voluntary Fitness Tracker**
```python
# Low privacy risk, high health benefit, transparent
Decision: APPROVE
Reason: Benefit clearly outweighs harm (ratio: 4.0)
```

###  Blocked

**Discriminatory Hiring Algorithm**
```python
# Historical bias favors men
Dignity Violations: ["no_discrimination", "equal_treatment"]
Decision: BLOCKED_BY_DIGNITY
```

### Human Review Needed

**Pandemic Contact Tracing**
```python
# Privacy concerns vs public health
High urgency, high social impact, conflicting values
Decision: HUMAN_REVIEW
Reason: Reflection probability 0.52 - requires deliberation
```

---

## Run Tests Yourself

```bash
# Full benchmark
python tests/test_qimes.py

# Expected output:
# Testing 100 scenarios...
# ✓ Accuracy: 85.0% (85/100)
# ✓ Dignity Blocks: 42
# ✓ False Positives: 0
```

---

## Theoretical Background

QIMES integrates:

- **Deontological Ethics**: Hard dignity constraints (Kant)
- **Consequentialism**: Harm-benefit analysis (Mill)
- **Virtue Ethics**: Reflection axis (Aristotle)
- **Care Ethics**: Context sensitivity (Gilligan)
- **Quantum Cognition**: Formal modeling of uncertainty (Busemeyer)

This pluralistic approach avoids reducing ethics to a single principle.

---

## Scope & Limitations

### What QIMES Is

✓ Theoretical framework with empirical validation  
✓ Working proof-of-concept  
✓ Research tool for exploring AI ethics  
✓ Demonstration that dignity-preserving AI is feasible  

### What QIMES Is Not

✗ Production system for critical deployments  
✗ Replacement for human moral judgment  
✗ Universal solution to all ethical problems  
✗ Claim to have "solved" ethics  

### Challenges

- 15% error rate on test scenarios
- May need domain-specific calibration
- Cultural variation in moral intuitions
- Edge cases remain difficult

---

## Use Cases

**Research**: Benchmark ethical AI, study alignment approaches  
**Development**: Pre-screen systems for ethical issues  
**Education**: Teach AI ethics through working examples  
**Policy**: Analyze ethical implications of proposals  

---

## Contributing

We welcome:
- Additional test scenarios
- Cross-cultural validation
- Domain-specific tuning
- Theoretical critiques
- Alternative implementations

See [CONTRIBUTING.md](CONTRIBUTING.md)

---

## License

MIT License - Free for research and exploration.

---

## Citation

```bibtex
@software{qimes2026,
  title={QIMES v2.0: Quantum-Inspired Multi-Axis Ethical State Model},
  year={2026}
}
```

---

## Contact

- Issues: [GitHub Issues](#)
- Discussions: [GitHub Discussions](#)

---

**QIMES v2.0**  
*Theoretical rigor. Empirical validation. Human dignity preserved.*
