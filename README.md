# Social Pulse

**Paste a batch of social posts or comments and Claude flags which ones are worth a reply.**

AppADay Day 153. Category: Interactive (I), AI powered.

Live app: https://augustineiacopelli.github.io/appaday-153-social-pulse/
Portfolio: https://augustineiacopelli.github.io/appaday/

## What it does

Paste up to 40 posts or comments, separated by a blank line or a line of three dashes. Claude reads the whole batch in a single request and gives every post a verdict of reply now, reply later, or skip, a short category label, and a one line reason. You can add your own reply criteria, such as "reply to real questions, skip arguments and spam," and Claude applies them to the batch.

Each result card has Open, Later, and Done buttons so you can work through the list, and the results can be filtered by verdict, category, and status. Statuses and results are saved in your browser under a session name, so a half finished inbox is still there when you come back.

## How to use it

1. Tap the gear button and enter your Anthropic API key. Optionally give the session a name.
2. Paste your posts into the box. The counter shows how many were found out of the 40 allowed.
3. Optionally write your reply criteria.
4. Tap the button. Results appear below with a tally and filters.
5. Mark cards Open, Later, or Done as you reply.

If more than 40 posts are pasted, only the first 40 are read and the app says so.

## Notes

The app calls the Anthropic Messages API directly from the browser with your own key. The key and session name are stored in this browser only and are never part of the source. The model comes from the portfolio config.json using the sonnet tier, with claude-sonnet-5 as the built in fallback. Adding `?tier=haiku` to the page address runs the cheaper Haiku model, which is handy for test runs. Extended thinking is turned off so the whole token budget goes to the answer, and if a reply ever comes back unreadable the app logs the stop reason and content block types to the console.

Social Pulse works on pasted text only. It does not connect to any social network.

## Home screen

Saved to a phone home screen, the app uses its own icon, the short name Social Pulse, and opens full screen.

## Tech

One self contained index.html with inline CSS and vanilla JavaScript. No build step and no dependencies beyond Google Fonts.

Part of [AppADay](https://augustineiacopelli.github.io/appaday/), one complete app every day.
