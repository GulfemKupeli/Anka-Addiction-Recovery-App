<p align="center">
  <img src="icon.png" width="120" alt="Anka app icon" />
</p>

# Anka — Smoking & Alcohol Recovery App

*A judgment-free addiction support app that's simply there with you.*

> This repo hosts the project description and the App Store–required privacy policy page; the source code is not included here.

## Problem

Someone trying to quit smoking or drinking is usually left with three gaps: no concrete tool in the moment a craving hits, no clear way to see their progress, and only one path on offer — "quit completely or nothing" — with no good middle ground for people who'd rather cut back on alcohol than quit it outright.

## Solution

Anka lets users choose their own goal (for alcohol, "quit completely" or "cut back with a weekly limit"), gives in-the-moment support during cravings (breathing and grounding exercises, plus a safety net of emergency contacts), makes progress tangible through a streak counter, savings tracker, badges, and a 12-week calendar, and restarts users after a slip instead of shaming them — all running entirely on-device, with privacy by default and no account required.

## Screenshots

_Coming soon, after the first TestFlight build._

## Features

- Separate tracking for cigarettes and alcohol; for alcohol, choose **quit completely** or **cut back** with a weekly drink budget
- Real-time day/hour/savings counters and a health-milestone timeline (11 milestones for smoking, 8 for alcohol)
- **Craving SOS** modal: breathing exercise, 5-senses grounding exercise, one-tap call to an emergency contact
- A compassionate **relapse** flow — resets the counter and shows the previous streak as motivation instead of punishment
- Daily **check-ins**: mood, craving intensity, triggers, notes — past entries shown in a diary view
- A 16-badge progress system plus a 12-week color-coded progress calendar (heatmap)
- Mood–craving correlation insight and most-frequent-trigger analysis
- Instant badge notifications, a customizable daily reminder, and a weekly summary notification
- A shareable progress card
- Full Turkish / English language support (auto-selected from device locale)
- **100% local data storage** — no account, nothing ever sent to a server

## Architecture

A simple, single-layer, serverless mobile architecture:

App.tsx
└─ AppProvider (React Context + AsyncStorage)
└─ RootNavigator
├─ OnboardingScreen (first-run setup)
└─ Bottom Tabs: Home · Check-in · Stats · Settings



Notifications (daily reminders, badge celebrations, weekly summary) are scheduled entirely on-device via `expo-notifications`; no push infrastructure is used, so no device token is ever sent to a server.

## Tech Stack

| Layer | Technology |
|---|---|
| Framework | React Native + Expo SDK 54 |
| Language | TypeScript |
| Navigation | React Navigation (bottom tabs) |
| Storage | AsyncStorage (fully local) |
| Notifications | expo-notifications (local scheduling) |
| Sharing | react-native-view-shot + expo-sharing |
| Build / Distribution | EAS Build · EAS Submit |

## Status

🚧 Actively in development — preparing for TestFlight verification and App Store submission.

## Privacy

All user data stays on-device; no account is ever created. Details: [Privacy Policy](https://gulfemkupeli.github.io/Anka-Addiction-Recovery-App/privacy-policy.html)

## Developer

Gülfem Küpeli — gulfemkupeli@gmail.com
