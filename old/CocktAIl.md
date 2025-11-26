# CocktAIl - 4-Hour Hackathon Sprint

## Project Overview

**App Name:** CocktAIl  
**Tagline:** Your AI-Powered Bartender  
**Time Limit:** 4 hours total  
**Focus:** One killer feature that works flawlessly

## Core Concept

A simple web app where users input ingredients they have, and AI generates custom cocktail recipes instantly. That's it. No bloat.

## MVP Feature (THE ONLY THING TO BUILD)

### AI Cocktail Generator

**User Flow:**
1. User lands on homepage
2. Selects 3-6 ingredients from quick-select buttons
3. Clicks "Generate Cocktails"
4. AI returns 3 cocktail recipes
5. User can view details and regenerate

**That's the entire app.**

## Detailed Requirements

### Homepage/Input Screen

**UI Elements:**
- App logo/title: "CocktAIl 🍹"
- Tagline: "AI-Powered Cocktails from Your Ingredients"
- Ingredient selector with pre-defined buttons:
  - **Spirits (pick 1-2):** Vodka, Gin, Rum, Tequila, Whiskey, Bourbon
  - **Mixers (pick 1-3):** Lime Juice, Lemon Juice, Simple Syrup, Tonic, Soda, Orange Juice, Cranberry Juice
  - **Extras (pick 0-2):** Mint, Sugar, Salt, Bitters, Triple Sec
- Big "Generate Cocktails" button
- Selected ingredients show as colored chips/badges

**Technical:**
- Single page React app (or vanilla JS)
- State management for selected ingredients
- Validation: Must select at least 3 ingredients

### AI Generation

**API Call:**
- Use Claude API (or OpenAI)
- Prompt template:
  ```
  Create 3 cocktail recipes using ONLY these ingredients: [USER_INGREDIENTS]
  
  For each cocktail provide:
  - Creative name
  - Ingredients with exact measurements
  - 3-4 step instructions
  - Glass type
  
  Format as JSON array.
  ```

**Response Handling:**
- Show loading spinner during API call
- Parse JSON response
- Display 3 cocktail cards

### Results Screen

**Cocktail Card Design:**
- Cocktail name (large, bold)
- Ingredient list with measurements
- Step-by-step instructions (numbered)
- Recommended glass
- "Generate More" button to get new suggestions

**Technical:**
- Clean, readable layout
- Mobile-responsive
- No need for save/favorite features

## Technology Stack

### Absolute Minimum Setup
- **Option 1 (Fastest):** Single HTML file with vanilla JS
  - No build tools needed
  - Just open in browser
  - Use CDN for styling (Tailwind CDN)
  
- **Option 2 (Recommended):** Vite + React
  - `npm create vite@latest cocktail-app -- --template react`
  - Tailwind CSS for styling
  - 5 minutes setup time

### API
- Claude API (requires API key) OR
- OpenAI API (requires API key)
- Store key in environment variable (even for demo)

### Deployment
- Vercel or Netlify (connect GitHub, auto-deploy)
- Alternative: Just run locally for demo

## 4-Hour Timeline

### Hour 1: Setup & Structure (0:00 - 1:00)
- **0:00-0:10** - Create project, install dependencies
- **0:10-0:20** - Set up API integration, test API call
- **0:20-0:40** - Build basic HTML structure & layout
- **0:40-1:00** - Create ingredient selector UI with state

### Hour 2: Core Functionality (1:00 - 2:00)
- **1:00-1:20** - Wire up "Generate" button to API
- **1:20-1:40** - Parse API response, display results
- **1:40-2:00** - Test with different ingredient combinations

### Hour 3: Polish & Styling (2:00 - 3:00)
- **2:00-2:30** - Style the app (colors, spacing, typography)
- **2:30-2:45** - Add loading states and error handling
- **2:45-3:00** - Mobile responsive adjustments

### Hour 4: Testing & Demo Prep (3:00 - 4:00)
- **3:00-3:20** - Bug fixes and edge cases
- **3:20-3:40** - Test on different devices/browsers
- **3:40-3:50** - Deploy to web (if time)
- **3:50-4:00** - Prepare 2-minute demo script

## Minimum Viable Code Structure

```
cocktail-app/
├── index.html (if single file approach)
OR
├── src/
│   ├── App.jsx (main component)
│   ├── components/
│   │   ├── IngredientSelector.jsx
│   │   ├── CocktailCard.jsx
│   │   └── LoadingSpinner.jsx
│   └── api.js (Claude/OpenAI integration)
├── package.json
└── .env (API key)
```

## Critical Success Factors

### Must Work
- [ ] Ingredient selection is intuitive
- [ ] API call successfully returns recipes
- [ ] Recipes display clearly and are readable
- [ ] Works on mobile (judges often check on phone)
- [ ] Loading state exists (no blank screen during API call)

### Can Skip
- ❌ User accounts/login
- ❌ Saving favorites
- ❌ Recipe history
- ❌ Complex filtering
- ❌ Image upload/recognition
- ❌ Multiple pages/routing
- ❌ Backend database
- ❌ Animation/transitions (unless trivial)

## Pre-Built Ingredient List

Copy-paste this array into your code:

```javascript
const INGREDIENTS = {
  spirits: ['Vodka', 'Gin', 'Rum', 'Tequila', 'Whiskey', 'Bourbon'],
  mixers: ['Lime Juice', 'Lemon Juice', 'Simple Syrup', 'Tonic Water', 
           'Club Soda', 'Orange Juice', 'Cranberry Juice', 'Ginger Beer'],
  extras: ['Mint', 'Sugar', 'Salt', 'Bitters', 'Triple Sec', 'Angostura']
};
```

## API Prompt Template

```javascript
const prompt = `You are an expert mixologist. Create exactly 3 cocktail recipes using ONLY these ingredients: ${selectedIngredients.join(', ')}.

Requirements:
- Use ONLY the ingredients provided
- Include exact measurements (oz or ml)
- Keep instructions simple (3-4 steps max)
- Suggest appropriate glassware

Return response as a JSON array with this structure:
[
  {
    "name": "Cocktail Name",
    "ingredients": ["2 oz Vodka", "1 oz Lime Juice", "0.5 oz Simple Syrup"],
    "instructions": ["Step 1", "Step 2", "Step 3"],
    "glass": "Martini glass"
  }
]

Only return the JSON array, no other text.`;
```

## Quick Styling Guide

### Color Palette (Copy-Paste)
```css
Primary: #FF6B6B (coral/red)
Secondary: #4ECDC4 (teal)
Background: #F7F7F7 (light gray)
Text: #2C3E50 (dark blue-gray)
Accent: #FFE66D (yellow)
```

### Tailwind Classes to Use
- Container: `max-w-4xl mx-auto p-6`
- Buttons: `bg-teal-500 hover:bg-teal-600 text-white font-bold py-3 px-6 rounded-lg`
- Cards: `bg-white shadow-lg rounded-lg p-6`
- Chips: `inline-block bg-coral-100 text-coral-700 px-3 py-1 rounded-full text-sm`

## Testing Checklist (5 minutes)

- [ ] Test with 3 ingredients → generates valid recipes
- [ ] Test with 6 ingredients → generates valid recipes  
- [ ] Test on mobile browser (Chrome/Safari)
- [ ] Verify loading spinner appears
- [ ] Check that error message shows if API fails
- [ ] Refresh page → state resets properly

## Demo Script (2 Minutes)

**Minute 1: Introduction**
- "Meet CocktAIl - your AI bartender"
- "Problem: You have random bottles at home, no idea what to make"
- "Solution: AI generates custom recipes from YOUR ingredients"

**Minute 2: Live Demo**
- Show homepage, select 4-5 ingredients
- Click generate (have this pre-loaded if API is slow)
- Show 3 generated recipes
- Highlight one recipe's details
- "That's it - simple, fast, solves a real problem"

## Risk Mitigation

### If API Fails During Demo
- Pre-load example response in your code
- Add a toggle to use mock data vs. real API
- Demo with mock data, mention API integration exists

### If You Run Out of Time
**Priority order (build in this sequence):**
1. ✅ Ingredient selector working
2. ✅ "Generate" button triggers something visible
3. ✅ Display at least 1 recipe (hardcoded is fine)
4. ✅ Basic styling so it doesn't look broken
5. ⭐ Real API integration
6. ⭐ Display 3 recipes
7. ⭐ Polish and mobile responsive

### Emergency Fallback
If nothing works, have 3-5 example cocktails pre-written in JSON that you can display. Just show the concept works, even if API integration isn't complete.

## Team Division (If 2-3 People)

### Person 1: Frontend/UI
- Build React components
- Ingredient selector interface
- Results display
- Styling

### Person 2: API Integration
- Set up Claude/OpenAI API
- Write prompt template
- Handle API responses
- Error handling

### Person 3 (if available): Polish
- Mobile responsiveness
- Loading states
- Testing
- Deployment

**Work in parallel from minute 1!**

## Quick Start Commands

```bash
# Setup (2 minutes)
npm create vite@latest cocktail-app -- --template react
cd cocktail-app
npm install
npm install axios

# Run dev server
npm run dev

# Build for production (if deploying)
npm run build
```

## File You Need: .env

```
VITE_CLAUDE_API_KEY=your_api_key_here
```

Get API key from: https://console.anthropic.com/

## Success = Simple + Working

**Remember:** A simple app that works perfectly beats a complex app that's broken. Focus on making ONE thing work really well.

The judges care about:
- ✅ Does it work?
- ✅ Is it useful?
- ✅ Can I understand it in 2 minutes?

Good luck! You've got this! 🍹⚡

---

**Pro Tip:** Commit to GitHub every 30 minutes. If something breaks, you can roll back.