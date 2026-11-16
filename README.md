# Workout Planner

An AI-assisted strength, conditioning and nutrition planner built around real family life. It uses Claude, set up as a strength and conditioning coach and nutritionist, to generate progressive training blocks, track progress against milestones and adapt plans when sleep, time or niggles get in the way.

## Why this exists

Most training plans assume unlimited time, perfect sleep and no aches. This one is built for people who:

- train early in the morning, before the household wakes up
- have under 60 minutes per session, warm-up and cool-down included
- sit at a desk most of the day
- have young children, so sleep and schedules are unpredictable
- want body recomposition (lose fat, build muscle) without wrecking energy

## What it does

- **Builds 4-week training blocks** with progressive overload and a lighter week every 4–6 weeks
- **Balances the week** across push, pull, legs/hinge, core and conditioning (typically 3 sessions a week)
- **Writes every session in a consistent format**: warm-up → strength/skill → conditioning (EMOM, AMRAP, couplets) → mobility/cool-down, each with timings
- **Bases loads on your benchmark lifts** (as % of working max or RPE) and updates them when you report new numbers
- **Gives a scaled option for every movement**, plus low-impact and joint-friendly swaps
- **Includes a 20–30 minute "minimum viable" session** for disrupted days
- **Adjusts after poor sleep**: under 6 hours means a lower-intensity version of the same session
- **Treats mobility as a priority**, with hip, thoracic and shoulder work in most sessions and 5–10 minute desk/home routines for rest days
- **Tracks skill goals** such as strict pull-ups and double-unders with short, regular practice blocks
- **Provides practical nutrition guidance**: high protein, a moderate calorie deficit, batch cooking and family-friendly meals, with UK supermarket references
- **Checks progress every 4 weeks** (weight, body fat, lifts, waist) and suggests changes if progress stalls for 3+ weeks
- **Suggests Apple Watch metrics** worth tracking: heart-rate zones, active calories, steps and sleep

## How it works

The planner runs as a [Claude Project](https://claude.ai):

1. **Project instructions** define the coach's role, your profile, goals, benchmarks, constraints, niggles and formatting rules.
2. **Reference files** (previous plans and workouts) are uploaded so new plans build on what you enjoyed and what you achieved, instead of repeating sessions without progression.
3. **The current training block** is saved as a project doc, with links to the published plan and progress tracker.
4. **Updates** (new lifts, weight, injuries) are given in chat; the coach uses them from then on and reminds you to update the instructions.

## Repository structure

```
.
├── README.md
├── instructions/
│   └── project-instructions.md   # Blank template: copy to my-instructions.md and fill in
├── blocks/
│   └── current-training-block.md # Active 4-week block, loads and nutrition targets
└── reference/                    # Previous plans and workouts used as context
```


## Example block

**Recomp Block 1 (4 weeks)**

| Day | Strength | Conditioning |
| --- | --- | --- |
| Mon (A) | Back squat 4×5, DB press, push-ups | 12-min EMOM: row / wall balls / skipping |
| Wed (B) | Deadlift 4×4, pull-up negatives, ring rows | 12-min AMRAP: bike / KB swings / burpees |
| Fri (C) | Bench 4×6, DB row, reverse lunges | Double-under practice, 3-round couplet |

Main lifts progress from roughly 70% to 80% of working max over weeks 1–3, followed by a lighter week 4 with skill testing and a check-in.

## Getting started

1. Create a new Claude Project.
2. Copy `instructions/project-instructions.md` to `instructions/my-instructions.md`, fill it in, and paste it into the project instructions .
3. Upload your previous plans and workouts to the project, and fill in the **Workout history and preferences** section (what you've done, what you enjoyed, what you didn't). This is how the AI suggests sessions you'll actually enjoy and stick with.
4. Ask for your first 4-week block, e.g. *"Build my first 4-week recomp block."*
5. Log sessions, report new numbers, and check in at the end of each block.

## Customising

Everything is driven by the instructions file. The key sections to edit are:

- **About me**: height, weight, body fat, age, lifestyle
- **Goals**: milestone and long-term targets
- **Benchmarks**: working or max lifts and skill levels
- **Mobility and niggles**: tight areas and any injuries, with the swaps you need
- **Training constraints**: sessions per week, time window, session length, equipment
- **Nutrition**: dietary preferences, fasting approach, staple foods

## Privacy

Your profile includes personal health data. If this repository is public, save your filled-in copy as `instructions/my-instructions.md`, which `.gitignore` keeps out of version control, and commit only the template.

## Disclaimer

This is a personal planning tool, not medical advice. If pain worsens or persists beyond 2–3 weeks, see a physiotherapist or GP before continuing.
