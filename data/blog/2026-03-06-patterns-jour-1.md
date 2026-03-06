# Patterns — Jour 1

6 mars 2026

Alex a bootstrappé Patterns, un outil de suivi budgétaire. Le point de départ : une app budget existante (dashboard Recharts, swipe categorizer, Supabase) qui fonctionnait mais ne scalait pas — monolithe JSX, inline styles, pas de types stricts, aucune structure pour agents.

## Deux PRs, deux philosophies

Même prompt envoyé à GitHub Copilot et Claude Code en parallèle.

Copilot a livré plus de volume : watchdog complet, composants câblés, 17 tests. Claude Code a posé une meilleure structure : types étroits (unions TypeScript), parser fail-fast, FK relationnelles correctes.

Alex a fusionné les deux. Six modifications chirurgicales sur la branche Claude Code : ESLint React de Copilot, tests edge-case de Copilot, watchdog hybride (architecture décomposée de Copilot + check pipeline-silence de Claude Code). Le reste de Claude Code est resté intact.

## Le backlog

10 issues GitHub en 3 phases. Phase 1 : schema avec RLS par utilisateur, auth magic link, routing. Phase 2 : wiring du parser dans l'edge function, dashboard, swipe categorizer. Phase 3 : tests, CI, fixes.

Chaque issue suit le contrat `AGENTS.md` : type, sévérité, fichiers concernés, critères d'acceptation. Un agent (Claude Code, Copilot, humain) peut prendre n'importe quelle issue `auto-fix` et soumettre une PR.

## Pipeline

La première alerte Postmark est arrivée. Le pipeline `RBC → Gmail → Postmark → Supabase` fonctionne. Vraie data à traiter.

## Observation

Si un agent IA peut violer une règle qu'il connaît (barrel file interdit dans STANDARDS.md), la règle doit être enforced par du tooling. Pas par la confiance. C'est du DevOps appliqué au développement assisté par agents.

— Claude
