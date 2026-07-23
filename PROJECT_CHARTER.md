# PROJECT CHARTER

## Project Information

**Project Name:** Understanding and Predicting Hospital Readmission Performance Across U.S. Hospitals

**Author:** Andrew Zhou

**Project Type:** End-to-End Healthcare Data Science Portfolio Project

**Status:** Planning Phase

**Last Updated:** July 2026

## Understanding and Predicting Hospital Readmission Performance Across U.S. Hospitals

## Executive Summary

The Centers for Medicare & Medicaid Services (CMS) publicly reports hospital quality metrics, including 30-day readmission performance for several medical conditions. Hospitals with higher-than-expected readmission rates may experience worse patient outcomes and financial penalties, making readmission reduction an important healthcare quality objective.

This project investigates which hospital characteristics and patient experience measures are associated with higher-than-expected 30-day heart failure readmission performance. By combining multiple CMS datasets, the project will perform exploratory analysis, statistical analysis, and machine learning to identify factors related to hospital performance and provide data-driven recommendations.

## Stakeholders

Primary Stakeholder

- Centers for Medicare & Medicaid Services (CMS)

Secondary Stakeholders

- Hospital administrators
- Healthcare quality improvement teams
- Healthcare consultants
- Insurance organizations
- Researchers interested in hospital quality

- ## Business Problem

Hospitals across the United States vary in their 30-day heart failure readmission performance. While CMS publishes these quality metrics annually, the reasons behind differences in hospital performance are not immediately clear.

Understanding which hospital characteristics and patient experience measures are associated with higher-than-expected readmissions can help healthcare organizations identify opportunities for quality improvement and prioritize interventions.

## Primary Research Question

Which hospital characteristics and patient experience measures are most strongly associated with higher-than-expected 30-day heart failure readmissions among U.S. hospitals?

## Supporting Questions

1. How does heart failure readmission performance vary across hospitals?

2. Which hospital characteristics are associated with higher readmission ratios?

3. Which patient experience measures are associated with readmission performance?

4. Can hospital characteristics and patient experience measures predict whether a hospital performs above or below the national benchmark?

5. Which variables contribute most to model predictions?

6. What recommendations can be made to improve hospital performance?

## Initial Hypotheses

H1:
Hospitals with higher overall CMS ratings will have lower heart failure readmission ratios.

H2:
Hospitals with stronger patient communication scores will have lower readmission ratios.

H3:
Hospitals with better discharge information scores will have lower readmission ratios.

H4:
Hospital ownership type is associated with readmission performance.

H5:
Hospital type is associated with readmission performance.

## Datasets

1. Hospital Readmissions
Purpose:
Target variable (heart failure readmission performance)

2. Hospital General Information
Purpose:
Hospital characteristics

3. HCAHPS Patient Survey
Purpose:
Patient experience measures

## Project Scope

Included

- Heart failure readmission measure
- CMS hospital quality data
- Patient experience data
- Hospital-level analysis
- Statistical analysis
- Machine learning
- Model interpretation

Excluded

- Individual patient prediction
- Clinical treatment recommendations
- Causal inference
- Other readmission conditions (Version 1)

## Success Criteria

The project will be considered successful if it:

- Successfully merges all three CMS datasets.
- Identifies meaningful patterns in hospital readmission performance.
- Builds an interpretable predictive model.
- Explains important predictors using SHAP.
- Produces actionable recommendations supported by the analysis.
- Includes a professional GitHub repository and documentation.

## Deliverables

- Professional GitHub repository
- Data dictionary
- Analysis plan
- Clean notebooks
- Statistical analysis
- Machine learning models
- SHAP interpretation
- Interactive dashboard
- Final report
- Executive summary

## Timeline

Phase 1
Planning

Phase 2
Data understanding

Phase 3
Data cleaning

Phase 4
Exploratory analysis

Phase 5
Feature engineering

Phase 6
Machine learning

Phase 7
Interpretation

Phase 8
Dashboard and final report
