# Pulse Recovery Decision Engine Summary

## Overview

The Pulse Recovery decision engine turns recovery data into structured, explainable advice.

It combines heart-rate recovery metrics, subjective user feedback, and previous session history to produce guidance at two levels:

* **Session advice** — what the latest workout and recovery response appear to suggest.
* **Trend advice** — how the user’s recovery pattern appears to be changing over time.

The engine is designed to help users understand not just *what* happened in a session, but what the result may mean in context and how they might approach their next workout.

---

## Role of the Decision Engine

The decision engine sits between the raw recovery data and the user-facing advice.

```text
Captured heart-rate data
        ↓
Recovery metrics
        ↓
Subjective feedback
        ↓
Previous session history
        ↓
Decision engine
        ↓
Session advice + trend advice
```

Its job is to combine several signals that would otherwise be hard for the user to interpret separately.

For example, a heart-rate recovery value may look good in isolation, but the interpretation may change if the session felt unusually hard. Similarly, one weaker session may not be especially meaningful, while a repeated decline across several sessions may suggest accumulated fatigue or under-recovery.

The decision engine brings these signals together and produces a clear, user-facing interpretation.

---

## Main Inputs

The engine uses three broad categories of input:

1. **Objective recovery data**
2. **Subjective user feedback**
3. **Historical context**

Together, these allow the app to move beyond a single recovery number and provide advice that is more contextual.

---

## Objective Recovery Data

Objective recovery data is derived from the heart-rate session captured by the watch.

Examples include:

* peak heart rate during the session
* heart rate at the end of exercise
* heart rate after 60 seconds of recovery
* heart rate after 120 seconds of recovery
* first-minute heart-rate drop
* second-minute heart-rate drop
* recovery curve shape
* comparison with previous recovery values

These values describe both the intensity of the session and the speed of recovery afterwards.

A single value can be useful, but the full curve gives a richer picture. For example, the app can distinguish between a session where heart rate drops quickly and continues to recover steadily, and one where recovery is slow, delayed, or uneven.

---

## Subjective Feedback

Pulse Recovery also uses subjective inputs because heart-rate data alone does not describe the whole user experience.

The main subjective inputs are:

* **Perceived effort** — how hard the session felt.
* **Post-exercise feeling** — how well the user felt after the session.

This matters because two workouts can produce similar heart-rate numbers but feel very different to the person doing them.

For example:

* Good recovery with low perceived effort may suggest the user handled the session well.
* Good recovery with very high perceived effort may suggest a harder session than the heart-rate data alone implies.
* Weak recovery with poor post-exercise feeling may suggest caution or the need for more recovery.

Subjective feedback therefore acts as a modifier on the objective recovery interpretation.

---

## Historical Context

The engine also considers previous sessions where available.

Historical context helps the app distinguish between an isolated result and a pattern.

Examples include:

* whether recovery is improving over recent sessions
* whether recovery is stable
* whether recovery appears to be declining
* whether perceived effort is rising across similar sessions
* whether post-exercise feeling is worsening
* whether the latest result is typical or unusual for the user

This is important because recovery is naturally variable. Sleep, stress, hydration, heat, illness, workout type, and day-to-day fatigue can all affect a single result. A trend across multiple sessions is often more meaningful than one isolated measurement.

---

## Session Advice

Session advice focuses on the latest workout.

The engine considers questions such as:

* How strong was the first-minute recovery?
* Did recovery continue at two minutes?
* Was the recovery curve smooth or delayed?
* Was the session unusually intense?
* Did the session feel harder than expected?
* Did the user feel good, neutral, or poor afterwards?
* Is this result typical compared with recent sessions?

The output is a user-facing explanation of what the latest session appears to suggest.

For example, the app may indicate that the user recovered well and can consider progressing gradually. Alternatively, it may suggest holding current intensity if recovery was acceptable but the session felt unusually hard. If recovery was weak and the user felt poor afterwards, the advice may recommend caution or additional recovery.

The aim is not simply to classify the session. The aim is to explain what appears to be driving the advice.

---

## Trend Advice

Trend advice looks across multiple sessions.

The engine looks for patterns such as:

* improving recovery
* stable recovery
* declining recovery
* rising perceived effort
* worsening post-exercise feeling
* repeated signs of strain
* improved recovery across similar or harder sessions

Trend advice helps answer a different question from session advice.

Session advice asks:

> What does this workout suggest?

Trend advice asks:

> What does the pattern suggest?

This allows the app to identify whether the user appears to be adapting well, holding steady, or showing signs that training load may be exceeding recovery.

---

## Output Structure

The decision engine produces advice that can include:

* a headline recommendation
* a short explanation
* supporting reasons
* trend context
* practical next-step guidance

The headline recommendation may use simple categories such as:

* progress
* maintain
* caution
* recover

However, these categories are only the headline. The more important output is the explanation around the category.

The advice should help the user understand:

* what the latest session suggests
* what appears to be driving the result
* whether subjective feedback supports or changes the interpretation
* how the result compares with previous sessions
* whether the broader trend is positive, stable, or concerning
* how the user might approach their next workout

---

## Example Scenarios

### Strong recovery and good subjective feedback

A session shows strong first-minute and second-minute recovery. The user reports that the workout felt manageable and that they felt good afterwards.

Possible interpretation:

> The user appears to have handled the session well. If this pattern is consistent with recent results, gradual progression may be appropriate.

### Good recovery but high perceived effort

The recovery numbers look good, but the user reports that the session felt unusually hard.

Possible interpretation:

> The heart-rate recovery response is encouraging, but the high perceived effort suggests the user should avoid increasing intensity too quickly. Maintaining current workload may be more appropriate.

### Weak recovery and poor post-exercise feeling

The recovery response is weaker than expected, and the user reports feeling poor afterwards.

Possible interpretation:

> The session may have created more strain than usual. The user may benefit from a lighter next session or additional recovery.

### One weak result but stable recent history

The latest session shows weaker recovery, but previous sessions were stable and subjective feedback is not concerning.

Possible interpretation:

> This may be an isolated result rather than a meaningful trend. The app can advise the user to monitor the next session rather than overreacting.

### Declining recovery trend

Recovery values have been declining across recent sessions, and perceived effort is rising.

Possible interpretation:

> The pattern may suggest accumulated fatigue or insufficient recovery. The user may benefit from reducing intensity temporarily.

### Improving recovery trend

Recovery values are improving across recent sessions, especially where workout intensity is similar.

Possible interpretation:

> The user may be adapting well. The trend may suggest improving fitness or better recovery capacity.

---

## Example Output

A typical advice output might contain a short headline and a more detailed explanation.

```text
Recommendation: Maintain

Your recovery response was reasonable, but the session felt harder than expected. Your first-minute recovery was acceptable, and your two-minute recovery continued in the right direction, but your perceived effort score suggests that this workout created meaningful strain.

For your next session, it may be better to maintain your current intensity rather than increase workload immediately. If your recovery remains stable and the same effort starts to feel easier, progression may become more appropriate.
```

A trend advice output might look like:

```text
Trend: Improving

Your recent recovery pattern is moving in a positive direction. Across your latest sessions, your heart rate has been recovering more quickly, and your post-exercise feeling has remained stable.

This may suggest that you are adapting well to your current training load. Continue to progress gradually, while watching for signs that effort is rising faster than recovery.
```

---

## Tuning and Improvement

The decision engine can be refined over time as more sessions are reviewed.

Potential areas for improvement include:

* adjusting recovery thresholds
* improving how subjective effort modifies the advice
* improving how post-exercise feeling modifies the advice
* using more personalised baselines
* distinguishing between workout types
* identifying unusual sessions or outliers
* improving trend sensitivity
* adding clearer confidence or caution indicators

The aim is to keep improving the quality of the advice while retaining transparency and control over the core judgement.

---

## Summary

The Pulse Recovery decision engine turns heart-rate recovery data, subjective feedback, and session history into practical recovery guidance.

It provides both session-level and trend-level advice, helping the user understand the latest workout as well as their broader recovery pattern.

The value of the engine is not simply in producing a label. Its val# Pulse Recovery Decision Engine Summary

## Overview

The Pulse Recovery decision engine turns recovery data into structured, explainable advice.

It combines heart-rate recovery metrics, subjective user feedback, and previous session history to produce guidance at two levels:

* **Session advice** — what the latest workout and recovery response appear to suggest.
* **Trend advice** — how the user’s recovery pattern appears to be changing over time.

The engine is designed to help users understand not just *what* happened in a session, but what the result may mean in context and how they might approach their next workout.

---

## Role of the Decision Engine

The decision engine sits between the raw recovery data and the user-facing advice.

```text
Captured heart-rate data
        ↓
Recovery metrics
        ↓
Subjective feedback
        ↓
Previous session history
        ↓
Decision engine
        ↓
Session advice + trend advice
```

Its job is to combine several signals that would otherwise be hard for the user to interpret separately.

For example, a heart-rate recovery value may look good in isolation, but the interpretation may change if the session felt unusually hard. Similarly, one weaker session may not be especially meaningful, while a repeated decline across several sessions may suggest accumulated fatigue or under-recovery.

The decision engine brings these signals together and produces a clear, user-facing interpretation.

---

## Main Inputs

The engine uses three broad categories of input:

1. **Objective recovery data**
2. **Subjective user feedback**
3. **Historical context**

Together, these allow the app to move beyond a single recovery number and provide advice that is more contextual.

---

## Objective Recovery Data

Objective recovery data is derived from the heart-rate session captured by the watch.

Examples include:

* peak heart rate during the session
* heart rate at the end of exercise
* heart rate after 60 seconds of recovery
* heart rate after 120 seconds of recovery
* first-minute heart-rate drop
* second-minute heart-rate drop
* recovery curve shape
* comparison with previous recovery values

These values describe both the intensity of the session and the speed of recovery afterwards.

A single value can be useful, but the full curve gives a richer picture. For example, the app can distinguish between a session where heart rate drops quickly and continues to recover steadily, and one where recovery is slow, delayed, or uneven.

---

## Subjective Feedback

Pulse Recovery also uses subjective inputs because heart-rate data alone does not describe the whole user experience.

The main subjective inputs are:

* **Perceived effort** — how hard the session felt.
* **Post-exercise feeling** — how well the user felt after the session.

This matters because two workouts can produce similar heart-rate numbers but feel very different to the person doing them.

For example:

* Good recovery with low perceived effort may suggest the user handled the session well.
* Good recovery with very high perceived effort may suggest a harder session than the heart-rate data alone implies.
* Weak recovery with poor post-exercise feeling may suggest caution or the need for more recovery.

Subjective feedback therefore acts as a modifier on the objective recovery interpretation.

---

## Historical Context

The engine also considers previous sessions where available.

Historical context helps the app distinguish between an isolated result and a pattern.

Examples include:

* whether recovery is improving over recent sessions
* whether recovery is stable
* whether recovery appears to be declining
* whether perceived effort is rising across similar sessions
* whether post-exercise feeling is worsening
* whether the latest result is typical or unusual for the user

This is important because recovery is naturally variable. Sleep, stress, hydration, heat, illness, workout type, and day-to-day fatigue can all affect a single result. A trend across multiple sessions is often more meaningful than one isolated measurement.

---

## Session Advice

Session advice focuses on the latest workout.

The engine considers questions such as:

* How strong was the first-minute recovery?
* Did recovery continue at two minutes?
* Was the recovery curve smooth or delayed?
* Was the session unusually intense?
* Did the session feel harder than expected?
* Did the user feel good, neutral, or poor afterwards?
* Is this result typical compared with recent sessions?

The output is a user-facing explanation of what the latest session appears to suggest.

For example, the app may indicate that the user recovered well and can consider progressing gradually. Alternatively, it may suggest holding current intensity if recovery was acceptable but the session felt unusually hard. If recovery was weak and the user felt poor afterwards, the advice may recommend caution or additional recovery.

The aim is not simply to classify the session. The aim is to explain what appears to be driving the advice.

---

## Trend Advice

Trend advice looks across multiple sessions.

The engine looks for patterns such as:

* improving recovery
* stable recovery
* declining recovery
* rising perceived effort
* worsening post-exercise feeling
* repeated signs of strain
* improved recovery across similar or harder sessions

Trend advice helps answer a different question from session advice.

Session advice asks:

> What does this workout suggest?

Trend advice asks:

> What does the pattern suggest?

This allows the app to identify whether the user appears to be adapting well, holding steady, or showing signs that training load may be exceeding recovery.

---

## Output Structure

The decision engine produces advice that can include:

* a headline recommendation
* a short explanation
* supporting reasons
* trend context
* practical next-step guidance

The headline recommendation may use simple categories such as:

* progress
* maintain
* caution
* recover

However, these categories are only the headline. The more important output is the explanation around the category.

The advice should help the user understand:

* what the latest session suggests
* what appears to be driving the result
* whether subjective feedback supports or changes the interpretation
* how the result compares with previous sessions
* whether the broader trend is positive, stable, or concerning
* how the user might approach their next workout

---

## Example Scenarios

### Strong recovery and good subjective feedback

A session shows strong first-minute and second-minute recovery. The user reports that the workout felt manageable and that they felt good afterwards.

Possible interpretation:

> The user appears to have handled the session well. If this pattern is consistent with recent results, gradual progression may be appropriate.

### Good recovery but high perceived effort

The recovery numbers look good, but the user reports that the session felt unusually hard.

Possible interpretation:

> The heart-rate recovery response is encouraging, but the high perceived effort suggests the user should avoid increasing intensity too quickly. Maintaining current workload may be more appropriate.

### Weak recovery and poor post-exercise feeling

The recovery response is weaker than expected, and the user reports feeling poor afterwards.

Possible interpretation:

> The session may have created more strain than usual. The user may benefit from a lighter next session or additional recovery.

### One weak result but stable recent history

The latest session shows weaker recovery, but previous sessions were stable and subjective feedback is not concerning.

Possible interpretation:

> This may be an isolated result rather than a meaningful trend. The app can advise the user to monitor the next session rather than overreacting.

### Declining recovery trend

Recovery values have been declining across recent sessions, and perceived effort is rising.

Possible interpretation:

> The pattern may suggest accumulated fatigue or insufficient recovery. The user may benefit from reducing intensity temporarily.

### Improving recovery trend

Recovery values are improving across recent sessions, especially where workout intensity is similar.

Possible interpretation:

> The user may be adapting well. The trend may suggest improving fitness or better recovery capacity.

---

## Example Output

A typical advice output might contain a short headline and a more detailed explanation.

```text
Recommendation: Maintain

Your recovery response was reasonable, but the session felt harder than expected. Your first-minute recovery was acceptable, and your two-minute recovery continued in the right direction, but your perceived effort score suggests that this workout created meaningful strain.

For your next session, it may be better to maintain your current intensity rather than increase workload immediately. If your recovery remains stable and the same effort starts to feel easier, progression may become more appropriate.
```

A trend advice output might look like:

```text
Trend: Improving

Your recent recovery pattern is moving in a positive direction. Across your latest sessions, your heart rate has been recovering more quickly, and your post-exercise feeling has remained stable.

This may suggest that you are adapting well to your current training load. Continue to progress gradually, while watching for signs that effort is rising faster than recovery.
```

---

## Tuning and Improvement

The decision engine can be refined over time as more sessions are reviewed.

Potential areas for improvement include:

* adjusting recovery thresholds
* improving how subjective effort modifies the advice
* improving how post-exercise feeling modifies the advice
* using more personalised baselines
* distinguishing between workout types
* identifying unusual sessions or outliers
* improving trend sensitivity
* adding clearer confidence or caution indicators

The aim is to keep improving the quality of the advice while retaining transparency and control over the core judgement.

---

## Summary

The Pulse Recovery decision engine turns heart-rate recovery data, subjective feedback, and session history into practical recovery guidance.

It provides both session-level and trend-level advice, helping the user understand the latest workout as well as their broader recovery pattern.

The value of the engine is not simply in producing a label. Its value is in explaining what appears to be happening, what signals contributed to the advice, and how the user might approach their next workout.
