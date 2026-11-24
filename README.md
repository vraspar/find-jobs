# find-jobs

![find-jobs](assets/cover.png)

**Find jobs that fit your resume, and the person hiring for each.**

Tell your coding agent to find you jobs and give it your resume. The skill searches Hacker News “Who is hiring?” threads, Y Combinator jobs, company job boards, and the web, checks that each job is open, and warns you about layoffs, stealth companies, and old listings. For the best jobs, it finds the person who owns the role; it never applies or messages anyone for you.

With [Tenjin](https://tenjin.sh), it also searches live X hiring posts and LinkedIn, Indeed, Glassdoor, and ZipRecruiter listings, and looks people up, for about 5 cents a run.

It works on its own or inside a [career-ops](#works-with-career-ops) folder, where it adds jobs to the career-ops inbox.

## Install

In Claude Code, run:

```text
/plugin marketplace add vraspar/find-jobs
/plugin install find-jobs@find-jobs
```

For Codex, Cursor, and other agents, run:

```bash
npx skills add vraspar/find-jobs -g
```

## Use

In your agent, say:

```text
Find me jobs worth applying to. My resume is at ~/resume.pdf
```

Without a resume, the skill uses what your agent knows about you or asks for your role, location, and level.

## What you get

From a free run on an ML engineer's resume, 23 Nov 2026 (excerpt):

**3. Lemurian Labs: Front End Compiler.** Toronto or Santa Clara. No pay shown. [Apply](https://job-boards.greenhouse.io/lemurianlabs/jobs/4118625009)
- **Fit:** You'd build the layer that takes in PyTorch, ONNX, StableHLO and MLIR models, the same kind of work as your compiler frontend internship.
- **Write to:** The VP of Engineering. Very likely the owner, not confirmed. No direct contact found, so use LinkedIn. ([source](https://www.lemurianlabs.com/about))
- **Cares about:** Making AI hardware usable by more people.
- **Warnings:** Open for about 9 months.

**7. Kernelize: Compiler Engineer.** Remote, US preferred. No pay shown. [Apply](https://job-boards.greenhouse.io/kernelize/jobs/5523857004)
- **Fit:** You'd write Triton compiler backends for chips that aren't Nvidia and bring models up on them.
- **Write to:** The founder and CTO, who used to lead AMD's Triton team. ([source](https://www.opencoreventures.com/blog/kernelize-inc-launches-to-bridge-the-cuda-moat))
- **Cares about:** Making Triton the standard kernel compiler for any hardware.
- **Warnings:** Open for about 19 months. Outside the US they hire contractors.

**Dropped:** Unity, Senior MLE On-Device (closed) · Luminal, ML Framework Frontend Engineer (closed)

## How it works

Each job includes the company, role, location, pay if shown, direct apply link, and a one-line explanation of why it fits. It also includes warnings. For the five best jobs, it adds the person to write to: their name, role, contact details, source link, and one thing they care about. If it cannot find the right person, it says so. It does not guess.

The skill drops a job only if it is closed or the work does not match the title. It keeps other jobs and warns you about layoffs in the last three months, stealth or unnamed companies, recruiter posts, contracts, and listings that have been open for months. You decide what to pursue.

Run it again anytime; it skips jobs it has already shown you. It saves each report to `find-jobs/<date>.md` in the folder where you run it.

Your resume stays on your machine. The skill sends only short search terms to services.

## Sources

| Free, no account or key | With Tenjin |
| --- | --- |
| Hacker News “Who is hiring?” threads, Y Combinator jobs, company job boards on Greenhouse, Lever, and Ashby, and your agent’s web search, which also finds some X posts and LinkedIn profiles | Live X hiring posts, LinkedIn, Indeed, Glassdoor, and ZipRecruiter listings, and people search |

Tenjin is a tool router for coding agents. It charges per call from one balance. find-jobs checks whether Tenjin is installed and uses it when available.

To install Tenjin, paste this into Claude Code or Codex:

```text
Install Tenjin from tenjin.sh
```

## Works with career-ops

[career-ops](https://github.com/career-ops-hq/career-ops) is an open-source job search system that scores jobs, tailors your CV, and helps fill applications.

Run find-jobs inside your career-ops folder. It reads `cv.md` and `config/profile.yml` without setup questions, skips jobs career-ops already has, and adds new jobs to `data/pipeline.md` with a note on who to write to. Then run `/career-ops pipeline` to score them and tailor your CV.

find-jobs is not part of or endorsed by career-ops.

## License

MIT
