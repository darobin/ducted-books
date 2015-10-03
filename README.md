
# ducted-books

A Ducted pipeline for book writing

Just some quick notes at this point. This is going to require:

* `ducted-style`: for style injection (the CSS is custom to here)
* `ducted-toc`: for ToC generation (take from ReSpec)
* `ducted-load-runner`: basically Ducted runs ASAP (especially with `async`) but sub-pipeline ought to be able to control when they run. Things like `ducted-style` you want running immediately; but the last step in the top-level pipeline should be `ducted-load-runner` that actually only runs its own sub-pipeline when the document is loaded.
* `ducted-writing-stats`: a small plugin that measures the word/character counts, can show them in a floating little panel in the corner, and can even save them (along with the date) at each load so that you can track them over time.
* `ducted-title`: takes the `h1`, sets the `title`.
* `ducted-script-config`: loads the configuration from a `script` with `type='application/ducted+json'`.
* `ducted-ui-panels`: handles the positioning of panels and such UI matters on the side (used by `ducted-writing-stats`)
* `ducted-punctuation-en`: helpfully replaces '{s,t} with ’, "" with “”, ... with … (and perhaps a few others).

Throw in a little bit of browserify/watchify/babelify building and we're good to go.

None of this is complicated, this is a good test of the system.
