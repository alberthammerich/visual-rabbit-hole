# Example Explanations

This invented factory illustrates the chat/page split. Page descriptions below guide generated content; delivery includes a real link to the completed page. Reuse the template's interactions and adapt the presentation to the topic.

## Turn 1: Discover the constraint

**User:** Teach me about bottlenecks.

**Chat:**

You double one machine's speed. The factory produces exactly as much. Why?

Imagine identical items passing through cutting, painting, then packing. All three machines run steadily, with plenty of material and demand and room for work to wait. These are their maximum rates:

```text
                 CUT       PAINT      PACK
Before:       12/hour  →  3/hour  →  12/hour
Faster cut:   24/hour  →  3/hour  →  12/hour
                            ↑
                  Output stays 3/hour
```

Painting still finishes only three items an hour. You've found the **bottleneck**: the stage limiting the whole line. Running cutting faster can leave more unfinished work waiting for paint.

This describes steady output, not the time one item takes to travel through the factory.

**Page content:**

- Start with the same puzzle. Use skippable background to distinguish capacity from actual output.
- Show the line as labeled HTML or SVG stages. Step through the original rates, faster cutting, and a painter upgraded to 15/hour. Keep units and labels fixed; explain why output changes from 3 to 12/hour when packing becomes the constraint.
- State the model's limits: identical items, steady processing, no defects or breakdowns, and enough space between stages.
- Write three checkpoint questions with changed capacities. For example: cutting 20/hour, painting 8/hour, packing 10/hour. Doubling packing leaves output at 8/hour; doubling painting raises it to 10/hour. Feedback explains the limiting stage.
- Offer three quests, with a lesson, diagram, and two questions each:
  1. **Go deeper:** What happens after you upgrade the painting machine?
  2. **Go sideways:** Where is the painting machine in your own workday? Explore a hypothetical writing → review → publish process. Both models have a shared step that can limit finished work; creative tasks vary and people change roles, so the factory's exact rate calculation need not transfer.
  3. **Break the model:** What if the machines keep stopping and starting?

Finish the chat with the actual page link and those three questions. The page has its own complete explanations; understanding the chat does not require opening it.

## Turn 2: Follow the chosen branch

**User:** Take me down the first rabbit hole.

**Chat:**

Keep our faster cutter. Now give the painter capacity for 15 items an hour. What sets the pace?

```text
                 CUT       PAINT       PACK
Before:       24/hour  →   3/hour  →  12/hour
New painter:  24/hour  →  15/hour  →  12/hour
                                        ↑
                           Output rises to 12/hour
```

Packing now sets the ceiling. Painting got five times the capacity; the line got four times the output. We can trace the difference to the next constraint: `min(24, 15, 12) = 12`.

The bottleneck moved. Choosing the next upgrade means looking at the whole line again.

**Page content:**

Open by linking the new question back to the original bottleneck puzzle. Retain the cutter at 24/hour and the same visual labels. Show the painter upgrade, then let the learner examine a packing upgrade. Quizzes change capacities again so answers require applying the rule.

Include these next questions among the quests:

1. If painting can finish 15 items an hour but packing handles 12, where do the extra items go?
2. What if those rates are averages, and each machine sometimes stops?

A copied prompt can carry context: `rabbit hole: What if the machines stop? (from bottlenecks; cut 24/hour, paint 15/hour, pack 12/hour)`.

## Turn 3: Break the model

**User:** The second one. What if the machines stop sometimes?

**Chat:**

`Bottlenecks → Changing constraints → Queues`

Our rate labels hid the timing. Let's pause packing for ten minutes. Painted items keep arriving every four minutes, starting at minute 4. The waiting area starts empty:

```text
MINUTE   ARRIVAL   PACKER                  WAITING
   0        —     stopped                    0
   4        A     stopped                    1
   8        B     stopped                    2
  10        —     starts A                   1
  12        C     working on A               2
  15        —     finishes A, starts B        1
```

Packing takes five minutes per item while running. At minute 15, A is finished, B is being packed, and C is waiting. The average rate alone could not tell us that sequence.

**Page content:**

Turn the timeline into a step-through with the same items A, B, and C. Distinguish waiting items from the one being processed. Explain both the pause and the lasting mismatch: arrivals every four minutes are faster than packing every five, so restarting cannot clear the backlog while that pattern continues.

The smallest capacity still gives a ceiling, but the earlier calculation assumed steady operation. To understand an item's wait, we also need arrival times, pauses, and the work ahead of it.

Use new timings in the checkpoint. One next quest can ask what happens if arrivals slow to one every six minutes. Retain the same page structure and quiz feedback conventions.

## A clarification stays small

**User:** Does the bottleneck mean the machine that breaks most often?

**Assistant:**

It means the stage limiting the line's output. Frequent breakdowns can make a machine that constraint, but a machine can also be the bottleneck while running perfectly: our original painter worked continuously and still handled only three items an hour.

*This clarification needs no new page or quest list.*

## A prediction pause is optional

**User:** Walk me through the factory in chat. Let me guess before you explain.

**Assistant:**

Every item passes through all three machines. They run steadily, with plenty of material and room for work to wait:

```text
CUT [12/hour] → PAINT [3/hour] → PACK [12/hour]
```

You can double one machine's capacity. Which would you choose to increase finished output, and what rate do you predict?

*Wait here because the user explicitly asked to predict before the reveal.*
