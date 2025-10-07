# Fuzzy Logic-Based Erosion Risk Assessment Using RUSLE Factors

This laboratory project contains the development of a fuzzy logic-based system for soil erosion risk assessment using RUSLE factors. The project demonstrates the integration of fuzzy inference systems with environmental modeling to provide interpretable risk classifications that incorporate expert knowledge and handle uncertainty.

### Project Overview
The fuzzy erosion risk assessment system transforms quantitative RUSLE parameters into qualitative risk categories through:
- Linguistic variable representation of environmental factors
- Expert-defined fuzzy rules capturing erosion dynamics
- Mamdani fuzzy inference for risk classification
- Visualization tools for transparency and validation

### Documentation Guide
This report is organized to provide both comprehensive coverage and focused access to specific topics:

**For Theoretical Background:**
- [Theory Guide](docs/theory.md) - RUSLE concepts and fuzzy logic integration
- [Design Rationale](docs/design-rationale.md) - Universe of discourse explanations and design decisions

**For Implementation Details:**
- [Main Implementation](imp/main.ipynb) - Complete fuzzy system code and inference engine
- [Membership Functions](imp/membership-functions.ipynb) - Fuzzy set definitions and visualization

The following sections provide a complete laboratory report structure, while the linked documentation offers deeper exploration of specific components.

## Methodology

### System Architecture
The fuzzy erosion risk assessment system consists of:
1. **Input Variables**: Five RUSLE factors (R, K, LS, C, P)
2. **Membership Functions**: Triangular and trapezoidal fuzzy sets for each input
3. **Rule Base**: Expert-defined fuzzy rules (30+ rules)
4. **Inference Engine**: Mamdani fuzzy inference system
5. **Output Variable**: Erosion risk level (Low/Medium/High)

### Fuzzy Variable Definitions

#### Input Variables
- **Rainfall (R)**: Universe of discourse [0, 2000] MJ·mm·ha⁻¹·h⁻¹·yr⁻¹
  - Low: Trapezoidal [0, 0, 400, 800]
  - Medium: Triangular [600, 1000, 1400]
  - High: Trapezoidal [1200, 1600, 2000, 2000]

- **Soil Erodibility (K)**: Universe of discourse [0, 1]
  - Low: Trapezoidal [0, 0, 0.2, 0.4]
  - Medium: Triangular [0.2, 0.4, 0.6]
  - High: Trapezoidal [0.4, 0.6, 1.0, 1.0]

- **Slope Length-Steepness (LS)**: Universe of discourse [0, 10]
  - Low: Trapezoidal [0, 0, 2, 4]
  - Medium: Triangular [2, 5, 8]
  - High: Trapezoidal [4, 8, 10, 10]

- **Cover-Management (C)**: Universe of discourse [0, 1]
  - Good: Trapezoidal [0, 0, 0.1, 0.5]
  - Moderate: Triangular [0.3, 0.6, 0.8]
  - Poor: Trapezoidal [0.6, 0.8, 1.0, 1.0]

- **Support Practice (P)**: Universe of discourse [0, 1]
  - Good: Trapezoidal [0, 0, 0.2, 0.4]
  - Moderate: Triangular [0.3, 0.5, 0.7]
  - Poor: Trapezoidal [0.6, 0.8, 1.0, 1.0]

#### Output Variable
- **Risk Level**: Universe of discourse [0, 1]
  - Low Risk: Trapezoidal [0, 0, 0.2, 0.4]
  - Medium Risk: Triangular [0.3, 0.5, 0.7]
  - High Risk: Trapezoidal [0.6, 0.8, 1.0, 1.0]

## Implementation

### Software Tools
- **Python 3.10**: Programming language
- **scikit-fuzzy**: Fuzzy logic library
- **NumPy**: Numerical computations
- **Matplotlib**: Visualization
- **Pandas**: Data manipulation
- **Jupyter Notebook**: Interactive development environment

### Code Structure
```
fuzzy-erosion-risk-assessment/
├── imp/
│   ├── main.ipynb              # Main implementation
│   └── membership-functions.ipynb # Membership function visualization
└── docs/
    ├── theory.md               # Theoretical background
    ├── design-rationale.md     # Design decisions
    └── rules.txt               # Complete rule set
```
## Results

### Membership Function Visualization
The system successfully implements membership functions for all RUSLE factors, providing clear visualization of fuzzy sets. Each factor demonstrates appropriate linguistic variable coverage with minimal overlap between adjacent terms.

### Sample Inference Results

| Input Factors |  Fuzzy Risk Level | Primary Drivers |
|--------------|------------------|-----------------|
| R=300, K=0.2, LS=2, C=0.3, P=0.4 | Low Risk (0.18) | Flat slope, Good cover |
| R=700, K=0.6, LS=8, C=0.8, P=0.9 | High Risk (0.77) | Steep slope, Poor cover |

## Conclusion

This successfully demonstrated the application of fuzzy logic to soil erosion risk assessment. The Mamdani fuzzy inference system effectively integrated RUSLE factors with expert knowledge, providing interpretable risk classifications. The implementation showcases the practical utility of fuzzy systems in environmental modeling, particularly for handling uncertainty and incorporating domain expertise.

Key achievements include:
- Successful implementation of fuzzy membership functions
- Development of comprehensive rule base
- Real-time inference capabilities
- Effective visualization tools

The system provides a foundation for further research in fuzzy environmental modeling and could be extended to include additional factors or more sophisticated defuzzification methods.