# The Kingdom's Voice

## Project Overview

**The Kingdom's Voice** — Plateforme d'éducation biblique professionnelle par **ANGE EMMANUEL KOUAMÉ**.

Ouverte à tous : croyants, chercheurs sceptiques, et débutants en foi. Full-stack pnpm monorepo.

### Features
- JWT Auth (localStorage), inscription, connexion, profil
- Bibliothèque: Livres GYNOSKO & EIDO avec 11 chapitres enrichis (illustrations, prières, déclarations)
- Quiz par chapitre, progression, notes personnelles
- Assistant IA (OpenAI via Replit proxy, modèle gpt-5.2)
- Communauté: carte géographique + classement
- **Histoire de l'Église**: Timeline interactive avec 12 événements historiques clés
- **Cellules de Prière**: Création/rejoindre des groupes privés avec code d'invitation, chat en temps réel (polling 3s)
- **Live & Dons**: Page streaming + programme des sessions + partenariat (Stripe à intégrer)
- **Panneau Admin**: Accessible uniquement aux admins (is_admin), ajout de chapitres et d'événements historiques
- Multi-langue: EN, FR, NL, ES, PT (localStorage: `tkv_language` sur web, AsyncStorage `tkv_language` sur mobile)
- **Mobile i18n** : `i18next` + `react-i18next` installés; fichiers locales dans `constants/locales/`; sélecteur de langue dans l'onglet Profil (modal bottom-sheet); `changeLanguage()` persisté dans AsyncStorage
- **Traductions Wave** : clés `giving.wave_*`, `giving.paypal_*`, `giving.recipient_name`, `giving.impact*` dans les 5 langues (web + mobile)
- **Wave paiement** : sections page dons (web + mobile) entièrement traduites via `t()`

### Credentials démo
- Email: `demo@thekingdomsvoice.com` / Password: `kingdom2024`
- Compte admin (is_admin=true)

## Workspace Structure

## Stack

- **Monorepo tool**: pnpm workspaces
- **Node.js version**: 24
- **Package manager**: pnpm
- **TypeScript version**: 5.9
- **API framework**: Express 5
- **Database**: PostgreSQL + Drizzle ORM
- **Validation**: Zod (`zod/v4`), `drizzle-zod`
- **API codegen**: Orval (from OpenAPI spec)
- **Build**: esbuild (CJS bundle)

## Key Commands

- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks and Zod schemas from OpenAPI spec
- `pnpm --filter @workspace/db run push` — push DB schema changes (dev only)
- `pnpm --filter @workspace/api-server run dev` — run API server locally

See the `pnpm-workspace` skill for workspace structure, TypeScript setup, and package details.
