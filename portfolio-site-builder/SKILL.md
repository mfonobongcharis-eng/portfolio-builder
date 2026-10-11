---
name: portfolio-site-builder
description: Plan, build, refine and launch a personal portfolio website, built for multi-hyphenates and multidisciplinary creatives, from brief, photos and references to a live site, working contact form and preview video.
---

# Portfolio site builder

A proven workflow for taking someone from "I need a portfolio" to a live, distinctive site. It was developed while building a brand and communications strategist's portfolio over many rounds of feedback.

It is designed first for **multi-hyphenates**: people whose work spans several disciplines (strategy, storytelling, community, building, design, and so on) and who struggle to fit into one job title. The site structure below is built to show many sides of one person without looking scattered. Stage 2 explains how to adapt it for someone with a single discipline.

Follow the stages in order. Each stage ends with something the person can see. If the person has a taste or design-system skill, load it first and let it override the defaults here.

## Stage 1: Brief
Get these before designing anything. Ask in one go, not drip by drip.
- Who they are and the one line they want people to remember (positioning).
- Who the site is for: recruiters, clients, collaborators. This decides what goes first.
- Their "sides": the 3 to 6 kinds of work they do. For each, what it covers and their proof.
- The work to show: 4 to 10 projects, each with the problem, what they did, results with real numbers, and links.
- Photos and video: where they live (Drive folder, uploads). Real photos of the person and their work matter more than anything else on the site.
- References: ask for 3 to 6 sites they love AND sites that "feel AI" or generic to them. The second list is as useful as the first.
- Fonts and palette if they have them. If they upload font files, check the licence. Personal-use fonts are fine for a personal site.
- Contact: email, socials, and whether they want a form.

Turn this into a short written plan (sections, case study list, palette, fonts, tone). Get a yes before building.

## Stage 2: Content structure
The multi-hyphenate structure:
1. Hero: name, one-line positioning, two buttons (see the work, contact), a small row of the 3 strongest results, a strong photo.
2. In short: a few lines on who they are and where they're based, plus a second photo.
3. What I do: their 3 to 6 sides as cards. Each card opens to show what it covers, the proof, and which job titles it maps to. This section is what lets a recruiter see where they fit.
4. Selected work: the best 5 to 7 projects as visual cards, each tagged with the sides it shows.
5. Numbers: the most impressive results, each linking to its case.
6. Behind the scenes or personal projects (a lab).
7. Contact.
Plus pages: Work (all cases, filterable by side), one page per case, About, Lab.

Each case page: a title that states the outcome, summary, role/team/channels, cover, 3 headline numbers, the brief, what I did (grouped by side), gallery, what it shows, links.

**Single-discipline person?** Drop the sides system. Replace "What I do" with 3 to 4 services or specialisms, remove the Work filter, and let the case studies carry the page. Everything else in this skill still applies.

Rule: only show proof that is impressive. Cut weak metrics.

## Stage 3: Build
Default stack (fast, good for motion):
- Vite + React + TypeScript + Tailwind, shadcn/ui components, motion (Framer Motion) for animation, Lenis for smooth scrolling.
- Hash routing (#work, #about, #case-slug) so it deploys anywhere as static files.
- All copy and project data in one data file, so text changes never touch layout code.
- Inline small fonts and convert photos to WebP at sensible sizes.

Design defaults that avoid the AI look:
- A display face paired with a script face, and a clean body face.
- A warm, specific palette defined as tokens, not default Tailwind colours. Give each side its own colour from the palette.
- Editorial details: tape, polaroid frames, slight rotations, cut-out portraits (remove backgrounds with rembg), paper grain.
- Visible motion: hover lifts, reveal on scroll, counters, page transitions, light mouse parallax. Respect reduced-motion settings.

Technical lessons learned:
- Reveal-on-scroll animations can fail to fire in some browsers and leave sections blank. Always add a timed fallback that shows the content anyway.
- Make every page work at phone width with no sideways scroll.
- Give images real alt text.

## Stage 4: Review loop
- After every build, take screenshots at desktop and phone sizes and check them yourself before showing anyone. Look for clipped text, overlaps, empty gaps, and decorative elements covering faces.
- Publish a preview the person can click through.
- When feedback arrives, make a numbered list of every requested change and do exactly those. Do not rearrange or reword anything that wasn't mentioned. Moving approved elements is the fastest way to lose trust.
- Never change copy the person has approved unless asked.
- For photo swaps: crop tight to remove distractions and tone down overly bright images.
- If a section feels busy, remove or shrink something before adding anything.
- Expect 4 to 6 rounds. Each round should get smaller.

## Stage 5: Contact form
- Best option: a Tally form (free), created through the Tally connector if available. Fields: name, email, message, plus hidden fields for anything the site collects (reason, side, source). Turn on email notifications to the owner's address. Publish it.
- On the site, the Send button opens the Tally form in a new tab with the answers already filled in. The visitor presses submit there.
- Tell the owner honestly: the message only arrives once the visitor presses submit on Tally. Ask them to send themselves a test message after launch.
- Fallback without Tally: a mailto link plus a copy-message button.

## Stage 6: Launch
- Run the production build. Zip the contents of the build folder (index.html, assets, images).
- The owner goes to Netlify, Add new site, Deploy manually, and drags in the unzipped folder. Then renames the site under Site configuration, and adds a custom domain if they have one.
- Check the live address for typos before they share it anywhere.
- Keep the source zip safe for future edits. Updates are a new build dragged into the same site's Deploys tab.

## Stage 7: Preview video
People share portfolios with a short screen recording.
- Record the real site with Playwright using the Chrome DevTools screencast (frame by frame, high quality). Drive smooth scrolls with eased wheel events and real mouse movement so hover effects show.
- Script it: the intro and hero, hover across the side cards and open one, hover project cards, a confirmation moment (for example "Copied"), the Work page filter, one case study, About, Lab.
- Keep it fast: speed up 1.2 to 1.3 times if it drags.
- Frame it inside a simple browser window on a brand-colour background, with the site address in the bar, and end on a card with the name, role and link.
- Export two cuts: a full walkthrough of 30 to 40 seconds, and a teaser of about 10 seconds (opening, one standout section, About, ending).
