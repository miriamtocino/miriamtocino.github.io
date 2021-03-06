+ scss/
  |
  |
  | + base/                 # reset, typography, site-wide
  |   |-- _index.scss       # imports for all base styles
  |   |-- _config.scss      # global configuration
  |   |-- _base.scss        # base styles
  |   |-- _normalize.scss   # normalize v3.0.1
  |   |-- _susy-setup.scss  # global layouts definitions
  |   |-- _breakpoints.scss # media queries for different devices
  |
  | + layout/               # major components, e.g., header, footer etc.
  |   |-- _index.scss       # imports for all layout styles
  |
  | + modules/              # minor components, e.g., buttons, widgets etc.
  |   |-- _index.scss       # imports for all modules
  |   |-- + buttons/        # buttons types definition
  |       | _btn.scss       # white button styles (color hover effect)
  |       | _btn--color-background.scss   # color button styles (white hover effect)
  |       | ...
  |
  | + states/               # js-based classes, alternative states e.g., success or error state
  |   |-- _index.scss       # imports for all state styles
  |   |-- _states.scss      # state rules
  |   |-- _print.scss       # print styles
  |   |-- _touch.scss       # touch styles
  |
  | + themes/               # (optional) separate theme files
  |   |-- beccapurple.scss  # rename to appropriate theme name
  |
  | + utilities/            # non-CSS outputs (i.e. mixins, variables) & non-modules
  |   |-- _index.scss       # imports for all mixins + global project variables
  |   |-- _fonts.scss       # @font-face mixins
  |   |-- _functions.scss   # ems to rems conversion, etc.
  |   |-- _global.scss      # global variables
  |   |-- _helpers.scss     # placeholder helper classes
  |   |-- _mixins.scss      # media queries, CSS3, etc.
  |   |-- _lib.scss         # imports for third party styles
  |   |-- + lib/            # third party styles
  |       | _pesticide.scss # CSS pesticide
  |       | ...
  |   |-- _vendor-prefixes.scss   # mixins for all vendor prefixes
  |
  |   + ie.scss             # IE specific Sass file
  |   + styles.scss         # primary Sass file
  |   + _shame.scss         # because hacks happen