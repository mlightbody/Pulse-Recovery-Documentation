# Pulse Recovery Portfolio

## Explainable recovery guidance from smartwatch heart-rate data

Pulse Recovery is a smartwatch and phone-based app that helps users understand how well they recover after exercise and how they might approach their next workout.

Many apps and devices can record heart-rate data. Pulse Recovery focuses on the harder question: *what does that data actually mean for the user?*

The app combines smartwatch heart-rate recovery data, subjective feedback, session history, and recovery trends to provide clear, personalised recovery guidance. It interprets the latest session, explains what appears to be driving the result, compares it with previous recovery patterns, and gives practical advice on how the user might approach their next workout.


---

## What this repository contains

This repository contains public portfolio and product documentation for Pulse Recovery.

The full application source code is currently private, but this repository includes product documentation, screenshots, architecture summaries, decision-engine notes, roadmap material, privacy and data-handling notes, and example session data.

---

## Product documents

* [Pulse Recovery Overview PDF](https://github.com/mlightbody/Pulse-Recovery-Documentation/blob/main/pdf/Pulse%20Recovery%20Overview.pdf)
  A fuller product overview covering the idea, user experience, screenshots, advice workflow, decision engine, and future direction.

* [Pulse Recovery One-Page PDF](https://github.com/mlightbody/Pulse-Recovery-Documentation/blob/main/pdf/Pulse%20Recovery%20One%20Page.pdf)
  A concise summary of the product, problem, differentiation, current status, and future direction.

---

## The problem

Heart-rate data is increasingly easy to collect, but it is not always easy to interpret.

A user may be able to see their peak heart rate, workout zones, recovery curve, or historical health data, but still be left wondering:

* Was that session harder than it should have been?
* Am I recovering well?
* Is my fitness improving?
* Should I push harder next time, hold steady, or back off?
* Is this just one poor session, or part of a trend?

Pulse Recovery is designed to close the gap between data and understanding.

---

## What the app does

Pulse Recovery uses the watch as a low-friction capture device and the phone as the richer review and interpretation experience.

The core workflow is:

1. Start a recovery session on the watch.
2. Capture heart-rate data during exercise and recovery.
3. Sync the session to the phone.
4. Review the workout and recovery curve.
5. Add subjective inputs such as perceived effort and post-exercise feeling.
6. Receive session-level recovery advice.
7. Review longer-term recovery trends.
8. Receive trend-based advice.

The goal is not simply to display heart-rate numbers. The goal is to help the user understand what those numbers may suggest.

---

## What makes Pulse Recovery different

Pulse Recovery is not just a heart-rate chart or a generic recovery score.

The app combines:

* objective heart-rate recovery data
* subjective user feedback
* previous session history
* trend direction
* explainable decision logic

This allows the app to provide advice that is more contextual than a single measurement.

For example, two workouts may produce similar recovery values but feel very different to the person doing them. A session that appears normal from heart-rate data alone may deserve more caution if it felt unusually hard or left the user feeling poor afterwards. Similarly, one weaker recovery result may not matter much on its own, while a pattern of declining recovery may suggest accumulated fatigue.

---

## Screenshots

The product experience is built around a watch-and-phone workflow:

* watch-based capture
* phone-based session review
* single-session advice
* recovery trend visualisation
* trend-based advice

Screenshots are included in the [Pulse Recovery Overview PDF](https://github.com/mlightbody/Pulse-Recovery-Documentation/blob/main/pdf/Pulse%20Recovery%20Overview.pdf) and supporting `images/` folder.

---

## Decision engine

Pulse Recovery uses a rule-based decision engine for the core recovery judgement.

The engine combines heart-rate recovery metrics, subjective feedback, and previous session history to generate both session-level and trend-level advice.

Its purpose is not simply to label a workout as good or bad. The aim is to explain what appears to be happening, what signals contributed to the advice, and how the user might approach their next workout.

See:

* [Decision Engine Summary](https://github.com/mlightbody/Pulse-Recovery-Documentation/blob/main/docs/Decision%20Engine%20Summary.md)

---

## Current status

Pulse Recovery has progressed beyond a concept into a working product prototype.

Current capabilities include:

* smartwatch-based heart-rate session capture
* phone-based session review
* full workout and recovery curve visualisation
* calculated recovery metrics
* subjective effort and post-exercise feeling inputs
* session-level advice
* trend-level advice
* session history
* Firebase-backed persistence
* Python-based analysis and charting tools
* iOS / Apple Watch development
* Android / Galaxy Watch development

---

## Supporting documents

* [Architecture Summary](https://github.com/mlightbody/Pulse-Recovery-Documentation/blob/main/docs/Architecture%20Summary.md)
* [Decision Engine Summary](https://github.com/mlightbody/Pulse-Recovery-Documentation/blob/main/docs/Decision%20Engine%20Summary.md)
* [Roadmap](https://github.com/mlightbody/Pulse-Recovery-Documentation/blob/main/docs/Roadmap.md)
* [Privacy and Data Handling](https://github.com/mlightbody/Pulse-Recovery-Documentation/blob/main/docs/Privacy%20and%20Data%20Handling.md)
* [Sample Session](https://github.com/mlightbody/Pulse-Recovery-Documentation/blob/main/examples/sample-session.md)
* [Sample Advice Output](https://github.com/mlightbody/Pulse-Recovery-Documentation/blob/main/examples/sample-advice-output.md)

---

## Future direction

Future development will focus on stronger personal baselines, richer trend analysis, saved and shareable charts, workout-type-specific context, and more adaptive coaching language.

The longer-term aim is for Pulse Recovery to become a practical recovery companion: not just recording what happened, but helping users understand how their body appears to be responding to training.

---

## What this project demonstrates

Pulse Recovery demonstrates end-to-end product thinking and practical implementation:

* identifying a real user problem
* designing a watch-and-phone workflow
* capturing physiological data from wearable devices
* combining objective and subjective inputs
* building an explainable decision engine
* persisting and analysing session history
* creating recovery visualisations
* developing across smartwatch, mobile, Firebase, and Python analysis tools
* turning raw data into practical user-facing guidance
