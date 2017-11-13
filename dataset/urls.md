# Guidelines for URLs in OPWS Dataset Documents

URLs should be as widely-applicable as possible, with as many components as possible removed that refer to specific contexts (such as referrers and locales), so long as visiting the simplified URL still results in the desired page.

In the event that certain components can't be removed without breaking the page (such as [adobe.com](https://github.com/opws/opws-dataset/blob/251ca9c64ac23676e8c1c9b404c3a874125a6b87/profiles/adobe.com.yaml#L27)), the used components should be as generic as possible (ie. using those components that would be presented when reaching that page from the root domain). Where generic values aren't possible but specific universal values are, they should use the most common specific instance (eg. 37signals accounts using Basecamp's Launchpad) or closest to the origin / most targeted market (so eg. if Pottermore required a locale, it would use en-GB).

(In the event of ties, English and specifically en-US wins, per the [Dataset Localization guidelines](localization.md).)

In the event that there is *no* acceptable universally-usable value, the component should be variable-concatenated out (ie. the way usernames in URLs are).
