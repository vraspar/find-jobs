# Sources

Use the free sources in every run. When Tenjin is installed, add its lookups on top.

## Free

**X hiring posts.** Web search, for example `site:x.com "hiring" "<role>"` or `site:x.com "we're hiring" <skill>`. Search engines index few recent X posts, so expect a thin result. Do not sign in to X or read browser cookies.

**Hacker News "Who is hiring?"** A new thread starts on the first weekday of each month. Each top-level comment is one company's post, and its author is often a founder or the hiring manager.

- Find this month's thread: `https://hn.algolia.com/api/v1/search_by_date?tags=story,author_whoishiring&query=%22who%20is%20hiring%22&hitsPerPage=1`. Its `objectID` is the thread ID.
- Search its posts: `https://hn.algolia.com/api/v1/search?tags=comment,story_<ID>&query=<term>&hitsPerPage=100`. Keep only comments whose `parent_id` is the thread ID; replies are from people who apply.

**Y Combinator jobs.** `https://www.ycombinator.com/jobs/role/<role>`, for example `software-engineer`. Each company page names its founders, who are often the people hiring.

**Company job boards.** Find openings with web search: `site:jobs.ashbyhq.com`, `site:job-boards.greenhouse.io`, `site:boards.greenhouse.io` or `site:jobs.lever.co`, with the role and place. To check that a job is still open, read the company's public board:

- Greenhouse: `https://boards-api.greenhouse.io/v1/boards/<board>/jobs`
- Lever: `https://api.lever.co/v0/postings/<company>?mode=json`
- Ashby: `https://api.ashbyhq.com/posting-api/job-board/<board>`

**Big job boards.** Web search finds some LinkedIn and Indeed listings. Many LinkedIn pages need a sign-in: do not sign in, and find the same job on the company's own board instead.

**People.** The Hacker News post author, the YC company page, the company's team or about page, conference talks, blog posts, GitHub, and LinkedIn profiles that web search shows. Do not sign in anywhere.

## With Tenjin

Ask Tenjin's `request` tool in plain words, one lookup per call. Tenjin picks the service and shows the price before it charges. Each lookup costs a fraction of a cent to about 2 cents.

- **X:** "X posts from the last 7 days where people say they are hiring a <role> in <place>". X is where Tenjin finds jobs that the free sources miss, so run a few searches with different words: the job title, the key skill, and phrases such as "my team is hiring" or "DM me".
- **Job boards:** "Job listings for <role> in <place> from the last week". This covers LinkedIn, Indeed, Glassdoor, ZipRecruiter and employers' own boards.
- **People:** "People at <company> who lead <team>", to find the hiring manager.
- **Deeper web search:** for a company's recent news, layoffs or a person's recent posts.

If a lookup fails, go on with the other sources and say so in one line of the report.
