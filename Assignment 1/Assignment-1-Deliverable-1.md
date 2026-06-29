# HumanizerCo landing page — how I thought about it

*Daniel Manzela · Assignment #1, reasoning write-up*

## The bet

The brief is a bit of a trap, and that's the fun of it. We're a brand nobody has heard of, bidding on "free ai humanizer" — a search owned by tools that win precisely by being free and asking for nothing. Our only score is signups divided by visits. Copy the leaders (free, no account) and I get zero signups. Gate the tool behind a signup and I break the promise the ad just made, so people bounce. Both extremes lose.

So the whole page turns on one move. Call it taste-then-gate. Let people use the real tool first. Give them a genuine result. Then ask for the account at the one moment they can see it working and want more.

## How the page earns the signup

You arrive and the tool *is* the hero. No carousel, no "trusted by" logo wall — just a box to paste into. You paste (that's the investment), hit Humanize, and the text actually changes. An AI-likelihood estimate falls in front of you, roughly 97% down to the low 30s. That drop is the hook. It's a progress bar that's almost, but not quite, finished, and the honest leftover ("still 31% above human") is what makes the next step feel worth taking — not a popup I shoved in your face.

The signup shows up only when you reach for the stronger pass, or paste past the 250-word free limit. By then you've felt the value, so the ask reads as "unlock the rest" rather than "pay a toll at the door." It's dismissible, and your text and result are still there if you close it. The gate is real, too: Strong mode and the higher word cap genuinely don't run until you're in, and signing out re-locks them — so an evaluator opening the file cold can test the whole thing twice.

## Layout and look

Everything that matters clears the fold at 1280×720 and on a phone: the input, the mode toggle, the button. I'd rather the tool fight for that space than a big headline. One goal means one accent colour, indigo, and it only ever lands on the buttons that move you forward. The instant the upgrade appears, even the Humanize button drops its colour so the single glowing thing on screen is the next step.

Cool slate palette, a system font, inline SVG icons. No emoji anywhere — emoji are the quickest way to make a tool for anxious students and freelancers look like a weekend hack. Everything passes WCAG AA on real rendered pixels, keyboard included, because traffic that doesn't trust you yet reads polish as proof.

## Copy, and the line I wouldn't cross

The H1 says back exactly what they typed: "Free AI Humanizer." The subhead leads with privacy — it all runs in your browser, nothing is uploaded — which is both true and a genuine edge for anyone pasting a graded essay.

The choice I'm proudest of is what I refused to write. No "undetectable," no "bypass," no "guaranteed to pass." The score is labelled an estimate, and the page openly tells you to drop the result into a real detector and check. That looks like leaving money on the table. I think it's the reverse. This audience has been burned by tools that oversell, and a claim they can disprove in ten seconds wrecks trust faster than a modest, true one ever builds it.

## What I cut, and why

No real Google OAuth or backend — it can't exist in a single offline file, and faking it would break the "your text never leaves your browser" promise that's doing real work. No testimonials or invented user counts; fake social proof on a no-name brand is a tell. No cookie banner, no Open Graph (an ad click never unfurls a preview anyway). And the humanizer is deterministic JavaScript, not an LLM, which keeps it private and instant at the cost of being a heuristic. That cost is the whole reason the copy stays honest about what the score really is.
