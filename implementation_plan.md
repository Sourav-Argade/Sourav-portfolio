# Implementation Plan - Portfolio Website for Sourav Argade

This plan details the implementation of a professional, interactive portfolio website for Sourav Argade, a Senior Backend Engineer. The design is inspired by the cyberpunk/AI aesthetic of [akankshavarade.github.io](https://akankshavarade.github.io/), customized to highlight Sourav's backend engineering, microservices, databases, and cloud expertise.

The website will be built as a single-page React app inside the existing Vite workspace. This will allow running it locally with `npm run dev` and generating a optimized production build via `npm run build` that can be deployed to GitHub Pages or any static hosting service.

## Proposed Design & Customization

We will adapt the visual style of the reference website, including:
- **Neural Network Canvas Background**: Interactive node-and-line animations.
- **Ambient Floating Orbs**: Smooth blurred gradients in the background.
- **Interactive Terminal Widget**: Simulating a terminal boot sequence tailored to backend engineering.
- **Smooth Scroll & Parallax Scroll Effects**: Responsive, modern navigation.
- **Typing Effect**: Cycling titles related to Sourav's technical focus.
- **Cyberpunk Color Palette**: Vibrant cyan/violet gradients against a deep dark background.

We will map Sourav's resume content to the following sections:
1. **Hero**: Interactive greeting, typewriter effect with titles (e.g., "Senior Backend Engineer", "Spring Boot Specialist"), and an introductory bio.
2. **About**: In-depth description of backend & cloud capabilities, quick stats (3.5+ years experience, 15+ tools, etc.), certifications list, and academic education.
3. **Skills**:
   - Emoji-based grid of core languages, databases, and DevOps tools.
   - Categorized cards detailing backend, databases, cloud, messaging, and AI technologies.
4. **Projects**:
   - **Delivery API**: A cloud-native e-commerce backend built with Spring Boot, Kafka, Redis, Docker, and Resilience4j.
   - **Banking Transaction Microservices**: High-volume financial transaction engine built at Capgemini.
   - **SQL Query & Indexing Optimizer**: Caching and SQL optimization project improving latency by 35%.
   - **CI/CD Automation Pipeline**: Jenkins and GitHub Actions containerization project.
5. **Experience**: Timeline displaying Sourav's tenure at Capgemini India as a Senior Software Engineer.
6. **Contact**: Direct connection channels (Email, LinkedIn, GitHub, Phone, and a message form).

---

## Proposed Changes

### Configuration & Entry

#### [MODIFY] [index.html](file:///c:/Users/soura/antigravity/Plans-API-Admin-Console/index.html)
- Update page title to **Sourav Argade — Senior Backend Engineer** and set SEO meta tags.
- Load required fonts: *Syne* for headings, *DM Sans* for body, and *DM Mono* for code/monospaced items.

#### [MODIFY] [index.css](file:///c:/Users/soura/antigravity/Plans-API-Admin-Console/src/index.css)
- Incorporate the full set of custom CSS properties, base resets, keyframe animations, card tilts, custom cursor trails, loading screens, and floating orb styling.
- Merge these smoothly with the current configuration.

### Application Components

#### [NEW] [types.ts](file:///c:/Users/soura/antigravity/Plans-API-Admin-Console/src/types.ts)
- Add TypeScript interfaces for skills, projects, and experiences to ensure typesafety.

#### [NEW] [Navbar.tsx](file:///c:/Users/soura/antigravity/Plans-API-Admin-Console/src/components/Navbar.tsx)
- Responsive header navigation supporting desktop links, a mobile hamburger menu overlay, and a resume download action.

#### [NEW] [Loader.tsx](file:///c:/Users/soura/antigravity/Plans-API-Admin-Console/src/components/Loader.tsx)
- A smooth loading screen with a pulsing progress indicator that fades out when the app mounts.

#### [NEW] [NeuralCanvas.tsx](file:///c:/Users/soura/antigravity/Plans-API-Admin-Console/src/components/NeuralCanvas.tsx)
- React canvas wrapper implementing the node-line physics and movement calculations for the interactive background.

#### [MODIFY] [App.tsx](file:///c:/Users/soura/antigravity/Plans-API-Admin-Console/src/App.tsx)
- Re-architect `App.tsx` as the master component coordinating the portfolio state, scroll tracking, typing effect timer, custom cursor, and embedding all section elements.

---

## Verification Plan

### Automated Verification
- Run TypeScript compilation checks to verify no build errors:
  ```powershell
  npm run lint
  ```
- Run Vite production bundle compilation to check build output:
  ```powershell
  npm run build
  ```

### Manual Verification
- Start local development server to test page layout and interactivity:
  ```powershell
  npm run dev
  ```
- Verify interactive components:
  - Mobile responsiveness (shrinking viewport).
  - Neural network background interaction.
  - Hover states and 3D card tilt effects.
  - Smooth scrolling for navigation anchors.
  - Speed of initial load.
