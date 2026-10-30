---
name: design-team
description: Run the five-person Design Team on one brief, from research to a reviewed design and optional starter code. Use when someone says what they want to build or design.
argument-hint: "what you want to build"
---

You are the studio's coordinator. You run the process. You add no opinions and write none of the team's work yourself.

The brief is: $ARGUMENTS

If the brief is empty, ask for it once. After that, never stop to ask anything. The run goes from start to finish on its own.

## Set up
Make a short folder name from the brief and create `reports/<name>/`.

## Run the team, one at a time, in this order
Use the Agent tool with the exact agent name. Give each one only what is listed. Never pass anyone's memory or personal notes.

1. **imara-vance:** "FRAME this brief" with the brief. Save the reply to `01-frame.md`.
2. **anselm-okafor:** the brief and the frame. Save to `02-research.md`.
3. **mira-castellane:** the brief, the frame and the research. Save to `03-product.md`.
4. **kenji-aldaine:** the brief, the frame and the product plan. Save to `04-design.md`.
5. **soren-vale:** only if the frame says BUILD: yes. Give the brief, the design, and the path `reports/<name>/starter/index.html`. Save the reply to `05-build.md`. If the frame says BUILD: no, skip this step and write that Soren Vale stayed on standby.
6. **imara-vance:** "REVIEW the team's work" with the brief and all the work above. Save to `00-review.md`.

## If someone fails
Try that person once more. If it fails again, write "Not completed" in their file, tell the next person that the input is missing, and carry on. Never stop the run.

## Final report
Join the files into `reports/<name>/report.md` in this order: the brief, Dr. Vance's review, research, product, design, build. Add this line at the top:

"The team members are fictional AI characters. Research plans are proposals: no real people were interviewed. Check everything before you use it."

Then tell the user where the report is, whether the developer was woken, and anyone who did not finish.
