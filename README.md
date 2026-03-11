# MunchMatch

MunchMatch is a mobile food discovery application that helps users decide **what they want to eat before deciding where to go**. Inspired by swipe-based matching systems, users swipe left or right on dishes to build a personalized taste profile. MunchMatch learns these preferences and recommends dishes tailored to each user.

Once a dish match is identified, MunchMatch uses location-based services to suggest nearby restaurants that serve that dish, factoring in distance, ratings, vibe, and dining context.

The goal is to simplify food decisions by matching users with dishes they actually want and then guiding them to the best place to get them.

---

# Features

### Swipe-Based Food Discovery

Users swipe left or right on dishes to train their taste profile.

* Right Swipe → Interested
* Left Swipe → Not Interested

This interaction helps the system learn what foods users prefer.

### Personalized Dish Recommendations

MunchMatch recommends dishes based on:

* Swipe history
* Cuisine preferences
* Dietary restrictions
* Allergies
* Spice tolerance
* Ingredient preferences

### Location-Based Restaurant Matching

Once a dish is selected, the app finds nearby restaurants that likely serve it using location services and restaurant metadata.

### Favorites

Users can save dishes or restaurants they like for quick access later.

### Future Features

Planned future capabilities include:

* Restaurant swiping
* Group food matching with friends
* Meal planning suggestions
* Social sharing
* Context-aware recommendations (date night, quick lunch, etc.)

---

# Problem

Many food apps start by recommending restaurants, but most people think in terms of **cravings or dishes first**.

Users often struggle with questions like:

* What do I want to eat right now?
* Where can I get the best version of it nearby?

Traditional food discovery apps make this process unnecessarily complicated.

---

# Solution

MunchMatch solves this problem with a **two-stage recommendation system**.

### Stage 1: Dish Matching

Users swipe through dishes to train the system on their taste preferences. The system filters dishes based on allergies, diet restrictions, and spice tolerance.

### Stage 2: Restaurant Matching

After identifying a desired dish, MunchMatch finds nearby restaurants that serve it and ranks them based on:

* Distance
* Restaurant rating
* Price range
* Vibe/atmosphere
* Neighborhood

This dish-first approach simplifies the food discovery process.

---

# Tech Stack

## Mobile Frontend

* React Native
* TypeScript
* Expo
* Expo Router
* TanStack Query
* Zustand
* React Native Gesture Handler
* React Native Reanimated

## Backend

* Node.js
* TypeScript
* NestJS
* Prisma ORM
* PostgreSQL

## APIs and Services

* Google Maps Platform
* Google Places API
* Google Geocoding API
* Google Place Details API

## Authentication

* Clerk or Firebase Authentication

## Infrastructure

* Backend Hosting: Railway / Render / AWS
* Database Hosting: Supabase / Neon (PostgreSQL)
* Mobile Build & Deployment: Expo Application Services

---

# System Architecture

MunchMatch uses a mobile-first architecture composed of three main layers.

### Mobile Client

The mobile application handles user interactions, swipe gestures, profile management, and displays recommendations.

### Backend API

The backend manages authentication, user data, dish metadata, swipe tracking, recommendation logic, and restaurant lookup.

### External APIs

Location and restaurant discovery are powered by Google Maps services.

---

# Recommendation Logic

The recommendation engine works in two stages.

### Dish Recommendation

Dishes are filtered and ranked using factors such as:

* Cuisine preference
* Ingredient similarity
* Previous swipe behavior
* Dietary restrictions
* Spice tolerance
* Context tags (quick meal, comfort food, etc.)

### Restaurant Recommendation

Restaurants are ranked based on:

* Distance from user
* Restaurant rating
* Price range
* Restaurant vibe
* Likelihood the dish is served
* Whether the restaurant is open

---

# MVP Scope

The first version of MunchMatch will include the following core features:

* User authentication
* Preference onboarding
* Swipe-based dish discovery
* Dish recommendation logic
* Restaurant suggestions based on location
* Favorite dishes and restaurants
* User profile management

---

# Future Roadmap

Future versions of MunchMatch may include:

* Restaurant swiping
* Group matching with friends
* Context-aware recommendations
* Machine learning–driven personalization
* Meal planning
* Social features
* Food ordering integrations

---

# Local Development Setup

## Prerequisites

* Node.js
* npm or yarn
* PostgreSQL
* Expo CLI

## Clone the Repository

```bash
git clone https://github.com/ethanhuang1189/MunchMatch.git
cd munchmatch
```

## Install Dependencies

### Mobile App

```bash
cd mobile
npm install
```

### Backend API

```bash
cd backend
npm install
```

## Environment Variables

Create `.env` files for both mobile and backend environments.

Example backend variables:

```
DATABASE_URL=
GOOGLE_MAPS_API_KEY=
AUTH_PROVIDER_KEY=
```

---

# Project Structure

```
munchmatch/
│
├── mobile/                 # React Native mobile application
│
├── backend/                # Node.js API server
│
├── docs/                   # Project documentation
│
├── README.md
│
└── package.json
```

A more detailed breakdown is provided below.

---

# Simple Folder Structure

This structure keeps the project organized and scalable while staying simple.

```
munchmatch
│
├── mobile
│   ├── app
│   │   ├── (auth)
│   │   ├── (tabs)
│   │   ├── swipe
│   │   └── profile
│   │
│   ├── components
│   │   ├── DishCard
│   │   ├── SwipeDeck
│   │   └── RestaurantCard
│   │
│   ├── hooks
│   │
│   ├── services
│   │   ├── api.ts
│   │   └── location.ts
│   │
│   ├── store
│   │
│   └── utils
│
├── backend
│   ├── src
│   │   ├── auth
│   │   ├── users
│   │   ├── dishes
│   │   ├── restaurants
│   │   ├── recommendations
│   │   └── location
│   │
│   ├── prisma
│   │   └── schema.prisma
│   │
│   └── config
│
├── docs
│   ├── architecture.md
│   └── roadmap.md
│
├── README.md
│
└── .gitignore
```

---

# Team Vision

MunchMatch aims to make food discovery faster, more intuitive, and more personalized by focusing on what people actually crave rather than forcing them to browse through endless restaurant listings.

By combining swipe-based learning with real-world restaurant discovery, MunchMatch hopes to simplify one of the most common everyday decisions: **what to eat next**.

---

# Status

MunchMatch is currently in active development.