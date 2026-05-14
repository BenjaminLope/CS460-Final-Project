# Development Log – The Torchbearer

**Student Name:** Benjamin Lopez
**Student ID:** 825274015

> Instructions: Write at least four dated entries. Required entry types are marked below.
> Two to five sentences per entry is sufficient. Write entries as you go, not all in one
> sitting. Graders check that entries reflect genuine work across multiple sessions.
> Delete all blockquotes before submitting.

---

## Entry 1 – [5/12/2026]: Initial Plan

> Required. Write this before writing any code. Describe your plan: what you will
> implement first, what parts you expect to be difficult, and how you plan to test.

I plan to probabily implement the code sequentially as the orders are labeled in the instructions.
I forsee the invariant check and optimal route to be some tricky parts of the coding, given their more in depth approaches
Finally, I plan on testing via some classic print statement testing, as well as using the debugger when presented with more stubborn bugs for specific value checking

---

## Entry 2 – [5/13/2026]: [Starting work]

Began to work on the final, starting and finishing part 2 of the README.
Realized I misinput year on Entry 1, and I have been neglecting the torchbearer.py so I went into that as well to keep on track.
Finished up working on the torchbearer and readme up to part 2. No formal testing yet, but figured ill go as far as i can before I really go into debug and testing mode.

---

## Entry 3 – [5/13/2026]: [Finish Part 3]

Finished working on all subsections of part 3 in README.
Additionally implemented the answers into the invariant check method in the torchbearer.py file.

---

## Entry #4 – [5/13/2026]: [Finish Part 4]

Finished working on all subsection of part 4 in README.
Implemented answers into relevant method in torchbearer.py
Also revisted the string return for methods, as formatting my mult-line answers was getting annoying.
Found out that python allows triple parenthesis for string returns, so I elected to use those moving forward.
Also fixed a missing answer way back in part 2a that I somehow just missed entering.

---

## Entry #5 – [5/13/2026]: [Finish Part 5 & 6 README]

Finished working on part 5 & 6 in the README.
Now utilizing my current README answers to start working and implementing the algorithm in python.
Did a trial "run" of my python code and got errors right off the bat, so quite  alot of debugging in my future.

---

## Entry #6 – [5/13/2026]: [Route finding implementation]

During work on coding for my main exploring algorithm ran into an incorrect assumption I made earlier.
I had made my relics already collected as "collectedRelics", whereas in the code it is preset of "relics_remaining".
I realized that it wasn't asking for a set of the relics collected but rather to track the relics collected, which in another way is just removing relics you've already collected from the list.
I realized this as it makes much more sense code wise to track the list of relics remaining to collect, as you can then just use the empty list as a base case.
Moving forward I will completely change my answer for part 5 with variable names that better match what the code wants.
Also changed fuelCost to a float

---

## Entry #7 – [5/14/2026]: [Small Crash and method implementation]

Implemented the main exploring and path finding functions. Ran into small crashing bug, which sounds easy enough to fix.
I decided instead to sleep and tackle this issue in the morning, as I spent the bulk of the day working on another final project.
I also fixed Entry #6 date, as I beieve it was set to the wrong day. Reason being a funny but simple one: My laptop Im using is still set to Japan timezone.
It broke when I studied abroad, and I only recently fixed it this semester and just haven't been bothered to fix the clock. Apologies for that.

---

## Entry #x – [Date]: Post-Implementation Reflection

> Required. Written after your implementation is complete. Describe what you would
> change or improve given more time.

_Your entry here._

---

## Final Entry – [Date]: Time Estimate

> Required. Estimate minutes spent per part. Honesty is expected; accuracy is not graded.

| Part | Estimated Hours |
|---|---|
| Part 1: Problem Analysis | |
| Part 2: Precomputation Design | |
| Part 3: Algorithm Correctness | |
| Part 4: Search Design | |
| Part 5: State and Search Space | |
| Part 6: Pruning | |
| Part 7: Implementation | |
| README and DEVLOG writing | |
| **Total** | |
