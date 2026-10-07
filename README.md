# Social Pulse

**Paste a batch of social posts or comments and Claude flags which ones are worth a reply.**

AppADay Day 153. Category: Interactive (I), AI powered.

Live app: https://augustineiacopelli.github.io/appaday-153-social-pulse/
Portfolio: https://augustineiacopelli.github.io/appaday/

## What it does

Copy a page of posts or comments and paste it in exactly as it comes, interface clutter and all. With Smart read on, Claude cleans up the paste: it drops buttons like Like and Reply, timestamps, reaction counts, and badges, joins lines that wrapped mid sentence, and finds each distinct post and its author, up to 40 per run. Facebook style clutter is stripped out before Claude sees the text, and a long paste is read in parts of about 12,000 characters so posts are not skipped. It gives every post a verdict of reply now, reply later, or skip, a short category label, and a one line reason. You can add your own reply criteria in Settings, such as "reply to real questions, skip arguments and spam," and Claude applies them to every batch.

Each result card has Open, Later, and Done buttons so you can work through the list, and the results can be filtered by verdict, category, and status. Statuses and results are saved in your browser under a session name, so a half finished inbox is still there when you come back.

## How to use it

1. Tap the gear button and enter your Anthropic API key. Optionally give the session a name and write your reply criteria.
2. Paste straight from the page into the box. The counter shows how many characters you pasted and roughly how many comments it spotted, so you can check that the copy caught everything. Facebook only keeps the posts near your screen loaded, so a copy of a long page can miss the ones that scrolled away.
3. Tap the button. Results appear below with a tally and filters.
4. Mark cards Open, Later, or Done as you reply.
5. To work through a long page in batches, scroll, copy and paste a section, run it, then tick the box that adds new posts to the results instead of replacing them. Posts already in the list are skipped and your statuses are kept.

If the paste holds more than 40 posts, Claude reads the first 40 and the app tells you how many it found. If the paste looks like it holds many more comments than were found, or part of it failed, the app warns you so you can run it again. Smart read can be switched off for a classic mode where you split posts yourself with a blank line or a line of three dashes, and the app remembers your choice.

## Notes

The app calls the Anthropic Messages API directly from the browser with your own key. The key, session name, and reply criteria are stored in this browser only and are never part of the source. The model comes from the portfolio config.json using the sonnet tier, with claude-sonnet-5 as the built in fallback. Adding `?tier=haiku` to the page address runs the cheaper Haiku model, which is handy for test runs. Extended thinking is turned off so the whole token budget goes to the answer, and if a reply ever comes back unreadable the app logs the stop reason and content block types to the console.

Social Pulse works on pasted text only. It does not connect to any social network.

## Home screen

Saved to a phone home screen, the app uses its own icon, the short name Social Pulse, and opens full screen.

## Tech

One self contained index.html with inline CSS and vanilla JavaScript. No build step and no dependencies beyond Google Fonts.

Part of [AppADay](https://augustineiacopelli.github.io/appaday/), one complete app every day.
