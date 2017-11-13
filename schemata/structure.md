# Guidelines for Structures Defined by OPWS Schemata

Field names are either separated by levels (if there is liable to be a neighboring field of that scope) or by compound word (which is not separated by underscores or anything like that), with the exception of fields specifying regional localization (eg. `en_US`), which follow an established convention that uses underscores (to fit the pattern of traditional C identifier compatibility).

Part of the reason words are not separated (eg. `thirdparty`) is because that's the way colloquial English usage normally trends toward, like the way "login" has become a word. It'd be a little cringeworthy to see `log_in`, the way it is when you read really old writing and people write things like "Inter-Net".

Fields are supposed to be defined in positions that will allow as much flexibility with what we can foreseeably want. We never want to have to make breaking changes to the schema, and strive to not do so by doing it as correctly as possible the first time (though we're far from being hubristic enough to pretend that breaking changes won't happen).

If something will be specified down the road, the field is supposed to be designed to allow that spec to work with the field *without* requiring the first field to have a breaking change (ie. fields are allowed to be awkward now if it means not being awkward in a later context). That said, fields are still balanced against a certain amount of [YAGNI](https://en.wikipedia.org/wiki/You_aren%27t_gonna_need_it) - hypothetical massive future scope creep isn't a valid reason to make a field twelve levels deep.

Field names are often words that are both nouns and verbs (like "change"): when there's a definite disagreement, the noun form is preferred (see [legacy issue opws/opws-dataset#104](https://github.com/opws/opws-dataset/issues/104)).
