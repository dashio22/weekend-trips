---
name: weekend-trips
description: "Pick 3-5 nature hikes in Israel for the coming Saturday, check each one is open and fits the season, and deliver them as a Hebrew trail-guide page plus a log line. Use when the user asks for weekend hikes, Saturday trips, or when the weekly hikes routine runs."
---
# Weekend trips

Recommend nature hikes in Israel for the coming Saturday. All output for the reader is in Hebrew. These instructions describe the method only; who receives the message and where the page lives come from the prompt or routine that calls this skill.

## 1. Work out the date and the season

- Find today's date with a clock tool (not from memory), then the date of the coming Saturday. If today is Saturday, use next Saturday.
- Write one or two sentences on what that time of year means for hiking: what is blooming, whether streams are still flowing, how hot the desert is, whether rain or flash floods are possible.

## 2. Choose the routes

- Pick 3 to 5 routes.
- Spread them across regions: at least one in the north, one in the center and one in the south, unless the weather or closures make a region unsuitable (then say why in one line).
- Prefer routes that are at their best right now (season, flowers, water, temperature).
- Mix difficulty: at least one easy, family-friendly route and at least one challenging one.
- Avoid repeating routes from the last two runs: read the previous lines in `trips-log.txt` if it exists.

## 3. Check every route before including it

Search the web for each route. Check:
- **Open or closed**: Israel Nature and Parks Authority (parks.org.il) or KKL for that site, plus any security restrictions in the area (Home Front Command). If a route is closed, drop it and pick another.
- **Saturday**: opening hours on Saturdays and whether booking ahead is required.
- **Cost**: free or paid. If paid, say so and suggest checking the current price; do not invent an amount.
- **Weather**: the forecast for that region on Saturday. Drop desert or canyon routes if there is a flash-flood warning, and flag heat above about 30°C.

Never state a fact about a route that you did not find in a source. Keep one source link per route.

## 4. Write each route card (in Hebrew)

For each route, in this order:
- **Name and region**: route name – area (צפון / מרכז / דרום)
- **למה עכשיו**: why this route fits this week
- **משך**: time and length, loop or out-and-back, trail color if known
- **קושי**: easy / medium / challenging, and who it suits (families, small children, experienced hikers)
- **עלות**: free or paid, and who runs the site
- **טיפ**: one practical tip (parking, start time, shoes, water, layers)
- **מקור**: the source link

Plain, friendly language. Short sentences.

## 5. Build the page

- One self-contained `.html` file, right-to-left (`dir="rtl"`, `lang="he"`), no external scripts, works on a phone.
- Title: the Saturday date, for example "טיולי טבע לשבת 17.10".
- Top: the season sentences, then a short warning box if any route has a restriction or weather issue.
- Filter buttons by region (הכל / צפון / מרכז / דרום).
- One card per route, styled like an Israeli trail blaze (white–color–white stripe), colored by region.
- Light and dark mode.
- If an artifact URL is given, update that artifact; otherwise save the file as `trips-artifact.html` and publish it.

## 6. Send the message (only if asked)

- If the calling prompt names a recipient, send a short email with the route names and the page link.
- If sending fails, try saving a draft instead.
- If both fail (for example the Gmail connector needs reconnecting), do not retry in a loop. Note it in the log and tell the user in one line what to fix.
- Never send to an address that was not given in the prompt.

## 7. Log the run

Append one line to `trips-log.txt`:

```
YYYY-MM-DD HH:MM | <delivery status> | <route 1>, <route 2>, <route 3>
```

Delivery status is one of: `sent`, `draft saved`, `page only`, or `none (<short reason>)`.

## Finish

Tell the user in two or three plain sentences: which routes were picked, how the result was delivered, and anything that failed or needs their attention.
