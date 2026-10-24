# DebateCoach: AI Feedback for Student Debaters

Building AI course project

## Summary

DebateCoach is an AI tool that gives student debaters and public speakers quick, private feedback on their speeches. It transcribes a practice speech, then checks pace, filler words and argument structure, so beginners can improve without waiting for a coach.

## Background

Debating and public speaking build confidence and critical thinking, but good feedback is hard to get:
* College clubs have few experienced coaches, and each can only review a few speakers per session
* Beginners are often too shy to practise in front of others
* Feedback is usually subjective and given after the event, when it is too late to apply
* Students who are not fluent in English can struggle to find out whether the issue is language or argument quality

I'm a CSE student with a background in ML and NLP, and I am part of a college literary and debating club. I've seen how many talented students hold back because they don't know what to improve. I wanted to build something that gives every member a practice partner.

## How is it used?

The users are club members, school students and anyone preparing for a debate, MUN or presentation. They would:

1. Record or upload a practice speech (2 to 5 minutes)
2. Receive a transcript and a short report covering:
   * Speaking pace (words per minute)
   * Filler words ("um", "like", "you know") and their count
   * Argument structure: is there a clear claim, reasons and a conclusion?
   * Vocabulary variety and sentence length
3. Practise again and compare their progress over time

Coaches and club leaders can use it as an extra tool, not a replacement. The tool is designed to be private, so students only see their own recordings.

Example report:

```
Pace: 142 wpm (good range: 120-160)
Filler words: 9 (mostly "like")
Structure: Claim found, 2 reasons found, no clear conclusion
```

## Data sources and AI methods

* **Own data**: practice speeches recorded by volunteer club members, with their written consent. Recordings stay private and are not shared in this repo
* **Public data**: a public debate or argument dataset (licence to be checked before use)

| Task | Technique |
| ---- | --------- |
| Speech to text | Open source speech recognition (e.g. Whisper) |
| Pace and filler word detection | Rule-based analysis of transcript and timestamps |
| Argument structure | Text classification of sentences as claim, reason or conclusion (e.g. fine-tuned transformer) |
| Language quality | Basic NLP features such as vocabulary variety and sentence length |

## Challenges

* Speech recognition makes more errors with strong accents and noisy rooms, which could unfairly penalise some speakers
* It cannot judge delivery qualities like body language, passion or humour
* Argument "quality" is partly subjective, so scores should be shown as suggestions, not grades
* Voice recordings are personal data, so they need consent, secure storage and easy deletion
* Over-reliance on the tool could make speakers sound formulaic

## What next?

* Support Indian languages such as Telugu and Hindi, plus mixed-language speech
* Add feedback on rebuttals during live debate practice
* Build a simple mobile or web app for club use
* Work with coaches to check that the feedback matches what experts would say

## Acknowledgments

* Elements of AI and Building AI course by Reaktor Innovations and the University of Helsinki
* Open source tools such as Whisper and Hugging Face Transformers
