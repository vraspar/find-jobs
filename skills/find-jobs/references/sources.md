# How to do each step

Do the free way in every run. With Tenjin, do the free way and add the Tenjin lookup, then merge the results and drop duplicates.

Ask Tenjin's `request` tool in plain words, one lookup per call. Tenjin picks the service and shows the price. If a Tenjin lookup fails, use the free way for that step and say so in one line of the report.

## Step 1: X

- **Free:** web search, for example `site:x.com "hiring" "<role>"`. Search engines index few recent X posts, so expect little. Do not sign in to X.
- **Tenjin:** "X posts from the last 7 days where people say they are hiring a <role>". The person who posted is often the one to write to.

## Step 2: Hacker News, Y Combinator and the job boards

- **Hacker News, both ways:** find this month's thread with `https://hn.algolia.com/api/v1/search_by_date?tags=story,author_whoishiring&query=%22who%20is%20hiring%22&hitsPerPage=1` (its `objectID` is the thread ID). Search its posts with `https://hn.algolia.com/api/v1/search?tags=comment,story_<ID>&query=<term>&hitsPerPage=100`. Keep only comments whose `parent_id` is the thread ID; replies are from people who apply.
- **Y Combinator, both ways:** `https://www.ycombinator.com/jobs/role/<role>`, for example `software-engineer`.
- **Job boards, free:** web search for listings, also on company job pages: `site:jobs.ashbyhq.com`, `site:job-boards.greenhouse.io`, `site:boards.greenhouse.io` and `site:jobs.lever.co`, with the role and place. Many LinkedIn pages need a sign-in: do not sign in.
- **Job boards, Tenjin:** "Job listings for <role> in <place> from the last 14 days". This covers LinkedIn, Indeed, Glassdoor, ZipRecruiter and employers' own boards. Outside the US, name the country.

## Step 4: check each job

The same both ways. Open the job's own page. To confirm that a job is open, read the company's public board:

- Greenhouse: `https://boards-api.greenhouse.io/v1/boards/<board>/jobs`
- Lever: `https://api.lever.co/v0/postings/<company>?mode=json`
- Ashby: `https://api.ashbyhq.com/posting-api/job-board/<board>`

Use web search for layoffs and hiring freezes.

## Step 5: the person, for the 5 best jobs

- **Free:** the author of a Hacker News or X post, the Y Combinator company page (it names the founders), the company's team page, talks, blog posts, GitHub, and LinkedIn profiles that web search shows. Do not sign in anywhere.
- **Tenjin:** do the free way, and add "People at <company> who lead <team>" to find the hiring manager.
