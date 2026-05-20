# TripGenius Implementation Plan

Provide a brief description of the problem, any background context, and what the change accomplishes.
TripGenius will be a premium AI-powered travel planning platform designed to feel like a modern, venture-backed startup. The core features include an immersive scroll storytelling landing page, dynamic AI-generated itineraries using Gemini 1.5 Flash, and a user dashboard for saved trips. The application will be built using HTML5, Vanilla CSS, and ES Modules for a lightweight, highly customized experience. It will include a Sandbox Demo mode that works without API keys.

## User Review Required

> [!IMPORTANT]
> **Workspace**: I will create this project in `C:\Users\Roy\.gemini\antigravity\scratch\TripGenius`. Once we begin execution, I recommend you set this directory as your active workspace in your IDE.

> [!WARNING]
> **API Keys & Backend**: The full application requires a Gemini API key and Firebase configuration (Auth + Firestore). I will build the Sandbox Mode (LocalStorage fallback) first so the application is fully functional for demos even without these credentials.

## Open Questions

> [!CAUTION]
> **High-Resolution Imagery**: The scroll storytelling experience relies heavily on beautiful imagery for the 5 sections (Goa, Manali, Jaipur, Kerala, Ladakh). Do you have specific image URLs you want me to use, or should I generate premium placeholder images using my AI image generation tool?
> 
> **Credentials**: Would you like to provide your Gemini API key and Firebase configuration now, or should we stick to the Sandbox Demo mode for the initial build?

## Proposed Changes

We will build the application using a modular architecture with Vanilla HTML/CSS/JS.

### Core Assets & Pages

#### [NEW] index.html
The landing page containing the hero section, the search panel with tabs (Flights, Hotels, Packages, AI Planner), and the 5-section immersive scroll storytelling experience.

#### [NEW] itinerary.html
The generated itinerary page featuring a premium UI, day-wise timeline, budget chart, and export options (PDF, Print, Save).

#### [NEW] dashboard.html
The user dashboard for managing saved trips.

---

### Styling (Vanilla CSS)

#### [NEW] css/style.css
Core design system, CSS variables (colors, typography), global resets, and utility classes.

#### [NEW] css/storytelling.css
Specific styles for the fixed background parallax effect, fade transitions, and text overlays for the scroll experience.

#### [NEW] css/components.css
Styles for the glassmorphism cards, soft shadows, buttons, inputs, and animations.

---

### JavaScript Logic

#### [NEW] js/main.js
Core UI interactions, modal handling, and form submissions.

#### [NEW] js/storytelling.js
Intersection Observers and scroll event listeners to manage the smooth background transitions on the landing page.

#### [NEW] js/ai-service.js
Handles communication with the Gemini 1.5 Flash API and contains the hardcoded JSON data for the 4 required Demo Mode itineraries.

#### [NEW] js/storage-service.js
Handles saving and retrieving trips. It will wrap both LocalStorage (for the sandbox fallback) and Firebase Firestore.

## Verification Plan

### Automated Tests
- Serve the project locally using a lightweight HTTP server.
- Verify ES Module loading and CSS imports.

### Manual Verification
- **Scroll Experience**: Open `index.html` and scroll to verify smooth background transitions and parallax effects across the 5 destination sections.
- **Demo Mode**: Click the "Generate Award-Winning Demo" buttons to ensure itineraries are generated instantly without API keys.
- **Itinerary UI**: Verify that the generated itinerary page matches the premium SaaS aesthetic with glassmorphism and modern typography.
- **Dashboard**: Test saving a trip and viewing it in the dashboard using the LocalStorage fallback.
