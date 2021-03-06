## Embedding Oppia explorations in the OpenEdX platform

Oppia is a tool for creating short interactive tutorials (called 'explorations') that try to simulate a conversation with a human tutor. This XBlock allows Oppia explorations to be embedded in OpenEdX courses.

For installation instructions, please consult the latest OpenEdX documentation. You may also find [this tutorial](http://opencraft.com/doc/edx/xblock/tutorial.html#deploying-to-edx-platform) useful.

Notes:

1. You will need to add the value "oppia" to the `advanced_modules` field in Studio's 'Advanced Settings' menu.
2. On devstack, the XBlock does not show up in Studio as a live preview in the editor. However, it does show up in the LMS.
3. This XBlock also comes with default logging capabilities that make use of edX's `event-tracking` library (documented [here](http://edx.readthedocs.org/projects/edx-developer-guide/en/latest/analytics.html#event-tracking)).


## Working with Translations

For information about working with translations, see the [Internationalization Support](http://edx.readthedocs.io/projects/xblock-tutorial/en/latest/edx_platform/edx_lms.html#internationalization-support) section of the [Open edX XBlock Tutorial](https://xblock-tutorial.readthedocs.io/en/latest/).


### Working with Transifex
Prepare your environment:

```
$ mkvirtualenv poll-xblock
$ make requirements
```

Also ensure that the [Transifex client has the proper authentication](https://docs.transifex.com/client/init) 
in the `~/.transifexrc` file.

Push new strings to Transifex:
```
$ make push_translations
```

To get the latest translations from Transifex:
```
$ make pull_translations
```

For testing purposes it's faster to avoid Transifex and work on dummy Esperanto translations:
```
$ make build_dummy_translations
``` 
