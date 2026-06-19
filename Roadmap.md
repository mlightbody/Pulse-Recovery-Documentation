# Pulse Recovery Roadmap

## Overview

Pulse Recovery has progressed from a personal experiment into a working smartwatch and phone-based recovery guidance product. The current version focuses on capturing heart-rate recovery data, displaying the full workout and recovery curve, collecting subjective feedback, and producing both session-level and trend-level advice.

The roadmap below sets out possible next steps. It is organised by product maturity rather than fixed dates.

---

## Current Capabilities

Pulse Recovery currently supports the core recovery workflow:

* smartwatch-based heart-rate capture
* workout and recovery session recording
* phone-based session review
* full workout and recovery curve visualisation
* peak heart-rate detection
* end-of-exercise heart-rate value
* 60-second recovery value
* 120-second recovery value
* subjective perceived effort input
* post-exercise feeling input
* session-level advice
* trend-level advice
* session history
* Firebase-backed persistence
* Python-based recovery curve analysis and charting
* iOS / Apple Watch development
* Android / Galaxy Watch development

This creates the foundation for a product that does more than collect heart-rate data. It interprets recovery and helps users understand what their latest session and longer-term pattern may suggest.

---

## Near-Term Improvements

The next stage should focus on improving usability, clarity, and confidence in the current experience.

### 1. Improve Session Review

Possible improvements:

* clearer session summary layout
* better separation between workout and recovery phases
* clearer display of peak heart rate, end heart rate, 60-second recovery, and 120-second recovery
* improved chart labels and annotations
* ability to save or export recovery charts
* better handling of unusual heart-rate curves

The goal is to make the session result easier to understand at a glance.

### 2. Improve Advice Presentation

Possible improvements:

* clearer headline recommendation
* stronger explanation of what drove the advice
* better distinction between session advice and trend advice
* clearer next-step suggestions
* more cautious wording where the data is uncertain
* improved advice text for edge cases

The goal is to make the advice feel specific, useful, and trustworthy rather than generic.

### 3. Improve Subjective Input Guidance

The app currently uses perceived effort and post-exercise feeling. These inputs could be made easier for users to answer consistently.

Possible improvements:

* guidance labels for effort scores
* guidance labels for post-exercise feeling scores
* examples for different score ranges
* clearer explanation of why subjective feedback matters
* optional notes field for context such as poor sleep, heat, illness, or stress

The goal is to improve the quality of the subjective data without adding too much friction.

### 4. Improve Watch Experience

Possible improvements:

* clearer start and stop states
* more obvious session status
* better feedback when recording is active
* clearer indication when a session has been saved or synced
* support for pending sessions on the watch
* improved handling when the phone is not nearby

The goal is to keep watch capture simple and reliable.

---

## Medium-Term Product Development

The medium-term roadmap should focus on making the app more personalised and more useful over time.

### 1. Personal Recovery Baselines

Heart-rate recovery varies between individuals. A fixed threshold can be useful, but personal baselines make the advice more meaningful.

Possible improvements:

* calculate each user’s normal recovery range
* compare sessions against personal history
* identify unusually strong or weak recovery
* distinguish normal variation from meaningful change
* adapt trend advice to the user’s own pattern

The goal is to make advice more personal and less dependent on generic thresholds.

### 2. Richer Trend Analysis

Trend advice is one of the most distinctive parts of Pulse Recovery. This can be expanded further.

Possible improvements:

* clearer improving, stable, and declining trend detection
* trend charts for 60-second and 120-second recovery
* trend charts for perceived effort and post-exercise feeling
* combined recovery and effort trend interpretation
* detection of repeated strain patterns
* detection of improving recovery at similar or higher workload

The goal is to help users understand not just one workout, but how their recovery is changing.

### 3. Workout-Type Context

Recovery values mean more when interpreted in relation to the type of activity.

Possible improvements:

* allow users to label workout type
* compare similar sessions with similar sessions
* separate walking, running, cycling, gym, intervals, stairs, and sport sessions
* adjust advice based on workout intensity and type
* identify when a session was unusually hard for its category

The goal is to avoid comparing fundamentally different workouts too directly.

### 4. Better History and Reporting

The history view can become more useful as more sessions are collected.

Possible improvements:

* improved session list and filtering
* saved charts
* shareable session summaries
* PDF export
* weekly or monthly recovery summaries
* personal best recovery markers
* notes on unusual sessions

The goal is to make Pulse Recovery useful as an ongoing recovery journal.

---

## Longer-Term Opportunities

Longer-term development could extend Pulse Recovery from a recovery assessment app into a broader recovery companion.

### 1. AI Coaching-Language Layer

AI could be used to improve the way advice is explained, while keeping the core decision engine explainable.

Possible uses:

* warmer coaching-style explanations
* personalised tone based on user preference
* summaries of recent recovery history
* natural-language explanations of trends
* conversion of structured decision outputs into more readable guidance

The important principle is that AI should explain and communicate the decision, not replace the core recovery judgement.

### 2. Training Load and Readiness Context

Pulse Recovery could become more useful by incorporating broader context around training load and readiness.

Possible additions:

* recent workout frequency
* recent intensity pattern
* rest days
* repeated hard sessions
* user-reported fatigue
* sleep or stress context, if available and appropriate
* comparison between planned and actual training load

The goal would be to help users understand whether their current training pattern is sustainable.

### 3. Broader Device and Platform Support

The product could support a wider range of devices and workflows.

Possible directions:

* wider Android watch support
* improved Apple Watch integration
* support for additional heart-rate sensors
* integration with external fitness platforms
* exportable data formats
* companion web dashboard

The goal would be to make the recovery workflow available to more users without losing the simplicity of the watch-and-phone experience.

### 4. Smarter Personalisation

As more data is collected, the app can become better at recognising the user’s normal patterns.

Possible improvements:

* adaptive thresholds
* personalised recovery zones
* outlier detection
* user-specific trend sensitivity
* context-aware advice
* confidence indicators
* different guidance styles for beginners and experienced athletes

The goal is to move from general recovery guidance toward genuinely personal recovery interpretation.

---

## Backlog Themes

The roadmap can also be viewed as a set of backlog themes.

| Theme              | Example Items                                                       | User Value                                   |
| ------------------ | ------------------------------------------------------------------- | -------------------------------------------- |
| Session clarity    | Better chart labels, clearer recovery metrics, improved summaries   | Makes each result easier to understand       |
| Advice quality     | Stronger explanations, better edge-case wording, clearer next steps | Makes recommendations more useful            |
| Subjective context | Better scoring guidance, optional notes, context capture            | Improves interpretation of the data          |
| Trend insight      | Richer trend detection, combined recovery/effort patterns           | Helps users understand progress over time    |
| Personalisation    | Personal baselines, adaptive thresholds, outlier detection          | Makes advice more relevant to the individual |
| Reporting          | Saved charts, shareable summaries, PDF export                       | Helps users review and communicate progress  |
| Platform support   | Better watch sync, broader device support                           | Improves reliability and reach               |
| Coaching layer     | AI-assisted explanations, personalised tone                         | Makes advice warmer and easier to act on     |

---

## Prioritisation

A sensible priority order would be:

1. Improve the clarity of the current session review and advice.
2. Improve subjective input guidance.
3. Add saved/exportable charts.
4. Strengthen trend analysis.
5. Add personal recovery baselines.
6. Add workout-type context.
7. Improve reporting and history views.
8. Explore AI-assisted coaching language.
9. Broaden device and platform support.

This prioritisation keeps the focus on improving the core value of the product before expanding too widely.

---

## Summary

The current Pulse Recovery product already supports the core workflow: capture recovery data, review the session, add subjective context, generate advice, and track trends over time.

The next stage is to make the product clearer, more personal, and more useful across repeated use. The most important future directions are stronger advice presentation, better trend analysis, personal baselines, saved charts, workout-type context, and more adaptive coaching language.

The long-term opportunity is to develop Pulse Recovery into a personal recovery companion that helps users understand how their body appears to be responding to training over time.
