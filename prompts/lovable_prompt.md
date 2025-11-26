# Lovable.dev Mega-Prompt: CocktAIl

**Copy and paste the following into Lovable.dev to generate your winning hackathon app.**

---

**Role:** You are an expert UI/UX Designer and Frontend Engineer winning a hackathon.

**Goal:** Build a "Glassmorphism" style cocktail generator app called **"CocktAIl"**.

**Design System (Critical):**
*   **Style:** Premium Glassmorphism. Use translucent white backgrounds with blur (`backdrop-filter: blur(10px)`), thin white borders, and subtle shadows.
*   **Background:** A vibrant, animated gradient mesh (Coral #FF6B6B to Teal #4ECDC4) that moves slowly.
*   **Typography:** Modern sans-serif (Inter or Outfit). Large, bold headings.
*   **Vibe:** Fun, energetic, and expensive-looking.

**Core Features to Build:**

1.  **Header:**
    *   Logo text "CocktAIl" (Gradient text).
    *   Subtitle: "The AI-Powered Mixologist".

2.  **The "Virtual Bar" (Main Input):**
    *   A section titled "What do you have?".
    *   A grid of selectable "Chips" for ingredients.
    *   **Categories:**
        *   *Spirits:* Vodka, Gin, Rum, Tequila, Whiskey.
        *   *Mixers:* Coke, Soda Water, Tonic, Orange Juice, Lemon Juice.
        *   *Garnishes:* Lime, Mint, Sugar, Salt.
    *   *Interaction:* Clicking a chip toggles it (changes color/glow).

3.  **"Snap & Sip" (The Wow Feature):**
    *   A large, beautiful card next to the ingredient list.
    *   Icon: Camera.
    *   Text: "Or snap a photo of your cabinet".
    *   Action: A file upload button (styled as a glass card). *Note: Just build the UI for now, I will wire up the AI later.*

4.  **Action Button:**
    *   A massive, floating "Generate Cocktail" button at the bottom.
    *   Animation: Pulse effect.

5.  **Recipe Display (The Output):**
    *   A placeholder area for the results.
    *   Design a "Recipe Card" that looks like a holographic trading card.
    *   Fields: Drink Name, Glass Type Icon, Ingredients List, Instructions.

**Technical Constraints:**
*   Use React, Tailwind CSS, and Lucide React for icons.
*   Use `framer-motion` for smooth entrance animations.
*   Make it mobile-responsive (stack columns on phone).

**Start by building the Layout and the Ingredient Selector.**
