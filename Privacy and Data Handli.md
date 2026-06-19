# Pulse Recovery Privacy and Data Handling

## Overview

Pulse Recovery works with heart-rate, workout, recovery, and subjective user feedback data. Although the app is designed for fitness and recovery guidance rather than medical diagnosis, this data is still personal and should be treated carefully.

This document summarises the privacy and data-handling principles behind Pulse Recovery. It is intended as a portfolio and product-design note rather than a formal legal privacy policy.

---

## Type of Data Used

Pulse Recovery may use several types of user data to provide recovery guidance.

Examples include:

* heart-rate samples captured during exercise and recovery
* workout and recovery timestamps
* peak heart rate
* heart rate at the end of exercise
* heart rate after 60 seconds of recovery
* heart rate after 120 seconds of recovery
* calculated recovery metrics
* perceived effort score
* post-exercise feeling score
* generated session advice
* generated trend advice
* previous recovery assessments
* recovery trend history

The purpose of collecting this data is to help the user understand their recovery response and how it changes over time.

---

## Why This Data Is Needed

Pulse Recovery needs heart-rate and session data to calculate recovery metrics. It needs subjective feedback because heart-rate data alone does not fully describe how a workout affected the user.

For example, two sessions may show similar heart-rate recovery values but feel very different. A session that looks acceptable from heart-rate data alone may still deserve caution if it felt unusually hard or left the user feeling poor afterwards.

Historical data is also important because recovery trends are often more meaningful than isolated results. Storing previous sessions allows the app to compare the latest result with the user’s recent recovery pattern.

---

## Data Use Principles

Pulse Recovery is guided by several data-use principles.

### 1. Use data for user benefit

The data should be used to help the user understand their own recovery, not simply to collect more information.

### 2. Avoid unnecessary data collection

The app should only collect data that supports the recovery assessment, advice generation, history view, or product improvement.

### 3. Treat recovery data as sensitive

Heart-rate and workout data can reveal information about a person’s health, habits, routines, and physical condition. Even where the app is not making medical claims, the data should be handled with care.

### 4. Keep advice explainable

The app should make it possible to understand why advice was given. Users should not be left with a black-box recommendation based on hidden assumptions.

### 5. Avoid medical overclaiming

Pulse Recovery should present its output as fitness and recovery guidance, not diagnosis or medical advice.

---

## Data Storage

Pulse Recovery stores completed sessions and assessments so that the user can review previous results and receive trend-based advice.

Stored information may include:

* raw or sampled heart-rate data
* calculated recovery values
* subjective scores
* generated advice
* timestamps
* session history

Firebase-backed persistence is used to support session history, cross-device access, and analysis of previous recovery patterns.

Where possible, the app should avoid storing unnecessary personal information beyond what is needed for the recovery workflow.

---

## Data Interpretation

Pulse Recovery interprets recovery data using an explainable decision engine.

The advice may consider:

* the latest recovery response
* first-minute and second-minute heart-rate recovery
* how hard the session felt
* how the user felt after exercise
* previous recovery results
* recent trend direction

The app should avoid implying certainty where the data is only suggestive. Heart-rate recovery can be affected by many factors, including sleep, stress, hydration, heat, illness, medication, caffeine, workout type, and general fatigue.

For that reason, Pulse Recovery should frame advice carefully. It can suggest that a pattern may indicate good recovery, accumulated fatigue, or the need for caution, but it should not present this as a medical conclusion.

---

## Health and Medical Disclaimer

Pulse Recovery is intended for fitness, recovery, and training guidance.

It is not intended to diagnose, treat, prevent, or monitor medical conditions. It should not be used as a substitute for professional medical advice.

Users with chest pain, dizziness, fainting, unusual shortness of breath, irregular heartbeat symptoms, or any other concerning symptoms should seek appropriate medical advice.

The app’s recommendations should be understood as guidance based on available recovery data, not as a clinical judgement.

---

## User Transparency

The user should be able to understand:

* what data is being captured
* why that data is used
* how it contributes to advice
* what the advice does and does not mean
* where previous sessions are stored
* how trend advice is generated

This is especially important because recovery advice can influence user behaviour. If the app suggests caution or recovery, the user should understand the reason. If it suggests progression, the user should still understand that progression should be gradual and based on their own judgement.

---

## Product Design Implications

Privacy and data handling are not just legal issues. They affect the product design.

Pulse Recovery should aim to:

* avoid collecting unnecessary data
* present advice in cautious, non-medical language
* explain recommendations clearly
* distinguish fitness guidance from diagnosis
* allow users to review their own history
* make trend advice understandable
* avoid creating false certainty from limited data

These principles help make the app more trustworthy.

---

## Summary

Pulse Recovery uses heart-rate recovery data, subjective feedback, and previous session history to provide personalised recovery guidance.

Because this data is personal and health-adjacent, it should be handled carefully. The app should collect only what it needs, explain how the data is used, avoid medical claims, and present recovery advice as guidance rather than diagnosis.

The goal is to give users useful insight while respecting the sensitivity of their data.
