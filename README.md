# WordPress Themes Review Checklist
This is the actionable checklist to review a WordPress theme on [WordPress.org](https://wordpress.org/)

## Getting Started
- [ ] Join [WordPress Slack](http://chat.wordpress.org/), then join the theme review team in #themereview
- [ ] Subscribe to [Theme Review Team Updates](https://make.wordpress.org/themes)
- [ ] [Request a Theme](https://make.wordpress.org/themes/) to review

## Internal Setup
- [x] [Install a WordPress site for testing](https://make.wordpress.org/meta/handbook/about/get-involved/setting-up-your-machine)
- [x] Import the [theme unit test data](https://wpcom-themes.svn.automattic.com/demo/theme-unit-test-data.xml) into your installation
- [x] Set WP_DEBUG to `true` in wp-config
- [x] Install the following Plugins: [Theme Check](https://wordpress.org/extend/plugins/theme-check/), [Debug Bar](https://wordpress.org/extend/plugins/debug-bar/), [Log Deprecated Notices](https://wordpress.org/extend/plugins/log-deprecated-notices/), [Monster Widget](https://wordpress.org/extend/plugins/monster-widget/), [WordPress Beta Tester](https://wordpress.org/extend/plugins/wordpress-beta-tester/), [Theme Mentor](https://wordpress.org/plugins/theme-mentor/) _(Note: all those plugins can be installed via the [Developer](https://wordpress.org/extend/plugins/developer/) plugin)_

## Run Test Tools
- [x] Run Theme Check then see the results
- [x] Run Theme Mentor then see the results
- [x] Drag Monster Widget to the Sidebar then see how it looks

## Accessibility

- [x] If the theme has the tag `accessibility-ready` then it needs to meet [these requirements](https://make.wordpress.org/themes/handbook/review/accessibility/).

## Code

- [x] Check PHP and JS errors.
- [x] Include at least index.php and style.css.
- [x] Have a valid DOCTYPE declaration and include language_attributes.
- [ ] Sanitize everything.
- [ ] No removing or modifying non-presentational hooks.
- [x] No shortcodes are allowed.
- [x] Support the following WordPress-generated CSS classes: `.alignleft, .alignright, .wp-caption, .wp-caption-text, .gallery-caption, .sticky, .bypostauthor`

## Core Functionality and Features

- [x] Use [WordPress functionality and features first, if available](https://make.wordpress.org/themes/handbook/review/wordpress-functionality-and-features/).
- [x] Don’t include admin/feature pointers.
- [x] No custom post types and no custom taxonomies.
- [x] No pay wall restricting any WordPress feature.
- [x] No disabling of the admin tool bar.
- [x] Use [get_template_directory()](https://developer.wordpress.org/reference/functions/get_template_directory/) rather than `TEMPLATEPATH` to return the template path.
- [x] Use [get_stylesheet_directory()](https://developer.wordpress.org/reference/functions/get_stylesheet_directory/) rather than `STYLESHEETPATH` to return the stylesheet path.
- [x] Avoid hard coding to modify content. Instead, use function parameters, filters and action hooks where appropriate. For  example wp_title should be modified using a filter.
- [x] Able to have child themes made from them.
- [x] Include comments_template().

## Favicons

- [x] If implemented, disable favicons by default and have the ability for users to override.

## Language

- [x] All theme text strings are to be translatable.
- [x] Include a text domain in style.css
- [x] Use a single unique theme slug – as the theme slug appears in style.css. If it uses a framework then no more than 2 unique slugs.
- [x] Can use any language for text, but only use the same one for all text.

## Licensing

- [x] Be 100% GPL and/or 100% GPL-compatible licensed.
- [x] Declare copyright and license explicitly. Use the license and license uri header slugs to style.css.
- [x] Declare licenses of any resources included such as fonts or images.
- [x] All code and design should be your own or legally yours. Cloning of designs is not acceptable.

## Naming

- [x] Theme names must not use: WordPress, Theme.
- [x] Spell “WordPress” correctly in all public facing text: all one word, with both an uppercase W and P.

## Options and Settings

- [ ] Save options in a single array.
- [ ] Use [sane defaults](https://make.wordpress.org/themes/2014/07/09/using-sane-defaults-in-themes/) and don’t write default setting values to the database.
- [ ] Use edit_theme_options capability for add_theme_page(), rather than rely on a role (e.g. “administrator”), or a different capability (e.g. “edit_themes”, “manage_options”) for the capability to add the settings page.
- [ ] If using a theme options page, add it to the ‘Appearance’ menu.
- [ ] Use either the Settings API or the Customizer for implementing theme options.
- [ ] Prefix all options, custom functions, custom [global variables](http://php.net/manual/en/language.variables.scope.php) and custom constants with the theme-slug.

## Plugins

- [x] Don’t include any plugins. A theme can recommend plugins but not include those plugins in the theme code.
- [x] Don’t do things in a theme considered plugin territory.

## Screenshot

- [ ] Screenshot.png should be of the actual theme as it appears with default options, not a logo or mockup.
- [x] The screenshot.png should be no bigger than 880 x 660px.

## Security and Privacy

- [ ] Don’t phone home without informed user consent. Find out more about [security](https://make.wordpress.org/themes/handbook/review/recommended/security-and-privacy/) here.
- [ ] Make any collection of user data ‘opt-in’ only and have a theme option that is set to disabled by default.Validate and sanitze untrusted data before entering into the database. All untrusted data should be escaped before output. (see: [Data Validation](https://codex.wordpress.org/Data_Validation))
- [x] No url shorteners used in the theme.
- [x] Use `esc_attr()` for text inputs and `esc_textarea()` for textareas.

## Selling, credits and links

- [ ] If you are a themeshop you should be selling under GPL to be in the WordPress.org repo.
- [ ] If the theme adds a footer credit link, there should only be one (link to WordPress does not count)

## Stylesheets and Scripts

- [x] No hard coding of scripts, styles and Favicons unless a browser workaround script. Everything should be enqueued.
- [ ] No analytics or tracking.
- [ ] No minification of scripts or files unless provide original files.
- [ ] Required to use core-bundled scripts rather than including their own version of that script. For example jQuery.
- [ ] Include all scripts and resources it uses rather than hot-linking. The exception to this is Google libraries.
- [ ] If a tag is used in style.css the theme should support that feature or adhere to what that tag stands for. For example custom background or header.

## Templates

If using templates, custom template files should be called using [get_template_part()](https://developer.wordpress.org/reference/functions/get_template_part/) or locate_template().
There are several [template specific things](https://make.wordpress.org/themes/handbook/review/recommended/templates/) you should consider when certain ones are being used.
Use *_url() template tags, rather than bloginfo() equivalents.
