# Before / After Examples

Illustrative only — hand-written to show what the instruction snippets change
about a response, not benchmarked output from any specific model.

## Example 1: Ambiguous request

**Prompt:** "Can you help me with my resume?"

**Generic style:**
> Sure! Here are some general resume tips:
> 1. Use action verbs.
> 2. Quantify achievements.
> 3. Keep it to one page.
> 4. Tailor it to the job.
> Let me know if you want more help!

**With the style snippets applied:**
> Happy to help — a couple of things will change my approach: are you updating
> an existing resume or starting fresh, and do you have a specific role or
> industry in mind? That'll tell me whether we're editing what you have or
> building structure from scratch.

The generic version answers a question that wasn't quite asked. The second
version figures out which question to actually answer first.

## Example 2: Task goes wrong mid-way

**Prompt:** "Deploy this to staging."

**Generic style:**
> I'm so sorry, there seems to have been an issue with the deployment process!
> I sincerely apologize for any inconvenience this may have caused. Let me try
> again, and I apologize once more if this doesn't work...

**With the style snippets applied:**
> The deploy failed at the build step — a missing environment variable
> (`API_KEY`). I've added a placeholder so the build completes; you'll need to
> set the real value before this is actually usable in staging.

Same failure, very different amount of your time wasted reading apologies
instead of the actual problem.

## Example 3: A fact that could be outdated

**Prompt:** "What's the current price of [some SaaS product]?"

**Generic style:**
> [Product] typically costs around $10/month for the basic plan, though
> pricing can vary.

**With the style snippets applied:**
> Let me check the current pricing page rather than go from memory, since
> these change often.
>
> *(searches, then reports the actual current price with a source link)*

The first answer might be right. It might also be eight months stale. The
second one doesn't leave that to chance.

## Example 4: Multi-step work

**Prompt:** "Set up a CI pipeline for this repo."

**Generic style:** Immediately starts writing a `.github/workflows/ci.yml`
file with default assumptions about the language, test runner, and deploy
target, then presents it as finished.

**With the style snippets applied:** States the plan first ("I'll detect the
language and test setup, add a workflow that runs tests on PRs, and flag
anything that needs a secret or credential you'll need to add manually — here
goes"), does the work with visible steps, then confirms the workflow actually
runs before calling it done.

---

None of these are word-for-word transcripts — they're constructed to make the
difference in approach concrete. Your mileage with any given model will vary;
that's the point of [the limitations section](./README.md#limitations--read-this-before-you-rely-on-it).
