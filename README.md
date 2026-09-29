# SETUP COMMANDS — QR Attendance App

> **Target:** First-year students | **Expo SDK:** 54 | **Expo Go:** 54.0.8

---

## SUPABASE CONFIGURATION

1. Create a Supabase project and copy its project URL and publishable (anon) key.
2. Copy `.env.example` to `.env` and fill in `EXPO_PUBLIC_SUPABASE_URL` and `EXPO_PUBLIC_SUPABASE_ANON_KEY`.
3. In the Supabase SQL Editor, run the contents of `supabase/schema.sql`.
4. In Authentication settings, turn off email confirmation if accounts should sign in immediately after registration.
5. Install dependencies with `npm install`, then restart Expo after changing `.env`.

The app uses only the publishable client key. Never put a service-role key in a mobile app or Expo environment variables.

---

## APP FEATURES

- Email/password registration and sign-in with student or teacher profiles.
- Student QR scanning, duplicate-scan protection, and personal history.
- Teacher event creation with a cloud-backed version 1 QR code.
- Teacher event attendance counts and attendee names in History.
- Row Level Security policies for profiles, events, and attendance.

---

## PREREQUISITES

| Tool | Download | Verify |
|---|---|---|
| Node.js (LTS) | https://nodejs.org/en | `node --version` |
| VS Code | https://code.visualstudio.com | (open it) |
| Expo Go 54.0.8 | Play Store → "Expo Go" | (version in app settings) |

---

## STEP 1 — Create the App

```powershell
cd D:\QR-ATT
npx create-expo-app@latest qr-att

# When prompted, select "SDK 54"
# Wait for npm install (~2 min)
```

---

## STEP 2 — Install Matching Versions

The default install may need these fixed versions that match Expo Go 54.0.8:

```powershell
npm install expo@~54.0.37 react@19.1.0 react-native@0.81.5 expo-router@~6.0.24 @expo/vector-icons@^15.0.3 expo-linking@~8.0.12 expo-constants@~18.0.14 expo-font@~14.0.12 expo-status-bar@~3.0.9 expo-splash-screen@~31.0.13 expo-secure-store@~15.0.8 @supabase/supabase-js react-native-url-polyfill react-native-screens@~4.16.0 react-native-safe-area-context@~5.6.0 react-native-gesture-handler@~2.28.0 react-native-reanimated@~4.1.1 react-dom@19.1.0 react-native-web@~0.21.0 @types/react@~19.1.0 typescript@~5.9.2 --legacy-peer-deps
```

---

## STEP 3 — Start

```powershell
npx expo start
```

Scan QR code with Expo Go. Or press `W` for web.

---

## TROUBLESHOOTING

| Problem | Solution |
|---|---|
| npm install fails | Use `npm install --legacy-peer-deps` |
| App crashes in Expo Go | Make sure all versions match STEP 2 exactly |
| QR won't scan | Phone + computer on same WiFi |
| White screen | Wait 10s, or shake → Reload |
| TypeScript errors | Run `npx tsc --noEmit` |
