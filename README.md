# Riftbound Deckbuilder

A deck builder app, built for desktop offline use. The scope is focused solely on deck building and features that support it.

Being an offline desktop app makes it more reliable and responsive, compared to online platforms. Decks can still be exported and published to online platforms using standard formats such as deck code or text list.

> [!NOTE]
> While collection tracking might be useful for building decks with one's available card pool, collection tracking feels more natural in an online platform environment, which enables features such as trading groups. Thus, collection tracking is out of scope for now, and this app is intended for players that care little about collection features.

This deck builder aims to strongly support deck statistics (and possibly goldfish testing). A central feature is *functional categories* (e.g: draw, recursion, removal, ramp), seen in deck builders such as [Archidekt](https://archidekt.com). Dataset may contain default categories, and users can add/remove/rename categories local to the deck they are building.

## Card Data

The dataset lives as an embedded database file (in this case [SQLite](https://www.sqlite.org/)) that is distributed with the deck builder.

> [!NOTE]
> For lower download size and faster build time, the card images are downloaded in the background during runtime, rather than bundling them with the app. The app renders a readable placeholder until the respective card image is available in the device.

Data sources:

- [Riftcodex](https://riftcodex.com)
- [Riot API](https://developer.riotgames.com/docs/riftbound)
- Piltover Archive?

### Data Editor

The data editor allows users to change cards' default categories if they wish to. This editor also has a developer mode which allows importing new card data, and make changes and corrections, and apply them to the database.

## Development

[Documentation](./docs/Home.md)
