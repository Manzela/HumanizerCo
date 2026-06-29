# HumanizerCo — Assignment #2: three A/B tests I'd run before scaling spend

*Daniel Manzela · Assignment #2, reasoning write-up*

Everyone who lands on this page typed "free ai humanizer" into Google and clicked our ad. They're pre-qualified and impatient, the page needs to get them to a signup. So I picked three bets that sit directly on the conversion path: one at the top of the page (the headline), and two inside the CTA gate, which is where the account is actually won or lost. Each test changes exactly one thing.

The three tests operate at different funnel depths, so their timelines differ: 
- Test 1 (headline) measures against all visitors at a ~4% baseline signup CVR — detecting a 15% relative lift at 90% confidence requires roughly 10,000 visitors per variant, or about 6–10 weeks with a Google Search campaign driving 300–500 clicks/day.
- Tests 2 and 3 measure gate completion rate against users who already hit the paywall, where baseline rates run closer to 25–35% — those tests reach significance at roughly 1,100 visitors per variant, potentially within the first days of the campaign.
- Running all three simultaneously is the right call: two tests give fast reads while the headline test accumulates.

### Test 1 — Headline: Bold vs. Honest

The headline is the first thing a visitor sees, and it decides whether they stay or leave. I set the honest version as the control: "Free AI Humanizer - Make AI Text Read Like You Wrote It", because the bolder "Sound 100% Human" contradicts our own disclaimers. But does the bold promise convert better? This audience is split: some people want the aggressive claim because it matches exactly what they searched for, while others have been burned by tools that oversell and will trust the modest version more. This test will figure it out. I'd decide on **Signup CVR** (signups ÷ exposures), and watch **bounce rate** closely, if the bold headline breaks trust, visitors will leave before they even try the tool. If the bold version lifts CVR without spiking bounce, it earns its place. If not, the honest version stays.

### Test 2 — Gate offer: Benefit-driven vs. Feature-driven

The CTA gate is where we win the account, but right now its entire pitch is one sentence: "Sign up free to run Strong mode and lift the 250-word limit." At the moment someone decides whether to hand over their email, we're underselling what's behind the wall. The variant replaces that line with a clear benefits list: Strong mode (our deepest rewrite), no word limit (full essays in one pass), free forever (no credit card). It tells people exactly what they get and that it costs nothing. The right metric is **gate completion rate** (signups ÷ gate views), not overall CVR, because most visitors never see the gate, so measuring against total traffic would cause false-positives and/or false-negatives. I'd also watch **gate dismissal rate** to make sure the longer copy doesn't scare people off. Additionally, I'd track **time on gate** to ensure the new copy is being read and not just ignored.

### Test 3 — Auth friction: Lead with Google Sign-in vs. Email Field

We already offer both email and Google sign-in, so this isn't about adding a new option, it's about which one appears first. This traffic is heavily skewed mobile, and on a phone the gap between one tap and typing out an email is real friction. The variant flips the order: "Continue with Google" moves to the top, email drops below. Fewer steps, more completions. **Signup CVR** is the primary metric. I'd also track which sign-in method people actually use to confirm the reorder is genuinely shifting behavior, not just rearranging it. The important guardrail: which sign-up method converts more users?


