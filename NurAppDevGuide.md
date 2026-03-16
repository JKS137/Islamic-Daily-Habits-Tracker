# Nur — Islamic Daily Habits Tracker
### Full Development Guide · Solo Founder Blueprint · March 2026

> بِسْمِ اللَّهِ الرَّحْمَنِ الرَّحِيم
> 1.8 billion Muslims. Zero beautiful, minimal, faith-aligned habit tracker.
> Nur fills that gap.

---

## Table of Contents

1. [Product Overview](#1-product-overview)
2. [Market Opportunity](#2-market-opportunity)
3. [Core Value Proposition](#3-core-value-proposition)
4. [MVP Feature List](#4-mvp-feature-list)
5. [Tech Stack](#5-tech-stack)
6. [Project Structure](#6-project-structure)
7. [Database Schema](#7-database-schema)
8. [Core Code — Prayer Times Engine](#8-core-code--prayer-times-engine)
9. [Core Code — Habit Tracking Logic](#9-core-code--habit-tracking-logic)
10. [Core Code — Streak System](#10-core-code--streak-system)
11. [Core Code — Notifications](#11-core-code--notifications)
12. [Quran Reading Tracker](#12-quran-reading-tracker)
13. [Screens & Navigation Map](#13-screens--navigation-map)
14. [Monetization Strategy](#14-monetization-strategy)
15. [Revenue Projections](#15-revenue-projections)
16. [6-Week Build Timeline](#16-6-week-build-timeline)
17. [App Store Setup & ASO](#17-app-store-setup--aso)
18. [Launch Strategy](#18-launch-strategy)
19. [Post-Launch Growth](#19-post-launch-growth)
20. [Pakistan & Global Muslim Market](#20-pakistan--global-muslim-market)
21. [Ramadan Strategy — The Annual Revenue Peak](#21-ramadan-strategy--the-annual-revenue-peak)
22. [Google Stitch UI Prompt](#22-google-stitch-ui-prompt)

---

## 1. Product Overview

**App name:** Nur (نور — Arabic for "light")
**Tagline:** Your daily light. Track your ibadah, grow your faith.
**Platform:** iOS + Android (React Native / Expo)
**Target user:** Muslim millennials and Gen Z (ages 18–40) who already use habit trackers, journals, and productivity apps — but want something built for their deen, not retrofitted from a generic tracker.

### The problem in one paragraph
A Muslim wants to track their Salah, Quran reading, dhikr, fasting, and sadaqah consistently. They try Google Sheets — too ugly. They try generic habit apps (Habitica, Streaks, Notion) — not Islamic, no prayer times, no hijri calendar, no niyyah. They try existing Islamic apps (Muslim Pro, Athan) — bloated with features, no habit tracking, terrible UX. They end up using nothing and feeling guilty about it. Nur is the answer.

### What makes Nur different
- **Minimal and beautiful** — not the cluttered Islamic app aesthetic of 2012
- **Habit tracker first** — streak psychology built around Islamic acts
- **Community without social media** — family leaderboard, no public feed
- **Ramadan mode** — the entire app transforms during Ramadan (premium killer feature)
- **Offline first** — works without internet, syncs when connected

---

## 2. Market Opportunity

| Signal | Data |
|--------|------|
| Global Muslim population | 1.8 billion |
| Smartphone-using Muslims | ~900 million |
| Muslim Pro (biggest Islamic app) downloads | 100M+ |
| Muslim Gen Z / Millennial population | ~600 million |
| Willingness to pay for quality Islamic apps | High — proven by Muslim Pro premium |
| Pakistan Muslims | 230 million |
| Indonesia Muslims | 230 million |
| Combined English-speaking Muslim market | 50M+ |
| Existing beautiful minimal Islamic habit tracker | None |

**The gap:** Muslim Pro is the biggest Islamic app but it is a prayer times + Quran reader — not a habit tracker. No app exists that combines beautiful design + streak psychology + Islamic habits in one clean package. This is a wide open market.

---

## 3. Core Value Proposition

Nur gives a Muslim user five things in one place:

1. **Salah tracker** — 5 prayers per day, mark each one on time / late / qada
2. **Quran reading log** — daily pages/juz goal with progress bar
3. **Dhikr counter** — tap-to-count for morning/evening adhkar
4. **Fasting tracker** — Sunnah fasts (Monday/Thursday), Ramadan, Shawwal
5. **Streak system** — visual fire streak for consecutive days of complete ibadah

Everything else is Phase 2. Ship these five, make them beautiful, and charge $3.99/mo.

---

## 4. MVP Feature List

### Phase 1 — Ship in Week 1–4 (Core product)

- [ ] Daily dashboard: 5 Salah slots + Quran goal + Dhikr target
- [ ] Mark Salah as: On time / Late (ada) / Makeup (qada) / Missed
- [ ] Quran pages tracker (set daily goal: 1 page / 1 juz / custom)
- [ ] Dhikr counter (tap counter with preset counts: 33, 99, 100)
- [ ] Fasting log (mark today as fasting, see monthly calendar)
- [ ] Streak counter (consecutive days of complete Salah)
- [ ] Prayer time notifications (based on location)
- [ ] Hijri calendar display (alongside Gregorian)
- [ ] Offline-first (all data stored locally, no account required for MVP)
- [ ] Dark mode + calming Islamic aesthetic

### Phase 2 — Week 5–8 (Premium features)

- [ ] Ramadan mode (suhoor/iftar countdowns, special 30-day tracker)
- [ ] Family / friends leaderboard (streak competition with loved ones)
- [ ] Weekly & monthly reports (your best ibadah week, patterns)
- [ ] Morning & evening adhkar routines (guided dhikr sessions)
- [ ] Sadaqah tracker (log charity given, set monthly sadaqah goal)
- [ ] Niyyah journal (write intention before each habit entry)
- [ ] Custom habits (add your own Islamic goals: tahajjud, learning Arabic, etc.)

### Phase 3 — Month 3+ (Growth features)

- [ ] Dua list (personal dua collection with reminders)
- [ ] 99 Names of Allah daily learning (one per day with meaning)
- [ ] Islamic quotes / hadith widget (daily notification)
- [ ] Prayer community challenges (community Quran khatm tracker)
- [ ] Apple Watch / Wear OS companion (quick dhikr counter on wrist)
- [ ] Widget support (iOS/Android home screen widget showing today's Salah status)

---

## 5. Tech Stack

| Layer | Technology | Reason |
|-------|-----------|--------|
| Framework | React Native + Expo | One codebase, iOS + Android |
| Prayer times | Adhan.js (npm: adhan) | Industry-standard Islamic prayer time library, free, offline |
| Hijri calendar | npm: hijri-date | Accurate Hijri/Gregorian conversion |
| Local storage | MMKV (react-native-mmkv) | Faster than AsyncStorage, perfect for offline-first |
| Backend (Phase 2) | Supabase | Free tier, auth, real-time sync for family leaderboard |
| Auth | Supabase Auth (email / Google / Apple) | Frictionless signup |
| Notifications | Expo Notifications | Prayer time alerts + streak reminders |
| Location | Expo Location | One-time permission for prayer time calculation |
| State | Zustand | Lightweight, no Redux boilerplate |
| Navigation | Expo Router | File-based, clean, deep linking |
| Analytics | PostHog | Free 1M events/mo |
| Animations | React Native Reanimated | Smooth streak animations, transitions |
| Charts | Victory Native | Streak history, weekly ibadah charts |

**Monthly infra cost at MVP: $0**
MMKV + Expo = everything runs on device, zero server needed for Phase 1.

---

## 6. Project Structure

```
nur/
├── app/
│   ├── (auth)/
│   │   ├── welcome.tsx          # Onboarding — language, location, madhab
│   │   ├── setup.tsx            # Set daily goals (pages/day, dhikr target)
│   │   └── login.tsx            # Optional account (for cloud sync)
│   │
│   ├── (tabs)/
│   │   ├── index.tsx            # Today dashboard (main screen)
│   │   ├── quran.tsx            # Quran reading progress
│   │   ├── dhikr.tsx            # Dhikr counter screen
│   │   ├── calendar.tsx         # Monthly ibadah calendar (Hijri)
│   │   └── profile.tsx          # Stats, streak history, settings
│   │
│   ├── ramadan/
│   │   ├── index.tsx            # Ramadan dashboard (premium)
│   │   ├── tracker.tsx          # 30-day Ramadan tracker
│   │   └── suhoor.tsx           # Suhoor/Iftar countdown
│   │
│   └── family/
│       ├── index.tsx            # Family leaderboard (premium)
│       └── invite.tsx           # Invite family member
│
├── components/
│   ├── SalahCard.tsx            # Individual prayer slot card
│   ├── StreakBadge.tsx          # Fire streak display
│   ├── PrayerTimesBar.tsx       # Next prayer countdown
│   ├── QuranProgressRing.tsx    # Circular progress for pages
│   ├── DhikrCounter.tsx         # Tap counter with haptics
│   ├── HijriDate.tsx            # Hijri date display component
│   ├── IbadahCalendar.tsx       # Monthly dot calendar
│   ├── RamadanCountdown.tsx     # Days until / into Ramadan
│   └── PremiumGate.tsx          # Paywall wrapper
│
├── lib/
│   ├── prayer-times.ts          # Adhan.js wrapper
│   ├── hijri.ts                 # Hijri date utilities
│   ├── storage.ts               # MMKV read/write helpers
│   ├── streak.ts                # Streak calculation logic
│   ├── notifications.ts         # Prayer time + streak notifications
│   └── ramadan.ts               # Ramadan date detection + features
│
├── store/
│   ├── habits.ts                # Zustand — daily habit state
│   ├── settings.ts              # User preferences
│   └── streak.ts                # Streak state
│
├── hooks/
│   ├── usePrayerTimes.ts        # Prayer times for user location
│   ├── useTodayHabits.ts        # Today's completion state
│   ├── useStreak.ts             # Current streak + history
│   └── useHijriDate.ts          # Today's Hijri date
│
└── constants/
    ├── prayers.ts               # Prayer names in Arabic + English
    ├── adhkar.ts                # Morning/evening dhikr text + counts
    ├── colors.ts                # Theme colors (light + dark)
    └── config.ts
```

---

## 7. Database Schema

### Local Storage (MMKV) — MVP
All MVP data is stored on-device. No account required.

```typescript
// Storage key structure
// "habits:2026-03-17"   → DailyRecord for that date
// "settings"            → UserSettings
// "streak"              → StreakData
// "quran:progress"      → QuranProgress

// -------------------------------------------------------
// TYPES
// -------------------------------------------------------

export type SalahStatus = 'pending' | 'on_time' | 'late' | 'qada' | 'missed';
export type Prayer = 'fajr' | 'dhuhr' | 'asr' | 'maghrib' | 'isha';

export interface DailyRecord {
  date: string;                        // ISO: "2026-03-17"
  hijriDate: string;                   // "17 Ramadan 1447"
  salah: Record<Prayer, SalahStatus>;
  quranPagesRead: number;
  dhikrMorningDone: boolean;
  dhikrEveningDone: boolean;
  fasting: boolean;
  tahajjud: boolean;
  sadaqah: number;                     // amount given
  notes?: string;
  completedAt?: string;                // ISO timestamp when all goals met
}

export interface UserSettings {
  name: string;
  location: { lat: number; lng: number; city: string };
  calculationMethod: string;           // 'MWL' | 'ISNA' | 'Egypt' | 'Karachi' | 'Tehran'
  madhab: 'hanafi' | 'shafi' | 'maliki' | 'hanbali';
  dailyQuranGoal: number;              // pages
  dailyDhikrGoal: number;             // count
  language: 'en' | 'ur' | 'ar';
  theme: 'light' | 'dark' | 'auto';
  isPremium: boolean;
  premiumExpiresAt?: string;
  notificationsEnabled: boolean;
  adhanEnabled: boolean;
  streakReminderTime: string;          // "21:00"
}

export interface StreakData {
  currentStreak: number;
  longestStreak: number;
  lastCompletedDate: string;
  totalDaysTracked: number;
  totalSalahCompleted: number;
  totalQuranPages: number;
}

export interface QuranProgress {
  currentJuz: number;
  currentSurah: number;
  currentAyah: number;
  totalPagesRead: number;
  khatmCount: number;                  // times completed full Quran
  startedAt: string;
}
```

### Cloud Schema (Supabase) — Phase 2

```sql
-- ============================================================
-- NUR APP — SUPABASE SCHEMA
-- Phase 2: cloud sync + family leaderboard
-- ============================================================

create extension if not exists "uuid-ossp";

-- ============================================================
-- PROFILES
-- ============================================================
create table profiles (
  id uuid references auth.users primary key,
  display_name text,
  avatar_seed text,                    -- for generated avatars
  calculation_method text default 'Karachi',
  madhab text default 'hanafi',
  city text,
  country text,
  timezone text,
  language text default 'en',
  is_premium boolean default false,
  premium_expires_at timestamptz,
  total_streak_days integer default 0,
  longest_streak integer default 0,
  total_quran_pages integer default 0,
  joined_at timestamptz default now()
);

-- ============================================================
-- DAILY RECORDS (synced from device)
-- ============================================================
create table daily_records (
  id uuid primary key default uuid_generate_v4(),
  user_id uuid references profiles not null,
  date date not null,
  hijri_date text,
  fajr_status text default 'pending',
  dhuhr_status text default 'pending',
  asr_status text default 'pending',
  maghrib_status text default 'pending',
  isha_status text default 'pending',
  quran_pages_read integer default 0,
  dhikr_morning boolean default false,
  dhikr_evening boolean default false,
  fasting boolean default false,
  tahajjud boolean default false,
  sadaqah numeric(10,2) default 0,
  notes text,
  ibadah_score integer generated always as (
    case when fajr_status = 'on_time' then 2
         when fajr_status = 'late' then 1 else 0 end +
    case when dhuhr_status = 'on_time' then 2
         when dhuhr_status = 'late' then 1 else 0 end +
    case when asr_status = 'on_time' then 2
         when asr_status = 'late' then 1 else 0 end +
    case when maghrib_status = 'on_time' then 2
         when maghrib_status = 'late' then 1 else 0 end +
    case when isha_status = 'on_time' then 2
         when isha_status = 'late' then 1 else 0 end +
    case when dhikr_morning then 2 else 0 end +
    case when dhikr_evening then 2 else 0 end +
    least(quran_pages_read, 5) +       -- max 5 points for Quran
    case when fasting then 3 else 0 end +
    case when tahajjud then 3 else 0 end
  ) stored,
  synced_at timestamptz default now(),
  unique(user_id, date)
);

-- ============================================================
-- FAMILY GROUPS (for leaderboard)
-- ============================================================
create table family_groups (
  id uuid primary key default uuid_generate_v4(),
  name text not null,
  created_by uuid references profiles,
  invite_code text unique default upper(substring(gen_random_uuid()::text, 1, 6)),
  created_at timestamptz default now()
);

create table family_members (
  group_id uuid references family_groups on delete cascade,
  user_id uuid references profiles,
  role text default 'member',
  joined_at timestamptz default now(),
  primary key (group_id, user_id)
);

-- ============================================================
-- STREAK RECORDS
-- ============================================================
create table streak_records (
  user_id uuid references profiles primary key,
  current_streak integer default 0,
  longest_streak integer default 0,
  last_completed_date date,
  updated_at timestamptz default now()
);

-- ============================================================
-- ROW LEVEL SECURITY
-- ============================================================
alter table profiles enable row level security;
alter table daily_records enable row level security;
alter table family_groups enable row level security;
alter table family_members enable row level security;
alter table streak_records enable row level security;

create policy "own_profile" on profiles for all using (auth.uid() = id);
create policy "own_records" on daily_records for all using (auth.uid() = user_id);
create policy "own_streak" on streak_records for all using (auth.uid() = user_id);

-- Family: members can see each other's data (for leaderboard)
create policy "family_records" on daily_records for select using (
  user_id in (
    select fm.user_id from family_members fm
    where fm.group_id in (
      select group_id from family_members where user_id = auth.uid()
    )
  )
);
```

---

## 8. Core Code — Prayer Times Engine

```typescript
// lib/prayer-times.ts
// Uses the 'adhan' npm package — most accurate Islamic prayer time library

import { Coordinates, CalculationMethod, PrayerTimes, Prayer, Madhab, HighLatitudeRule } from 'adhan';

export type CalculationMethodName =
  | 'MuslimWorldLeague'
  | 'NorthAmerica'
  | 'Egyptian'
  | 'Karachi'
  | 'UmmAlQura'
  | 'Dubai'
  | 'MoonsightingCommittee'
  | 'Turkey';

export interface PrayerTimesResult {
  fajr: Date;
  sunrise: Date;
  dhuhr: Date;
  asr: Date;
  maghrib: Date;
  isha: Date;
  nextPrayer: Prayer;
  nextPrayerTime: Date;
  minutesUntilNext: number;
}

export function getPrayerTimes(
  lat: number,
  lng: number,
  date: Date = new Date(),
  methodName: CalculationMethodName = 'Karachi',
  madhab: 'hanafi' | 'shafi' = 'hanafi'
): PrayerTimesResult {
  const coordinates = new Coordinates(lat, lng);

  const params = CalculationMethod[methodName]();
  params.madhab = madhab === 'hanafi' ? Madhab.Hanafi : Madhab.Shafi;
  params.highLatitudeRule = HighLatitudeRule.MiddleOfTheNight;

  const times = new PrayerTimes(coordinates, date, params);

  const nextPrayer = times.nextPrayer();
  const nextPrayerTime = times.timeForPrayer(nextPrayer);
  const minutesUntilNext = Math.floor(
    (nextPrayerTime.getTime() - Date.now()) / (1000 * 60)
  );

  return {
    fajr: times.fajr,
    sunrise: times.sunrise,
    dhuhr: times.dhuhr,
    asr: times.asr,
    maghrib: times.maghrib,
    isha: times.isha,
    nextPrayer,
    nextPrayerTime,
    minutesUntilNext,
  };
}

export function formatPrayerTime(date: Date): string {
  return date.toLocaleTimeString('en-US', {
    hour: '2-digit',
    minute: '2-digit',
    hour12: true,
  });
}

export function getPrayerDisplayName(prayer: Prayer, language: 'en' | 'ur' | 'ar'): string {
  const names: Record<Prayer, Record<string, string>> = {
    fajr:    { en: 'Fajr',    ur: 'فجر',   ar: 'الفجر'   },
    dhuhr:   { en: 'Dhuhr',   ur: 'ظہر',   ar: 'الظهر'   },
    asr:     { en: 'Asr',     ur: 'عصر',   ar: 'العصر'   },
    maghrib: { en: 'Maghrib', ur: 'مغرب',  ar: 'المغرب'  },
    isha:    { en: 'Isha',    ur: 'عشاء',  ar: 'العشاء'  },
    sunrise: { en: 'Sunrise', ur: 'طلوع',  ar: 'الشروق'  },
  };
  return names[prayer]?.[language] ?? prayer;
}

// Install: npm install adhan
```

---

## 9. Core Code — Habit Tracking Logic

```typescript
// lib/storage.ts
import { MMKV } from 'react-native-mmkv';
import { DailyRecord, Prayer, SalahStatus, StreakData } from '../types';

const storage = new MMKV();

const dateKey = (date: string) => `habits:${date}`;
const todayKey = () => dateKey(new Date().toISOString().split('T')[0]);

// -------------------------------------------------------
// DAILY RECORDS
// -------------------------------------------------------

export function getDailyRecord(date: string): DailyRecord {
  const raw = storage.getString(dateKey(date));
  if (raw) return JSON.parse(raw);

  // Return empty record for the day
  return {
    date,
    hijriDate: '',
    salah: {
      fajr: 'pending',
      dhuhr: 'pending',
      asr: 'pending',
      maghrib: 'pending',
      isha: 'pending',
    },
    quranPagesRead: 0,
    dhikrMorningDone: false,
    dhikrEveningDone: false,
    fasting: false,
    tahajjud: false,
    sadaqah: 0,
  };
}

export function updateSalahStatus(
  date: string,
  prayer: Prayer,
  status: SalahStatus
): DailyRecord {
  const record = getDailyRecord(date);
  record.salah[prayer] = status;
  storage.set(dateKey(date), JSON.stringify(record));
  return record;
}

export function updateQuranPages(date: string, pages: number): DailyRecord {
  const record = getDailyRecord(date);
  record.quranPagesRead = pages;
  storage.set(dateKey(date), JSON.stringify(record));
  return record;
}

export function toggleDhikr(date: string, session: 'morning' | 'evening'): DailyRecord {
  const record = getDailyRecord(date);
  if (session === 'morning') record.dhikrMorningDone = !record.dhikrMorningDone;
  else record.dhikrEveningDone = !record.dhikrEveningDone;
  storage.set(dateKey(date), JSON.stringify(record));
  return record;
}

export function toggleFasting(date: string): DailyRecord {
  const record = getDailyRecord(date);
  record.fasting = !record.fasting;
  storage.set(dateKey(date), JSON.stringify(record));
  return record;
}

// -------------------------------------------------------
// IBADAH SCORE (0–100 scale)
// -------------------------------------------------------

export function calculateIbadahScore(record: DailyRecord): number {
  let score = 0;

  // Salah: 10 points each (on time = 10, late = 6, qada = 3, missed = 0)
  const salahScores: Record<SalahStatus, number> = {
    on_time: 10, late: 6, qada: 3, missed: 0, pending: 0,
  };
  Object.values(record.salah).forEach(status => {
    score += salahScores[status];
  });
  // Max salah = 50 points

  if (record.dhikrMorningDone) score += 10;
  if (record.dhikrEveningDone) score += 10;
  if (record.quranPagesRead >= 1) score += Math.min(record.quranPagesRead * 5, 20);
  if (record.fasting) score += 5;
  if (record.tahajjud) score += 5;
  // Max total = 100

  return Math.min(score, 100);
}

export function isDayComplete(record: DailyRecord, quranGoal: number): boolean {
  const allSalahDone = Object.values(record.salah).every(
    s => s === 'on_time' || s === 'late' || s === 'qada'
  );
  const quranDone = record.quranPagesRead >= quranGoal;
  return allSalahDone && quranDone;
}

// -------------------------------------------------------
// HISTORY & STATS
// -------------------------------------------------------

export function getLast30Days(): DailyRecord[] {
  const records: DailyRecord[] = [];
  for (let i = 0; i < 30; i++) {
    const date = new Date();
    date.setDate(date.getDate() - i);
    const dateStr = date.toISOString().split('T')[0];
    records.push(getDailyRecord(dateStr));
  }
  return records;
}
```

---

## 10. Core Code — Streak System

```typescript
// lib/streak.ts
import { MMKV } from 'react-native-mmkv';
import { getDailyRecord, isDayComplete } from './storage';
import { StreakData } from '../types';

const storage = new MMKV();
const STREAK_KEY = 'streak_data';

export function getStreakData(): StreakData {
  const raw = storage.getString(STREAK_KEY);
  if (raw) return JSON.parse(raw);
  return {
    currentStreak: 0,
    longestStreak: 0,
    lastCompletedDate: '',
    totalDaysTracked: 0,
    totalSalahCompleted: 0,
    totalQuranPages: 0,
  };
}

export function recalculateStreak(quranGoal: number): StreakData {
  const streak = getStreakData();
  const today = new Date().toISOString().split('T')[0];
  const todayRecord = getDailyRecord(today);

  // Check if today is complete
  const todayComplete = isDayComplete(todayRecord, quranGoal);

  if (todayComplete) {
    const yesterday = new Date();
    yesterday.setDate(yesterday.getDate() - 1);
    const yesterdayStr = yesterday.toISOString().split('T')[0];

    const isConsecutive =
      streak.lastCompletedDate === yesterdayStr ||
      streak.lastCompletedDate === today;

    if (isConsecutive || streak.currentStreak === 0) {
      streak.currentStreak = streak.lastCompletedDate === today
        ? streak.currentStreak
        : streak.currentStreak + 1;
    } else {
      // Streak broken — reset
      streak.currentStreak = 1;
    }

    streak.lastCompletedDate = today;
    streak.longestStreak = Math.max(streak.longestStreak, streak.currentStreak);
  }

  // Recalculate totals from last 30 days
  let totalSalah = 0;
  let totalPages = 0;
  for (let i = 0; i < 30; i++) {
    const date = new Date();
    date.setDate(date.getDate() - i);
    const record = getDailyRecord(date.toISOString().split('T')[0]);
    totalSalah += Object.values(record.salah).filter(s => s !== 'pending' && s !== 'missed').length;
    totalPages += record.quranPagesRead;
  }
  streak.totalSalahCompleted = totalSalah;
  streak.totalQuranPages = totalPages;

  storage.set(STREAK_KEY, JSON.stringify(streak));
  return streak;
}

export function getStreakMessage(streak: number): string {
  if (streak === 0) return 'Start your streak today';
  if (streak === 1) return 'MashaAllah! Day 1';
  if (streak < 7) return `${streak} days — keep going!`;
  if (streak < 14) return `${streak} days — SubhanAllah!`;
  if (streak < 30) return `${streak} days — AlhamdulAllah!`;
  if (streak < 100) return `${streak} days — MashaAllah!`;
  return `${streak} days — AlhamdulAllah! You are consistent!`;
}
```

---

## 11. Core Code — Notifications

```typescript
// lib/notifications.ts
import * as Notifications from 'expo-notifications';
import { getPrayerTimes, formatPrayerTime } from './prayer-times';
import { Prayer } from 'adhan';

Notifications.setNotificationHandler({
  handleNotification: async () => ({
    shouldShowAlert: true,
    shouldPlaySound: true,
    shouldSetBadge: true,
  }),
});

export async function schedulePrayerTimeNotifications(
  lat: number,
  lng: number,
  methodName: string,
  madhab: 'hanafi' | 'shafi'
) {
  // Schedule for next 7 days to stay accurate
  await Notifications.cancelAllScheduledNotificationsAsync();

  const prayers: Prayer[] = ['fajr', 'dhuhr', 'asr', 'maghrib', 'isha'];
  const prayerMessages: Record<string, { en: string; ur: string }> = {
    fajr:    { en: 'Fajr time — begin your day with Allah', ur: 'فجر کا وقت ہو گیا' },
    dhuhr:   { en: 'Dhuhr time — pause and pray', ur: 'ظہر کا وقت ہو گیا' },
    asr:     { en: 'Asr time — do not delay', ur: 'عصر کا وقت ہو گیا' },
    maghrib: { en: 'Maghrib time — sunset prayer', ur: 'مغرب کا وقت ہو گیا' },
    isha:    { en: 'Isha time — end your day with gratitude', ur: 'عشاء کا وقت ہو گیا' },
  };

  for (let dayOffset = 0; dayOffset < 7; dayOffset++) {
    const date = new Date();
    date.setDate(date.getDate() + dayOffset);

    const times = getPrayerTimes(lat, lng, date, methodName as any, madhab);

    for (const prayer of prayers) {
      const prayerTime = times[prayer as keyof typeof times] as Date;
      if (prayerTime > new Date()) {
        await Notifications.scheduleNotificationAsync({
          identifier: `prayer-${prayer}-${date.toISOString().split('T')[0]}`,
          content: {
            title: `🕌 ${prayer.charAt(0).toUpperCase() + prayer.slice(1)}`,
            body: prayerMessages[prayer].en,
            data: { type: 'prayer', prayer },
            sound: 'adhan.wav', // include adhan sound in assets
          },
          trigger: { date: prayerTime },
        });
      }
    }
  }
}

// Streak reminder — gentle evening nudge if not all salah done
export async function scheduleStreakReminder(time: string = '21:00') {
  const [hours, minutes] = time.split(':').map(Number);

  await Notifications.scheduleNotificationAsync({
    identifier: 'streak-reminder',
    content: {
      title: 'Complete your ibadah today',
      body: "Don't break your streak — a few minutes left in the day",
      data: { type: 'streak_reminder' },
    },
    trigger: {
      hour: hours,
      minute: minutes,
      repeats: true,
    },
  });
}

// Fajr wake-up reminder (15 mins before Fajr)
export async function scheduleFajrWakeup(fajrTime: Date) {
  const wakeupTime = new Date(fajrTime.getTime() - 15 * 60 * 1000);
  if (wakeupTime > new Date()) {
    await Notifications.scheduleNotificationAsync({
      identifier: 'fajr-wakeup',
      content: {
        title: '🌙 Fajr in 15 minutes',
        body: 'Wake up for the best prayer of the day',
        data: { type: 'fajr_wakeup' },
      },
      trigger: { date: wakeupTime },
    });
  }
}
```

---

## 12. Quran Reading Tracker

```typescript
// lib/quran.ts
import { MMKV } from 'react-native-mmkv';
import { QuranProgress } from '../types';

const storage = new MMKV();
const QURAN_KEY = 'quran:progress';

// Quran has 604 pages (standard Madina Mushaf) and 30 juz
export const QURAN_TOTAL_PAGES = 604;
export const QURAN_TOTAL_JUZ = 30;

export const JUZ_PAGES: Record<number, { start: number; end: number }> = {
  1:  { start: 1,   end: 21  },
  2:  { start: 22,  end: 41  },
  3:  { start: 42,  end: 61  },
  4:  { start: 62,  end: 81  },
  5:  { start: 82,  end: 101 },
  6:  { start: 102, end: 121 },
  7:  { start: 122, end: 141 },
  8:  { start: 142, end: 161 },
  9:  { start: 162, end: 181 },
  10: { start: 182, end: 201 },
  // ... remaining juz
  30: { start: 582, end: 604 },
};

export function getQuranProgress(): QuranProgress {
  const raw = storage.getString(QURAN_KEY);
  if (raw) return JSON.parse(raw);
  return {
    currentJuz: 1,
    currentSurah: 1,
    currentAyah: 1,
    totalPagesRead: 0,
    khatmCount: 0,
    startedAt: new Date().toISOString(),
  };
}

export function updateQuranProgress(pagesRead: number): QuranProgress {
  const progress = getQuranProgress();
  progress.totalPagesRead += pagesRead;

  // Check for khatm completion
  if (progress.totalPagesRead >= QURAN_TOTAL_PAGES * (progress.khatmCount + 1)) {
    progress.khatmCount += 1;
  }

  // Update current juz
  const overallPage = progress.totalPagesRead % QURAN_TOTAL_PAGES || QURAN_TOTAL_PAGES;
  for (const [juz, range] of Object.entries(JUZ_PAGES)) {
    if (overallPage >= range.start && overallPage <= range.end) {
      progress.currentJuz = Number(juz);
      break;
    }
  }

  storage.set(QURAN_KEY, JSON.stringify(progress));
  return progress;
}

export function getKhatmProgress(): number {
  const progress = getQuranProgress();
  const pagesInCurrentKhatm = progress.totalPagesRead % QURAN_TOTAL_PAGES;
  return Math.round((pagesInCurrentKhatm / QURAN_TOTAL_PAGES) * 100);
}

export function daysToCompleteKhatm(dailyGoal: number): number {
  const progress = getQuranProgress();
  const remainingPages = QURAN_TOTAL_PAGES - (progress.totalPagesRead % QURAN_TOTAL_PAGES);
  return Math.ceil(remainingPages / dailyGoal);
}
```

---

## 13. Screens & Navigation Map

```
App
├── Onboarding (first launch)
│   ├── WelcomeScreen          — "Your daily light" hero + language picker
│   ├── LocationScreen         — "Allow location for accurate prayer times"
│   ├── SetupScreen            — Madhab, calculation method
│   └── GoalsScreen            — Daily Quran goal, dhikr target
│
└── Main Tab Navigator
    │
    ├── Tab: Today (index) — MAIN SCREEN
    │   ├── Header: Hijri date + Gregorian date
    │   ├── Next prayer countdown banner: "Maghrib in 47 minutes · 6:23 PM"
    │   ├── Streak badge: flame icon + "14 days"
    │   ├── SALAH SECTION:
    │   │   ├── Fajr card      [On Time ✓] [Late] [Qada] [✗]
    │   │   ├── Dhuhr card     [On Time ✓] [Late] [Qada] [✗]
    │   │   ├── Asr card       [On Time ✓] [Late] [Qada] [✗]
    │   │   ├── Maghrib card   [Pending — 47 min away]
    │   │   └── Isha card      [Pending — 2h 12min away]
    │   ├── QURAN SECTION:
    │   │   ├── Progress ring: "2/5 pages today"
    │   │   ├── +1 page / +5 pages buttons
    │   │   └── "Juz 12 · Khatm 42%"
    │   ├── DHIKR SECTION:
    │   │   ├── Morning adhkar checkbox
    │   │   └── Evening adhkar checkbox
    │   └── Fasting toggle (Sunnah fast today?)
    │
    ├── Tab: Quran
    │   ├── Khatm progress ring (large, center screen)
    │   ├── "Day X of your Quran journey"
    │   ├── Juz progress (Juz 12 of 30)
    │   ├── Daily goal tracker (2/5 pages)
    │   ├── "+1 Page" "+5 Pages" "+1 Juz" buttons
    │   ├── Log history (last 30 days, pages per day bar chart)
    │   └── "At this pace, complete in X days"
    │
    ├── Tab: Dhikr (Counter)
    │   ├── Large circular counter display
    │   ├── Current dhikr text (Arabic + translation)
    │   ├── Tap anywhere on screen = +1 count
    │   ├── Preset targets: 33 | 99 | 100 | Custom
    │   ├── Haptic feedback on each tap
    │   ├── Reset button
    │   ├── Dhikr library (SubhanAllah, Alhamdulillah, Allahu Akbar, Astaghfirullah...)
    │   └── Morning / Evening adhkar full session mode [PREMIUM]
    │
    ├── Tab: Calendar
    │   ├── Hijri month header ("Sha'ban 1447")
    │   ├── Monthly calendar grid:
    │   │   ├── Green dot = all 5 salah completed
    │   │   ├── Amber dot = partial salah
    │   │   ├── Red dot = mostly missed
    │   │   └── Gray = no data / future
    │   ├── Today selected — shows day detail below:
    │   │   ├── Ibadah score (out of 100)
    │   │   ├── Salah breakdown
    │   │   └── Quran pages read
    │   └── Month summary: "This month: 18/28 complete days · 87 pages read"
    │
    └── Tab: Profile / Stats
        ├── Streak section: current streak, longest streak, flame animation
        ├── Monthly stats grid:
        │   ├── Total salah completed
        │   ├── Total Quran pages
        │   ├── Fasting days
        │   └── Ibadah score average
        ├── Family leaderboard (premium)
        ├── Settings:
        │   ├── Calculation method
        │   ├── Madhab
        │   ├── Notification settings
        │   ├── Language (EN/UR/AR)
        │   └── Subscription
        └── Upgrade to Premium CTA

── Ramadan Mode (auto-activates / manual toggle) [PREMIUM]
    ├── RamadanDashboard
    │   ├── Day X of Ramadan header
    │   ├── Suhoor countdown / Iftar countdown (large)
    │   ├── 30-day tracker (each day: fasted + tarawih + quran)
    │   ├── Ramadan Quran goal (complete khatm by Eid)
    │   └── Laylatul Qadr countdown (last 10 nights highlighted)
    └── SuhoorScreen
        ├── Alarm setter for tomorrow's suhoor
        └── Fajr time prominently displayed
```

---

## 14. Monetization Strategy

### Pricing

| Plan | Price | What's included | Target user |
|------|-------|----------------|-------------|
| Free | $0 | All 5 core habits, streak, basic stats | Try before buy |
| Premium Monthly | $3.99/mo | Everything — Ramadan mode, family, reports | Regular user |
| Premium Annual | $29.99/yr | Same + save 37% | Committed user |
| Lifetime | $49.99 one-time | Forever access | Highly engaged |

### Why $3.99/mo works

Islamic apps have proven price tolerance. Muslim Pro charges $19.99/year and has millions of paying users. At $3.99/mo ($47.88/yr), Nur is cheaper than Muslim Pro while being more focused and beautiful. Users who track their Salah daily are deeply motivated — they will pay for a tool that supports their spiritual growth.

### The Ramadan monetization spike

Ramadan is to Islamic apps what Christmas is to retail. **During Ramadan:**
- Downloads spike 300–500% for any Islamic app
- User motivation is at its absolute peak
- Ramadan mode is the #1 reason users upgrade to premium

**Strategy:** Make Ramadan mode completely free for the first week of Ramadan, then gate it. Capture the spike, convert the committed.

### RevenueCat product IDs

```
nur_premium_monthly    → $3.99/mo
nur_premium_annual     → $29.99/yr
nur_lifetime           → $49.99 one-time
```

### Additional revenue streams

- **Custom dhikr packs** — curated adhkar collections (PKR 300 / $1.99 one-time)
- **Ramadan planner PDF** — printable 30-day planner (free with premium, or $0.99)
- **Islamic learning modules** — 99 Names, Surah memorization add-on ($1.99/mo)
- **B2B: Masjid / Islamic school edition** — leaderboard for entire congregation ($49/mo)

---

## 15. Revenue Projections

| Scenario | Monthly Downloads | Conversion | Paying Users | MRR | Net (after 30%) |
|----------|------------------|-----------|--------------|-----|----------------|
| Conservative | 1,000/mo | 5% | 150 | $598 | $419 |
| Realistic | 5,000/mo | 7% | 700 | $2,793 | $1,955 |
| Growth | 15,000/mo | 8% | 2,400 | $9,576 | $6,703 |
| Ramadan peak | +50,000 in 30 days | 12% | +6,000 | +$23,940 | +$16,758 |

**The Ramadan multiplier is real.** Muslim Pro, Athan, and Quran apps all report their highest download and revenue months during Ramadan. A single Ramadan can generate 3–6 months of normal revenue in 30 days.

**12-month realistic target:**
- Month 1–2: 200 paying users → $800 MRR
- Month 3 (pre-Ramadan push): 500 paying users → $2,000 MRR
- Ramadan month: +2,000 new paid → $10,000+ MRR spike
- Month 8: 1,500 steady paying users → $6,000 MRR

---

## 16. Six-Week Build Timeline

### Week 1 — Foundation + Prayer Times
- [ ] `npx create-expo-app nur --template expo-router`
- [ ] Install: `adhan`, `react-native-mmkv`, `expo-notifications`, `expo-location`
- [ ] Onboarding flow: language → location → madhab → goals
- [ ] Prayer times engine with Adhan.js (`lib/prayer-times.ts`)
- [ ] MMKV storage helpers (`lib/storage.ts`)
- [ ] Basic tab navigation structure

### Week 2 — Core habit tracking
- [ ] Today dashboard screen with 5 salah cards
- [ ] Mark salah as on time / late / qada / missed (4-state toggle)
- [ ] Quran pages tracker with progress ring
- [ ] Dhikr counter screen (tap counter + haptics)
- [ ] Fasting toggle
- [ ] Save all state to MMKV

### Week 3 — Streak system + Calendar
- [ ] Streak calculation (`lib/streak.ts`)
- [ ] Streak badge with fire animation (React Native Reanimated)
- [ ] Monthly calendar with colored dot system
- [ ] Ibadah score calculation
- [ ] Hijri date display

### Week 4 — Notifications + Polish + Paywall
- [ ] Prayer time push notifications (7-day lookahead)
- [ ] Streak evening reminder
- [ ] Fajr wake-up notification
- [ ] RevenueCat setup (create products in App Store Connect)
- [ ] PremiumGate component
- [ ] App icon, splash, theme (dark + light mode)

### Week 5 — Submission
- [ ] App Store screenshots (use simulator + Figma frames)
- [ ] App Store description + keywords
- [ ] Privacy policy page
- [ ] Submit to Apple + Google Play
- [ ] Fix review feedback

### Week 6 — Soft launch
- [ ] Share in 5 Muslim WhatsApp groups personally
- [ ] Post on Instagram with 30-second screen recording
- [ ] Post on r/islam, r/MuslimLounge with genuine story
- [ ] Facebook Islamic groups (Pakistan + diaspora)
- [ ] Collect first 20 App Store reviews

---

## 17. App Store Setup & ASO

### Keywords (iOS — 100 char limit)

```
salah,prayer,quran,islamic,muslim,dhikr,ramadan,tracker,habit,fasting,tasbih,ibadah
```

### App Store description

```
Nur is the Islamic habit tracker you have been looking for.

Beautiful. Minimal. Built for your deen — not retrofitted from a generic app.

TRACK YOUR DAILY IBADAH:
• 5 daily prayers — mark Fajr, Dhuhr, Asr, Maghrib, Isha as on time, late, or qada
• Quran reading — set your daily pages goal and track your khatm progress
• Dhikr counter — tap counter for morning and evening adhkar
• Fasting — log Sunnah and Ramadan fasts
• Streaks — build a habit with consecutive day tracking

ACCURATE PRAYER TIMES:
• Location-based times using the world's most accurate calculation methods
• Supports Hanafi and Shafi madhabs
• Calculation methods: Karachi, MWL, ISNA, Egyptian, Umm Al-Qura, and more
• Push notification for each prayer time

PREMIUM FEATURES:
• Ramadan mode — suhoor/iftar countdowns, 30-day tracker, Laylatul Qadr
• Family leaderboard — compete in ibadah with loved ones
• Monthly reports — see your patterns, your best weeks
• Guided morning & evening adhkar sessions
• Custom habit tracking

No account needed. Offline first. Free to start.

اللَّهُمَّ أَعِنَّا عَلَى ذِكْرِكَ وَشُكْرِكَ وَحُسْنِ عِبَادَتِكَ
```

### Category
Primary: Health & Fitness  
Secondary: Lifestyle

### Age rating: 4+

### Localize for
- English (primary)
- Urdu (Pakistan, India — 230M+ users)
- Arabic (Middle East, diaspora)
- Indonesian (230M+ Muslim users, underserved)

---

## 18. Launch Strategy

### Target audiences ranked by conversion

1. **Practicing Muslim millennials (ages 25–35)** — Already use productivity apps (Notion, Habitica), ready to pay for an Islamic version. Find on Instagram, Twitter/X, LinkedIn.

2. **Muslim university students** — High app usage, share apps in WhatsApp groups, form communities. Find on Reddit (r/islam, r/MuslimLounge), Discord Islamic servers, university Islamic societies.

3. **Muslim parents** — Want to track their own ibadah + share family leaderboard with children. Find on Facebook Pakistani/Indian/Arab community groups.

4. **Islamic teachers / scholars** — If one Islamic educator recommends the app to 10,000 followers, that is a single acquisition event worth $30,000+ in potential LTV.

5. **Diaspora Muslims** — Pakistani, Arab, Indonesian diaspora in UK, US, Canada — high income, high app spend, culturally connected. Target English + Urdu.

### Zero-budget marketing playbook

**Before launch (Week 4–5):**
- Post mockup screenshots on Instagram with caption: "I'm building a minimal Islamic habit tracker — would you use it? Drop a comment"
- Build a simple landing page (nurapp.io) with email waitlist
- Share in 3 Muslim Discord servers + 5 WhatsApp groups

**Launch week:**
- Post on all Islamic subreddits with genuine, non-spammy post
- Send personal WhatsApp message to 50 Muslim contacts
- Reach out to 3 Muslim Instagram accounts (50k–500k followers) offering free premium in exchange for an honest review post
- Product Hunt submission (Tuesday 12:01am PST)

**Month 1–2:**
- Record a 60-second Reels/TikTok: "I track my 5 daily prayers with this app" (show the UI)
- Reach out to Islamic YouTube channels (Yasmin Mogahed, Nouman Ali Khan channels' audience)
- Post on Twitter/X using hashtags: #IslamicApp #MuslimTech #Ramadan #DailyDhikr
- Submit to Islamic app directories and Muslim blog roundups

**Ramadan strategy (2–3 months before Ramadan):**
- Launch "Ramadan Prep" campaign: "Build your habits now, be ready for Ramadan"
- Send push notification to all users: "Ramadan is X days away — start tracking now"
- Post countdown content on social media for the last 30 days before Ramadan
- Make Ramadan mode FREE for the first 7 days of Ramadan, then require premium

### Influencer outreach template

```
Assalamu Alaikum [Name],

JazakAllah Khair for the content you share — it has genuinely helped me.

I built an app called Nur — a minimal Islamic habit tracker for Salah, Quran, 
and dhikr. I built it because I couldn't find a beautiful, simple app for this.

I would love to offer you free lifetime access to share with your audience if 
you find it genuinely useful. No obligation — only if you believe in it.

App Store: [link]

May Allah reward your efforts.
[Your name]
```

---

## 19. Post-Launch Growth

### Month 3–6 milestones

| Metric | Target |
|--------|--------|
| Total downloads | 10,000 |
| Paying subscribers | 500 |
| MRR | $2,000 |
| App Store rating | 4.7+ |
| Reviews | 200+ |
| Total salah logged | 100,000 |
| Ramadan mode activations | 2,000 |

### Feature priority based on user feedback

**If users ask most about:** → build first:
- "I want my family to use it together" → Family leaderboard (Phase 2)
- "I want Urdu UI" → Urdu localization (major growth unlock in Pakistan)
- "I want tahajjud / nafl prayer tracking" → Custom prayer slots
- "I want to read Quran in-app" → Built-in Quran reader (large build but massive retention)
- "I want hadith of the day" → Daily hadith notification (easy, high engagement)

### Localization unlock

Adding **Urdu UI** is estimated to unlock:
- Pakistan: +5M potential users
- India: +200M potential users
- UK/US Pakistani diaspora: +1M potential users

This is a 2-week development effort with potentially 10x download increase in South Asian markets.

### Community flywheel

The family leaderboard is a viral loop:
1. User invites spouse or sibling → 2 users
2. Family competes on streaks → both become daily active users
3. Family shares the app with extended family → exponential growth

One family of 5 using Nur together = 5 paying subscriptions + word-of-mouth to their mosque community.

---

## 20. Pakistan & Global Muslim Market

### Pakistan-specific features to prioritize

- **Urdu interface** — even partial Urdu (prayer names, buttons) dramatically increases adoption
- **Pakistani calculation method** — Karachi method (University of Islamic Sciences, Karachi) is default for Pakistan, needs to be the obvious first choice
- **Hanafi madhab default** — 90%+ of Pakistani Muslims follow Hanafi madhab
- **Lunar calendar prominence** — Hijri date should be as prominent as Gregorian
- **Friday (Jumu'ah) highlighting** — special indicator on Fridays
- **Sunnah fasts** — Monday and Thursday fasting is common practice, make it one-tap

### Global Muslim market priorities

| Market | Size | Language | Key need |
|--------|------|----------|---------|
| Pakistan | 230M | Urdu | Hanafi, Karachi method, Urdu UI |
| Indonesia | 230M | Indonesian/Bahasa | Different calculation methods |
| Bangladesh | 170M | Bengali | Similar to Pakistan |
| India | 200M | Urdu/Hindi | Diverse calculation needs |
| Turkey | 80M | Turkish | Diyanet calculation method |
| Egypt | 100M | Arabic | Egyptian calculation method |
| UK/US diaspora | 10M | English | English UI, Western time zones |

**Recommended launch order:** English first → Urdu → Arabic → Indonesian

---

## 21. Ramadan Strategy — The Annual Revenue Peak

Ramadan is not just a feature — it is a business event. Plan for it 3 months in advance.

### Pre-Ramadan (60 days before)

- Launch "Ramadan Prep" streak challenge: 60-day streak goal before Ramadan starts
- Push notification: "Ramadan is 60 days away — how consistent is your Salah right now?"
- Blog post / social content: "How to prepare for Ramadan with your phone"
- Offer 30% discount on annual plan: "Lock in your Ramadan companion today"

### During Ramadan (30 days)

- Auto-activate Ramadan mode for all users (free for 7 days)
- Suhoor notification at configured time each day
- Iftar countdown on home screen (mandatory, not optional)
- 30-day tracker: each day shows — Fasted | Tarawih | Quran | Ibadah score
- Special Laylatul Qadr reminder in last 10 nights (odd nights highlighted)
- Quran khatm challenge: "Complete the Quran before Eid"
- Push "Share your streak" card — goes viral as people share on Instagram

### Ramadan paywall strategy

Week 1: Full Ramadan mode free (maximize downloads)
Week 2: Gate Ramadan tracker behind premium ($3.99/mo)
Week 3: Urgency push: "Only 2 weeks of Ramadan left — don't lose your tracker"
Final days: "EID MUBARAK" screen with annual plan offer (50% off, 24 hours only)

### Post-Ramadan retention

The biggest churn risk: users who only came for Ramadan leave after Eid.

**Counter-strategy:**
- Shawwal 6 fasts challenge (6 voluntary fasts after Ramadan — major Sunnah)
- "Keep your Ramadan momentum" push notification on Eid +3 days
- Streak: show users their Ramadan streak as a badge to protect
- Dhul Hijjah mode (first 10 days of Dhul Hijjah — second holiest period)

---

## 22. Google Stitch UI Prompt

Copy this prompt directly into [Google Stitch](https://stitch.withgoogle.com) for all screens.

---

```
Design a complete mobile app UI for an Islamic daily habits tracker called Nur 
(meaning "light" in Arabic). 

The aesthetic is calm, minimal, and spiritually grounded — like a beautiful 
Islamic manuscript meets a modern iOS app. Not the cluttered Islamic app 
aesthetic of old apps. Think calm, generous whitespace, elegant typography.

COLOR PALETTE (Light Mode):
- Background: Warm cream #F9F7F2
- Surface / cards: Pure white #FFFFFF
- Primary accent: Deep teal-green #1B6B5A  (the color of Islamic geometry)
- Secondary accent: Warm gold #C9973A
- Text primary: Near-black #1A1A1A
- Text muted: Warm gray #7A736A
- Success / completed: Emerald #2A7A5A
- Pending / neutral: Light stone #E8E4DC
- Missed / danger: Muted terracotta #C25A3A

COLOR PALETTE (Dark Mode):
- Background: Deep midnight #0D1117
- Surface: Dark slate #161B22
- Primary accent: Soft teal #4ECBA0
- Text primary: Warm white #F0EDE8
- Text muted: Stone gray #8B8680

TYPOGRAPHY:
- Arabic text / headings: Amiri font (elegant Arabic-inspired serif)
- Body and UI: Plus Jakarta Sans (clean, modern, slightly humanist)
- Arabic script elements: Noto Naskh Arabic

SCREENS TO DESIGN (all 8 screens):

1. TODAY DASHBOARD — MAIN SCREEN
- Status bar (light)
- Header left: Hijri date in small text above Gregorian "17 Sha'ban 1447 · Monday"
- Header right: Streak flame badge "14 days" with animated flame icon
- Next prayer banner (full width, teal background):
  "Maghrib · in 47 minutes · 6:23 PM" with a horizontal countdown bar
- Section title: "Today's Salah" (in Amiri font, elegant)
- 5 Salah cards (stacked, not in a grid):
  * Fajr — COMPLETED: teal left border + checkmark, "On Time · 5:12 AM"
  * Dhuhr — COMPLETED: teal checkmark, "On Time · 1:30 PM"
  * Asr — COMPLETED: teal checkmark, "On Time · 4:45 PM"
  * Maghrib — PENDING: stone/gray card, "In 47 minutes · 6:23 PM", subtle pulse animation
  * Isha — PENDING: stone card, "8:45 PM"
- Below salah section:
  * Quran row: circular mini progress ring (60%), "3 / 5 pages today", small + button
  * Dhikr row: morning checkbox (done ✓) + evening checkbox (pending)
  * Fasting toggle: "Fasting today?" — pill toggle, currently OFF
- Bottom: Ibadah score "82 / 100" with a small warm progress bar
- Bottom tab bar: Today | Quran | Dhikr | Calendar | Profile

2. SALAH DETAIL / MARK SCREEN (tap on a Salah card)
- Modal bottom sheet (slides up from bottom)
- Large Arabic name at top: "الْمَغْرِب" (Maghrib) in Amiri font
- Below: "Maghrib · Today · 6:23 PM"
- 4 large selection buttons in a 2x2 grid:
  * "On Time" — teal background with checkmark, largest option
  * "Late (Ada)" — amber background
  * "Makeup (Qada)" — soft purple background
  * "Missed" — light terracotta background  
- Small text below: "Allah is Most Forgiving" (encouraging, not shaming)
- Each button has icon + Arabic label below English

3. QURAN TRACKER SCREEN
- Large centered progress ring (180px diameter):
  * Shows overall khatm completion: 42%
  * Inside the ring: large "42%" in Amiri font
  * Below inside: "Juz 12 of 30"
- "Your Quran Journey" section:
  * Days reading: 47 days
  * Pages this week: 18
  * Total pages: 256
  * Khatm count: 0 (show as "First khatm in progress")
- "Today's Goal" row: "3 / 5 pages" with progress bar
- 3 action buttons: "+1 Page" | "+5 Pages" | "+1 Juz" (pill buttons, teal outline)
- "At this pace, complete khatm in 58 days" — motivational line in muted text
- 30-day bar chart (compact, at bottom): pages read per day, teal bars

4. DHIKR COUNTER SCREEN
- Full-screen immersive counter
- Background: very dark teal/midnight gradient (this screen can use gradient as it is a focused mode)
- Large circular counter display (240px):
  * Current count: "33" in massive Amiri serif font (white)
  * Target ring: gold arc showing progress to 33
- Below counter: current dhikr text
  * Arabic: "سُبْحَانَ اللَّهِ" in large Amiri font (warm white)
  * Transliteration: "SubhanAllah" (medium)
  * Translation: "Glory be to Allah" (muted small)
- Bottom: dhikr selector pills — SubhanAllah | Alhamdulillah | Allahu Akbar | Astaghfirullah
- Large invisible tap zone (entire top 2/3 of screen = tap to count)
- Bottom row: [Reset] [- Target] [+ Target] buttons
- When target reached: gentle gold glow animation + haptic

5. MONTHLY CALENDAR SCREEN
- Header: "Sha'ban 1447" in Amiri font (large, centered)
- Below: "March 2026" in smaller muted text
- Calendar grid (7 columns, 5 rows):
  * Each day cell: date number + colored dot below
  * Green dot = complete ibadah day
  * Amber dot = partial (some salah done)
  * Red dot = mostly missed
  * Gray circle = future / no data
  * Today: teal ring around the date number
  * Friday: gold date number
- Selected day detail panel (below calendar, slides up when day tapped):
  * "Monday, 17 Sha'ban"
  * Mini salah status row (5 colored circles: Fajr ✓ Dhuhr ✓ Asr ✓ Maghrib ✗ Isha ✓)
  * Quran pages: 5 pages
  * Ibadah score: 82/100 with mini progress bar
- Month summary strip: "Complete days: 18 · Avg score: 79 · Best streak: 14"

6. RAMADAN MODE SCREEN (PREMIUM)
- Ramadan Mode header with crescent moon icon, gold color
- "Day 17 of Ramadan 1447" in large Amiri serif
- Two large countdown cards side by side:
  * Left: "Suhoor" — "Tomorrow · 5:08 AM" with countdown "14h 32m"
  * Right: "Iftar" — "Today · 6:47 PM" with countdown "0h 23m" (pulsing)
- Ramadan 30-day tracker grid (compact 6x5 grid of circles):
  * Each circle: day number
  * Filled teal = all good (fasted + tarawih + quran)
  * Gold fill = Laylatul Qadr nights (21, 23, 25, 27, 29 highlighted with star)
  * Empty outline = future
- Today's Ramadan goals:
  * Fasting: ✓ 
  * Tarawih: pending checkbox
  * Quran goal (1 Juz/day): 60% progress bar
- "Laylatul Qadr: 8 nights remaining" — gold alert strip at bottom

7. FAMILY LEADERBOARD SCREEN (PREMIUM)
- Title: "Your Circle" (in Amiri font)
- Subtitle: "This week's ibadah leaderboard"
- Podium section (top 3):
  * 1st: gold crown + avatar circle "Ahmad" + score 94
  * 2nd: silver + "Sara" + 87
  * 3rd: bronze + "Bilal" + 81
- Full leaderboard list (card for each member):
  * Avatar (initials circle, unique color per person)
  * Name
  * Streak: "12 days" with flame
  * Week score: "87 pts"
  * Rank badge
- Invite row at bottom: "Invite family · Share code: NUR-4F2K" with share button

8. UPGRADE / PAYWALL SCREEN
- Soft animated background (subtle geometric Islamic pattern, very faint)
- Crescent + star icon at top (gold)
- Title: "Unlock the full light" in Amiri serif
- 5 premium feature rows with icons:
  * Ramadan mode — full 30-day tracker
  * Family leaderboard — compete with loved ones
  * Monthly ibadah reports
  * Morning & evening adhkar sessions
  * Custom habits (tahajjud, Arabic learning, etc.)
- Pricing toggle: Monthly ($3.99) / Annual ($29.99 — "Best value · Save 37%")
  Annual option highlighted with gold border and "Most Popular" badge
- Large CTA: "Start 7-Day Free Trial" (teal, full width)
- Lifetime option (smaller link): "Lifetime access — $49.99"
- "Cancel anytime · No credit card for trial" muted text below

DESIGN PRINCIPLES:
- Arabic calligraphy-style typography for headings — Amiri font is essential
- Generous whitespace — calm, not cluttered
- The dhikr screen is the only screen that can have a dark gradient background
- Every other screen: warm cream/white backgrounds only
- Islamic geometric motifs can appear as subtle background textures (very faint, 5% opacity)
- Salah cards use a left border accent for status (completed = teal, pending = stone)
- The app should feel like a personal journal + spiritual companion
- Animations: subtle, slow, never flashy (fades and gentle slides only)
- Never use bright colors or neon — the palette is earthy and natural

OUTPUT: High-fidelity mobile mockups at 390x844px (iPhone 14 Pro),
all 8 screens, with a flow diagram connecting them.
Light mode for screens 1-6 and 8. Dark mode for screen 4 (Dhikr counter).
```

---

*Nur App Development Guide v1.0 · March 2026*
*بِسْمِ اللَّهِ الرَّحْمَنِ الرَّحِيم*
*May this app be a means of increasing ibadah for Muslims worldwide.*