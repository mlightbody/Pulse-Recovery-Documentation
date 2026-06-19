# Sample Session Data

## Overview

This file provides an illustrative example of the kind of structured session data Pulse Recovery might use to generate recovery advice.

The example is intended for portfolio and documentation purposes only. It is not a copy of the production data model, and the field names, structure, and values have been simplified to make the concept easier to understand.

The purpose of this example is to show how Pulse Recovery can combine:

* heart-rate recovery data
* workout context
* subjective feedback
* previous session history
* derived interpretation fields

to produce session-level and trend-level recovery advice.

---

## Important Notes

This example uses fictional or illustrative data.

It should not be interpreted as:

* a production Firebase schema
* a complete app data model
* a medical record format
* a diagnostic data structure
* a recommendation for clinical interpretation

Pulse Recovery is intended to provide fitness and recovery guidance, not medical diagnosis. Heart-rate recovery can be affected by many factors, including sleep, stress, hydration, heat, illness, caffeine, medication, workout type, and day-to-day fatigue.

---

## Example JSON

```json
{
  "sessionId": "sample-session-001",
  "userId": "example-user",
  "createdAt": "2026-06-19T10:15:00Z",
  "source": "smartwatch",
  "platform": "apple_watch",
  "workout": {
    "type": "stairs",
    "label": "Walking up and down stairs",
    "durationSeconds": 240,
    "notes": "Short high-intensity session using stairs."
  },
  "heartRateSummary": {
    "peakHeartRate": 156,
    "heartRateAtEndOfExercise": 152,
    "heartRateAfter60Seconds": 126,
    "heartRateAfter120Seconds": 112,
    "firstMinuteRecovery": 26,
    "secondMinuteRecovery": 40,
    "recoveryCurveShape": "steady_decline"
  },
  "heartRateSamples": [
    {
      "secondsFromStart": 0,
      "bpm": 94,
      "phase": "exercise"
    },
    {
      "secondsFromStart": 30,
      "bpm": 118,
      "phase": "exercise"
    },
    {
      "secondsFromStart": 60,
      "bpm": 137,
      "phase": "exercise"
    },
    {
      "secondsFromStart": 90,
      "bpm": 148,
      "phase": "exercise"
    },
    {
      "secondsFromStart": 120,
      "bpm": 156,
      "phase": "exercise"
    },
    {
      "secondsFromStart": 150,
      "bpm": 153,
      "phase": "exercise"
    },
    {
      "secondsFromStart": 180,
      "bpm": 152,
      "phase": "end_of_exercise"
    },
    {
      "secondsFromStart": 210,
      "bpm": 137,
      "phase": "recovery"
    },
    {
      "secondsFromStart": 240,
      "bpm": 126,
      "phase": "recovery_60s"
    },
    {
      "secondsFromStart": 270,
      "bpm": 118,
      "phase": "recovery"
    },
    {
      "secondsFromStart": 300,
      "bpm": 112,
      "phase": "recovery_120s"
    }
  ],
  "subjectiveInputs": {
    "perceivedEffort": 8,
    "postExerciseFeeling": 6,
    "userNotes": "Breathing was hard at the end, but I felt mostly fine after a short rest."
  },
  "historyContext": {
    "previousSessionsAvailable": true,
    "recentSessionCount": 6,
    "averageFirstMinuteRecovery": 23,
    "averageSecondMinuteRecovery": 37,
    "recoveryTrend": "slightly_improving",
    "effortTrend": "stable",
    "postExerciseFeelingTrend": "stable"
  },
  "derivedInterpretation": {
    "recoveryStrength": "good",
    "sessionStrain": "high",
    "subjectiveModifier": "caution_due_to_high_effort",
    "trendContext": "recovery_slightly_improving",
    "overallRecommendation": "maintain"
  }
}
```

---

## How This Example Is Used

This sample session can be read alongside:

```text
examples/sample-advice-output.md
```

The JSON file shows the kind of inputs and derived values the app may work with. The advice-output file shows how those values can be translated into user-facing recovery guidance.

Together, the two files demonstrate the central product idea: Pulse Recovery does not simply store heart-rate data. It interprets recovery data in context and turns it into practical advice.
