# Queries for each step

## Free searches (steps 1 and 2, every run)

**X hiring posts.** Web search, for example `site:x.com "hiring" "<role>"`. Do not sign in to X.

**Hacker News "Who is hiring?"** Find this month's thread with `https://hn.algolia.com/api/v1/search_by_date?tags=story,author_whoishiring&query=%22who%20is%20hiring%22&hitsPerPage=1`. Its `objectID` is the thread ID. Search its posts with `https://hn.algolia.com/api/v1/search?tags=comment,story_<ID>&query=<term>&hitsPerPage=1000`. Keep only comments whose `parent_id` is the thread ID; replies are from people who apply.

**Y Combinator.** `https://www.ycombinator.com/jobs/role/<role>`, for example `software-engineer`.

**Company job boards.** Web search with the role and place: `site:jobs.ashbyhq.com`, `site:job-boards.greenhouse.io`, `site:boards.greenhouse.io` and `site:jobs.lever.co`.

**Big job boards.** Web search for LinkedIn, Indeed, Glassdoor and ZipRecruiter listings.

## Tenjin searches (step 3, only if Tenjin is installed)

Ask Tenjin's `request` tool in plain words, one lookup per call. If a lookup fails, say so in one line of the report and go on.

- **X:** "X posts from the last 7 days where people say they are hiring a <role>".
- **Job listings:** "Job listings for <role> in <place> from the last 14 days". Outside the US, name the country.

## Checking a job (step 4)

To confirm that a job is open, read the company's public board:

- Greenhouse: `https://boards-api.greenhouse.io/v1/boards/<board>/jobs`
- Lever: `https://api.lever.co/v0/postings/<company>?mode=json`
- Ashby: `https://api.ashbyhq.com/posting-api/job-board/<board>`

Many LinkedIn pages need a sign-in: do not sign in, and find the same job on the company's own board instead. Use web search for layoffs and hiring freezes.

## The person (step 5, for the 5 best jobs)

**Free ways, in every run:** the author of a Hacker News or X post, the Y Combinator company page (it names the founders), the company's team page, talks, blog posts, GitHub, and LinkedIn profiles that web search shows. Do not sign in anywhere.

**Tenjin, if installed, for each of the 5 as well:** "People at <company> who lead <team>".
