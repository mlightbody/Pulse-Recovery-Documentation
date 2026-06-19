# Pulse Recovery Architecture Summary

## Overview

Pulse Recovery is built around a watch-and-phone workflow. The watch captures heart-rate data during exercise and recovery, while the phone provides the richer review, interpretation, history, and advice experience.

At a high level, the architecture is designed to support five core responsibilities:

1. capture heart-rate data with minimal friction
2. sync the captured session to the phone
3. calculate recovery metrics from the session
4. interpret the result through an explainable decision engine
5. store and review session history over time

```text
Smartwatch Capture
        ↓
Phone Sync
        ↓
Session Review
        ↓
Recovery Metrics
        ↓
Decision Engine
        ↓
Session Advice + Trend Advice
        ↓
History and Analysis
```

---

## Watch Capture Layer

The watch is used as the capture device because it is already on the user’s wrist during exercise and recovery.

The watch app is responsible for:

* starting and stopping a recovery session
* recording heart-rate samples during the workout and recovery period
* capturing key time points such as the end of exercise, 60-second recovery, and 120-second recovery
* storing captured sessions locally where needed
* transferring completed sessions to the phone

The design aim is to keep the watch experience low friction. During exercise, the user should not have to enter lots of information or interpret results. The watch focuses on capture; interpretation happens later on the phone.

---

## Phone Review Layer

The phone app provides the main user experience after the session has been captured.

The phone app is responsible for:

* receiving sessions from the watch
* displaying the full workout and recovery curve
* showing calculated recovery values
* collecting subjective inputs such as perceived effort and post-exercise feeling
* generating session-level advice
* showing recovery history
* presenting trend-level advice

This separation is important because it matches the context of use. The watch is best for quick capture during activity; the phone is better for charts, explanations, history, and reflection.

---

## Data Flow

A typical Pulse Recovery session follows this path:

1. The user starts a recovery session on the watch.
2. The watch records heart-rate samples during exercise.
3. The user stops the workout at the end of exercise.
4. The watch continues recording the recovery period.
5. Key recovery values are captured, including heart rate at the end of exercise, after 60 seconds, and after 120 seconds.
6. The completed session is synced to the phone.
7. The phone displays the session curve and calculates recovery metrics.
8. The user adds subjective feedback.
9. The decision engine generates session advice.
10. The result is stored and becomes part of the user’s recovery history.
11. Trend logic compares the latest session with previous results and generates trend advice.

---

## Recovery Metrics Layer

The recovery metrics layer converts the captured heart-rate session into values that can be used by the advice engine.

Examples of derived metrics include:

* peak heart rate during the session
* heart rate at the end of exercise
* heart-rate drop after 60 seconds
* heart-rate drop after 120 seconds
* recovery curve shape
* comparison with previous recovery values
* recent recovery trend direction

These metrics provide the objective foundation for the advice. They allow the app to go beyond a simple single-point measurement and consider the broader recovery pattern.

---

## Subjective Feedback Layer

Pulse Recovery also includes subjective inputs because heart-rate data alone does not tell the whole story.

The user can add context such as:

* perceived effort
* how they felt after exercise

This matters because two sessions with similar heart-rate recovery values may feel very different. A session that produced normal recovery numbers but felt unusually hard may need to be interpreted differently from a session that felt comfortable.

By combining objective and subjective inputs, Pulse Recovery can provide advice that is more personal and more useful than a heart-rate chart alone.

---

## Decision Engine Layer

The decision engine converts recovery metrics and subjective feedback into advice.

The current approach uses rule-based logic rather than a generative AI model for the core recovery judgement. This was chosen because recovery guidance should be:

* transparent
* consistent
* testable
* tunable
* explainable

The engine produces advice at two levels:

* **Session advice** — guidance based on the latest workout and recovery response.
* **Trend advice** — guidance based on how recovery appears to be changing across previous sessions.

This approach allows the app to explain not only what the recommendation is, but also what appears to be driving it.

---

## Persistence and History

Pulse Recovery stores completed sessions and assessments so that the user can review progress over time.

Stored information may include:

* heart-rate samples
* session timestamps
* recovery metrics
* perceived effort scores
* post-exercise feeling scores
* generated advice
* historical trend values

This history is important because a single session can be useful, but recovery patterns over time are often more meaningful. Storing previous sessions allows the app to identify improving, stable, or declining recovery trends.

---

## Analysis and Validation Tools

In addition to the watch and phone apps, Python-based tools are used for analysis and validation.

These tools support:

* plotting full workout and recovery curves
* comparing multiple sessions
* checking recovery trends
* validating decision-engine behaviour
* creating charts for documentation and review

This analysis layer is useful during development because it makes it easier to inspect whether the data, charts, and advice logic are behaving sensibly across real examples.

---

## Platform Scope

Pulse Recovery has been developed across multiple platform components:

* iOS / Apple Watch app development
* Android / Galaxy Watch app development
* phone-based session review and advice
* Firebase-backed persistence
* Python-based analysis and charting

The architecture is intended to support the same core product idea across platforms: capture recovery data on the watch, interpret it on the phone, and use history to provide more meaningful advice over time.

---

## Design Principles

The architecture is guided by several product and technical principles:

* **Low-friction capture**
  The watch experience should be simple during exercise.

* **Clear separation of roles**
  The watch captures; the phone explains.

* **Explainable advice**
  Recovery guidance should be traceable to data and decision logic.

* **Objective plus subjective context**
  Heart-rate data is combined with how the session felt.

* **History matters**
  Trend advice is based on patterns across sessions, not just isolated scores.

* **Health-adjacent caution**
  The app provides fitness and recovery guidance, not medical diagnosis.

---

## Summary

Pulse Recovery is built as a connected recovery workflow rather than a simple heart-rate display.

The watch captures the session, the phone presents the data, the metrics layer derives recovery values, the decision engine generates advice, and the history layer allows the app to understand trends over time.

This architecture supports the central product goal: turning raw heart-rate recovery data into clear, explainable, and actionable guidance.
