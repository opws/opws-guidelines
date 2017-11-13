## Schema structure

Field names are either separated by levels (if there is liable to be a neighboring field of that scope) or by compound word (which is not separated by underscores or anything like that), with the exception of fields specifying regional localization (eg. `en_US`), which follow an established convention that uses underscores (to fit the pattern of traditional C identifier compatibility).

Part of the reason words are not separated (eg. `thirdparty`) is because that's the way colloquial English usage normally trends toward, like the way "login" has become a word. It'd be a little cringeworthy to see `log_in`, the way it is when you read really old writing and people write things like "Inter-Net".

Fields are supposed to be defined in positions that will allow as much flexibility with what we can foreseeably want. We never want to have to make breaking changes to the schema, and strive to not do so by doing it as correctly as possible the first time (though we're far from being hubristic enough to pretend that breaking changes won't happen).

If something will be specified down the road, the field is supposed to be designed to allow that spec to work with the field *without* requiring the first field to have a breaking change (ie. fields are allowed to be awkward now if it means not being awkward in a later context). That said, fields are still balanced against a certain amount of [YAGNI](https://en.wikipedia.org/wiki/You_aren%27t_gonna_need_it) - hypothetical massive future scope creep isn't a valid reason to make a field twelve levels deep.

Field names are often words that are both nouns and verbs (like "change"): when there's a definite disagreement, the noun form is preferred (see [issue #104](https://github.com/opensets/domainprofiles/issues/104)).

## Content locale

Locales of text are labeled with [BCP47](https://tools.ietf.org/html/bcp47)-style keys (where locales may be distinguished beyond the lower-case language code with a capitalized country code), with underscores in place of hyphens. The simplest tag is picked for each localization: more complex tags may be used when writing alternative formulations that are more dialect-specific. (For instance, if the initial Portuguese localization of a freeform field were written with Brazilian Portuguese isms, it would be under "pt": a pull request to introduce a European Portuguese version would change it so there are "pt_BR" and "pt_PT" fields.)

An English (or en_US) version of any note should be included along with the target language, as a guaranteed last-chance fallback (see [issue #12](https://github.com/opensets/domainprofiles/issues/12)).

## URLs

URLs should be as widely-applicable as possible, with as many components as possible removed that refer to specific contexts (such as referrers and locales), so long as visiting the simplified URL still results in the desired page.

In the event that certain components can't be removed without breaking the page (such as [adobe.com](https://github.com/opensets/domainprofiles/blob/042732e9841986d624538c417d22c081e6b845ec/profiles/com/adobe.yaml)), the used components should be as generic as possible (ie. using those components that would be presented when reaching that page from the root domain). Where generic values aren't possible but specific universal values are, they should use the most common specific instance (eg. 37signals accounts using Basecamp's Launchpad) or closest to the origin / most targeted market (so eg. if Pottermore required a locale, it would use en-GB).

(In the event of ties, English and specifically en-US wins, per the style guidelines on content locale.)

In the event that there is *no* acceptable universally-usable value, the component should be variable-concatenated out (ie. the way usernames in URLs are).
