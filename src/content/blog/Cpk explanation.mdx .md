---
title: Explanation of cpk
cover: '@/assets/og-image.png'
date: '2026-07-12'
lastmod: '2026-07-12'
draft: false
summary: Explanation of cpk, red points on charts 
---

For this Process Capability Sixpack, the I Chart and Moving Range (MR) Chart are used to check whether the process is stable over time before trusting Cp/Cpk.

* I Chart (Individuals Chart) → checks process average (mean) stability
* Moving Range Chart → checks process variation stability

⸻

1. I Chart (Individuals Chart)

Purpose

The I Chart plots each individual measurement:

Example:

Sample	Measurement
1	84.2
2	84.5
3	83.9
4	84.3

Each dot = one product measurement.

It answers:

“Is the process average changing over time?”

⸻

I Chart Calculation

Step 1: Calculate Average (Center Line)

Formula:

\bar{X}=\frac{\sum X_i}{n}

From your report:

\bar{X}=84.281

This is the center line.

⸻

Step 2: Calculate Moving Range

Moving range is the difference between two consecutive measurements:

MR_i=|X_i-X_{i-1}|

Example:

Sample	Value	MR
1	84.2	-
2	84.5	0.3
3	83.9	0.6
4	84.3	0.4

⸻

Step 3: Average Moving Range

\overline{MR}=\frac{\sum MR}{n-1}

Your report:

\overline{MR}=0.358

⸻

Step 4: Estimate Process Sigma

For Individuals Chart:

\sigma=\frac{\overline{MR}}{d_2}

where:

d_2=1.128

Therefore:

\sigma=\frac{0.358}{1.128}

\sigma=0.317

This matches your report:

Within StDev = 0.3170

⸻

Step 5: Calculate Control Limits

For I Chart:

UCL=\bar{X}+3\sigma

LCL=\bar{X}-3\sigma

Your data:

UCL=84.281+3(0.317)

UCL=85.232

LCL=84.281-3(0.317)

LCL=83.330

So:

Limit	Value
UCL	85.232
Center	84.281
LCL	83.330

⸻

Red Point Criteria on I Chart

A red point means special cause variation.

Common Western Electric / Minitab rules:

Rule 1: One point outside control limits

Condition:

X_i>UCL

or

X_i<LCL

Example:

Measurement:

X_{98}=85.4

Because:

85.4>85.232

→ Red point

Meaning:

Possible causes:

* Machine adjustment
* Tool wear
* Material change
* Operator intervention
* Measurement error

⸻

Rule 2: 8 consecutive points on one side of center line

Example:

84.6  *
84.5  *
84.4  *
84.3  *
84.2  *
84.1  *
84.5  *
84.4  *
---------------- Mean

Even inside limits → abnormal.

Reason:



Random variation should move around the average.

⸻

Rule 3: Trend

Example:

84.0
84.2
84.4
84.6
84.8
85.0

7 points continuously increasing.

Possible:

* Tool degradation
* Temperature drift
* Wear

⸻

2. Moving Range Chart (MR Chart)

Purpose

MR chart checks:

“Is the variation itself stable?”

It does not look at the average value.

It looks at the distance between two measurements.

⸻

Example:

Measurements:

84.2
84.8
84.3

Moving ranges:

MR_1=|84.8-84.2|

MR_1=0.6

MR_2=|84.3-84.8|

MR_2=0.5

⸻

MR Chart Calculation

Center Line

CL=\overline{MR}

From report:

CL=0.358

⸻

Upper Control Limit

For MR chart:

UCL=D_4\times \overline{MR}

For moving range of 2:

D_4=3.267

Therefore:

UCL=3.267\times0.358

UCL=1.168

Matches report:

UCL = 1.168

⸻

Lower Control Limit

LCL=D_3\times MR

For n=2:

D_3=0

Therefore:

LCL=0

⸻

Red Point Criteria on MR Chart

Rule 1: MR point above UCL

Example:

MR_i>1.168

In your chart:

Around:

* Sample 1
* Sample 98
* Sample 123

there are red points.

Meaning:

The difference between two consecutive parts suddenly increased.

Possible causes:

Cause	Example
Machine	Unexpected adjustment
Tool	Broken/worn tool
Material	Different batch
Measurement	Fixture problem
Operator	Wrong setting

⸻

Interpretation of Your Report

Your report shows:

I Chart

✅ Most points stable
⚠️ One point above UCL (~sample 98)

MR Chart

⚠️ Several abnormal variation points

Therefore:

The process capability numbers (Cpk=1.50) are good, but:

The process is capable but not completely statistically controlled.

For automotive PPAP/IATF approval, I would require:

1. Investigate red points
2. Document root cause (8D/CAR)
3. Remove special cause if confirmed
4. Re-run capability study

A good rule:

Capability tells “Can the process make good parts?”
Control chart tells “Can the process continue making good parts?”

Both are needed for process approval.