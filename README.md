# Riftbound-Archidekt

### Concept

A deckbuilder for Riftbound modeled on Archidekt's structure: cards are organized by functional categories (draw, recursion, removal, ramp...) rather than only by printed type (Unit / Gear / Spell).

Dataset contains default categories, and users can add custom categories local to the deck they are building.

Desktop app and SQLite database because I do not want the trouble of hosting.

UI style also inspired by PiltoverArchive.

3 Views:
- Decks (= project list tab)
- Deckbuilder (includes card browser)
- hidden developer tab that allows updating/importing new sets and edit the categories (forms, table edit); import from Riftcodex.


Resources:
- https://riftmana.com
- https://archidekt.com
- https://riftcodex.com
- https://developer.riotgames.com/docs/riftbound
- https://docs.godotengine.org/en/stable/tutorials/ui/creating_applications.html
