# Riftbound-Archidekt

### Concept

A desktop deckbuilder tool for Riftbound modeled after [Archidekt](https://archidekt.com): cards are organized by functional categories (draw, recursion, removal, ramp...) rather than only by printed type (Unit / Gear / Spell). Dataset contains default categories, and users can add/remove/rename categories local to the deck they are building.

Scope focuses solely on the deckbuilding part, and leans on the philosophy of modularity and pipeline with prefered tools for each job, rather than a Swiss-knife platform. Online platforms still serve their purpose of sharing decks and collections.

Styling and layout similar to [Piltover Archive](https://piltoverarchive.com/), as I feel like it is very intuitive.

### Development

Framework: Vue + Tauri

Styling and Features: Tailwind CSS, vue-draggable, vue-charts

Data: SQLite - Dataset lives as a SQLite file hosted separately in the repo. The app can fetch for new versions of the dataset file. Card images use on-demand caching, keeping the repo and app size lean.

Dataset Editor: dedicated app for importing new card data and authoring default categories. [Riftcodex](https://riftcodex.com) used as source.

This is a **monorepo** containing both the Deckbuilder and the Dataset Editor.