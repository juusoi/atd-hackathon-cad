# Feasibility Assessment: CocktAIl Demo

## Executive Summary
**Verdict: Highly Feasible**
The proposed "CocktAIl" app is well-scoped for a 4-hour hackathon sprint, provided we stick to the MVP features. The "Snap & Sip" feature is the highest risk but has safe fallbacks.

## 1. Time Feasibility (4-Hour Sprint)
| Feature | Est. Time | Risk | Mitigation |
| :--- | :--- | :--- | :--- |
| **Setup & Boilerplate** | 30 mins | Low | Use Vite + Tailwind presets. |
| **UI (Glassmorphism)** | 60 mins | Medium | Use pre-made CSS glass generators. Don't over-polish initially. |
| **"Virtual Bar" (Logic)** | 45 mins | Low | Simple array manipulation. |
| **AI Integration (Text)** | 45 mins | Low | Gemini API is fast and easy to prompt. |
| **"Snap & Sip" (Vision)** | 60 mins | High | **Risk:** Camera access on web can be flaky. **Fallback:** File upload button. |
| **Polish & Demo Prep** | 30 mins | Medium | Focus on the "Happy Path" for the demo. |

**Total Estimated Time:** ~4.5 Hours.
*Buffer:* We need to be strict. If "Snap & Sip" takes too long, we mock it for the demo using a pre-set image and response.

## 2. Technical Feasibility
*   **Gemini API:**
    *   **Free Tier:** 15 RPM (Requests Per Minute). This is plenty for a live demo.
    *   **Latency:** Text generation is < 2s. Vision can be 3-5s. We need a "shaking mixer" animation to hide this delay.
*   **Web Camera:**
    *   Modern browsers support `navigator.mediaDevices.getUserMedia`.
    *   **Issue:** Mobile browsers can be strict about permissions.
    *   **Solution:** Simple `<input type="file" capture="environment">` is the most robust way to open the camera on mobile web.

## 3. Cost & Infrastructure
*   **Hosting:** Vercel (Free).
*   **Database:** LocalStorage (Free). No backend required.
*   **API:** Google AI Studio (Free).

## 4. Demo Risks & Fallbacks
*   **Risk:** Internet fails during demo.
    *   **Fallback:** Hardcode a "Demo Mode" that returns a pre-generated JSON recipe instantly.
*   **Risk:** AI hallucinates a bad recipe.
    *   **Fallback:** Set `temperature` to `0.4` (lower creativity, higher stability) and ask for "classic twists" rather than "inventing new chemicals".
*   **Risk:** "Glassmorphism" looks bad on projector.
    *   **Fallback:** Ensure high contrast text (white text on dark glass, with text-shadow).

## Conclusion
We can build this. The "Snap & Sip" is the "Wow" factor, so we should prioritize getting the Vision API working early. If it fails, we pivot to a "Upload Photo" flow which is safer.
