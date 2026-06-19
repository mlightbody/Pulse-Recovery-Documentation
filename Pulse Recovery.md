# Pulse Recovery

## Turning heart-rate recovery data into practical training guidance

Pulse Recovery helps users answer a simple but important question after exercise: *how well did I recover, and what should I do next?*

Using smartwatch heart-rate data, subjective feedback, session history, and recovery trends over time, the app turns each workout into clear, personalised recovery guidance. It interprets the latest session, explains what appears to be driving the result, compares it with previous recovery patterns, and gives practical advice on how to approach the next workout.

---

## The Problem

Many apps and devices collect heart-rate data, but the data is often left for the user to interpret. A user may be able to see their peak heart rate, average heart rate, recovery curve, workout zones, or historical health data, but still be left wondering what the session actually means.

Pulse Recovery is designed to close that gap between data and understanding.

---

## What the App Does

Pulse Recovery uses a smartwatch to capture heart-rate data during exercise and recovery. The phone app then presents the session, calculates recovery metrics, combines them with subjective inputs, and generates advice for both the latest workout and longer-term recovery trends.

The workflow is simple:

1. Start a recovery session on the watch.
2. Capture heart-rate data during exercise and recovery.
3. Sync the session to the phone.
4. Review the workout and recovery curve.
5. Add subjective inputs such as perceived effort and post-exercise feeling.
6. Receive session-level and trend-level recovery guidance.

---

## Key Features

* **Watch-based capture**
  Low-friction heart-rate recording during exercise and recovery.

* **Full recovery curve visualisation**
  Shows the workout build-up, peak heart rate, first-minute recovery, second-minute recovery, and recovery curve shape.

* **Subjective context**
  Adds perceived effort and post-exercise feeling so the advice reflects how the workout felt, not just what the heart-rate numbers show.

* **Session-level advice**
  Explains what the latest workout may suggest and how the user might approach their next session.

* **Trend-level advice**
  Looks across previous sessions to identify whether recovery appears to be improving, stable, or showing signs of strain.

* **Explainable decision engine**
  Uses transparent, rule-based logic rather than a black-box AI response, making the advice consistent, testable, and tunable.

---

## What Makes It Different

Pulse Recovery is not just a heart-rate chart or a generic recovery score. Many devices can show heart-rate data; the harder problem is helping the user understand what that data may mean.

The app combines objective recovery data, subjective feedback, and previous results to provide context-rich advice. It helps the user understand not only the latest session, but also whether their broader recovery pattern suggests progress, stability, fatigue, or the need for more recovery.

---

## Current Status

Pulse Recovery has progressed beyond a concept into a working product prototype. Current capabilities include:

* smartwatch-based heart-rate session capture
* phone-based session review
* iOS and Andriod front ends with common cross platform decision engine
* full workout and recovery charting
* calculated recovery metrics
* subjective effort and post-exercise feeling inputs
* session advice
* trend advice
* session history
* Firebase-backed data persistence
* Python-based analysis and charting tools
* iOS / Apple Watch development - initial beta build has Apple approval
* Android / Galaxy Watch development - working

---

## Future Direction

Future development will focus on stronger personal baselines, richer trend analysis, improved chart export, clearer workout-type context, and more adaptive coaching language.

AI may be useful as a future coaching-language layer, helping explain the results in a warmer and more personalised way. However, the core recovery judgement should remain explainable and grounded in the user’s data.

---

## Portfolio Value

Pulse Recovery demonstrates end-to-end product thinking: identifying a user problem, designing a watch-and-phone workflow, capturing real physiological data, building an explainable decision engine, developing visual feedback, persisting historical data, and turning raw measurements into actionable user guidance.
