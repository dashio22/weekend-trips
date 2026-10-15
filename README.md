# weekend-trips

A Claude Code plugin with one skill, `/weekend-trips`. It picks 3–5 nature hikes in Israel for the coming Saturday and checks that each one is open, fits the season and suits the weather. It then builds a Hebrew, right-to-left trail-guide page with one card per route.

## Install

From GitHub, once this folder is pushed to a repository:

```
/plugin marketplace add dashio22/weekend-trips
/plugin install weekend-trips@dashio22-skills
```

From a local copy of this folder:

```
/plugin marketplace add ./weekend-trips
/plugin install weekend-trips@dashio22-skills
```

## Use

Ask for weekend hikes or Saturday trips, or run `/weekend-trips`. If you want the result emailed, name the recipient and the target page in your own prompt or routine. The skill itself stores no addresses or links.

## What's inside

```
.claude-plugin/plugin.json        plugin description
.claude-plugin/marketplace.json   marketplace "dashio22-skills" listing this plugin
skills/weekend-trips/SKILL.md     the method
```
