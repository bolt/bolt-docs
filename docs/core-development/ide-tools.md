---
title: IDE Tools for Developing Bolt
level: advanced
---
IDE Tools for Developing Bolt
=============================

Currently the core team members use a combination of PhpStorm/IntelliJ, vim,
Atom, Sublime, Netbeans, and Visual Studio Code. There is probably even an
emacs die-hard out there.

In no way should any of these this be seen as a requirement to develop on
Bolt's core code, but some tools will make your life easier.

This document currently covers the following IDEs:
  * PhpStorm & IntelliJ IDEA

## PhpStorm & IntelliJ IDEA

### Useful Plugins

* Silex/Pimple Plugin
* Symfony Plugin
* Twig Support

In particular, most developers will find the Silex plugin extremely useful, as
it will allow services stored in the application container to be treated by the
IDE in the same way that normal variables are, and provide auto-completion,
hinting & code completion, to help avoid programmer mistakes.

e.g. Clicking on `$app['twig']` would resolve like a normal variable to
`\Twig\Environment`, and show appropriate data. Whereas `$app['twig']->render()`
will show you information about the `render()` function and highlight missing
parameters, or incorrect parameter types, etc.

#### Silex/Pimple Plugin

##### Set-up

1. Install the plugin from JetBrains repositories:
   * Settings → Plugins → Browse repositories and search for "Silex"
2. Restart PhpStorm/IntelliJ
3. Enable the plugin:
   * Per-project:
     * Settings → Other Settings → Silex Plugin  → Click "Enable Plugin"
   * All projects:
     * Default Settings → Other Settings → Silex Plugin  → Click "Enable Plugin"

For more information, the plugin source repository can be [found on GitHub][silex-idea-plugin]


##### Usage

Simply run the Nut command `pimple:dump`, i.e.:

```bash
php ./bin/console pimple:dump
```

This will generate a `pimple.json` file in the root directory, that once the
extensions is enabled in PhpStorm or IntelliJ IDEA will provide that extension
with the information to make your work with Dependency Injection (DI) objects
far more pleasurable.

---

[silex-pimple-dumper]: https://github.com/Sorien/silex-pimple-dumper
[silex-idea-plugin]: https://github.com/Sorien/silex-idea-plugin
