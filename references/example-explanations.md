# Example Explanations

This invented factory is a teaching model. The conversation keeps its labels and assumptions across turns, changing only what the learner chooses to explore. Other subjects can use different structures.

## Turn 1: Discover the constraint

**User:** Explain bottlenecks to me.

**Assistant:**

You make one machine twice as fast. The factory produces exactly as much. Why?

Imagine three machines making identical items. Every item must pass through cutting, painting, and packing. There is plenty of material and demand, the machines run steadily, and work can wait between stages. These are their maximum rates:

```text
       CUT             PAINT            PACK
   [12/hour] ──────→ [3/hour] ──────→ [12/hour]

                  Output: 3/hour
```

Suppose you double cutting capacity. Would finished output double too?

```text
       CUT             PAINT            PACK
   [24/hour] ──────→ [3/hour] ──────→ [12/hour]
                       ↑
              still setting the pace

                  Output: 3/hour
```

Painting still finishes only three items an hour. If cutting keeps producing faster than that, unfinished items accumulate before paint.

You've found the **bottleneck**: the stage limiting the line's steady output. Under these assumptions, the line's maximum rate is the smallest stage capacity:

`min(24, 3, 12) = 3 items/hour`

This describes output once the line is running, not how long one item takes to pass through all three machines. It also assumes no breakdowns or defective items. Those are useful complications for later.

Where next?

1. **Go deeper:** What happens after you upgrade the painting machine?
2. **Go sideways:** Where is the painting machine in your own workday? Think of a step every task needs before it can be finished.
3. **Break the model:** What if the machines keep stopping and starting?

## Turn 2: Follow the chosen branch

**User:** Take me down the first rabbit hole.

**Assistant:**

Keep our faster cutter. Now replace the painter with one that can finish 15 items an hour. What sets the pace?

```text
                       BEFORE
       CUT             PAINT            PACK
   [24/hour] ──────→ [3/hour] ──────→ [12/hour]
                  Output: 3/hour

                       AFTER
       CUT             PAINT            PACK
   [24/hour] ──────→ [15/hour] ─────→ [12/hour]
                                         ↑
                                new limiting stage
                  Output: 12/hour
```

Packing now sets the ceiling. Painting got five times the capacity; the line got four times the output. We can trace the difference to the next constraint: `min(24, 15, 12) = 12`.

The bottleneck moved. Choosing the next upgrade means looking at the whole line again.

Two threads to pull:

1. If painting can finish 15 items an hour but packing handles 12, where do the extra items go?
2. What if those rates are averages, and each machine sometimes stops?

## Turn 3: Break the model

**User:** The second one. What if the machines stop sometimes?

**Assistant:**

`Bottlenecks → Changing constraints → Queues`

Our rate labels hid the timing. Let's zoom into packing, which can handle one item every five minutes while running, and give it a ten-minute pause.

Suppose its waiting area starts empty and painted items arrive every four minutes, starting at minute 4. Packing restarts at minute 10:

```text
MINUTE    ARRIVAL     PACKER                 WAITING
   0         —       stopped                   0
   4         A       stopped                   1
   8         B       stopped                   2
  10         —       starts A                  1
  12         C       working on A              2
  15         —       finishes A, starts B       1
```

At minute 15, A is finished, B is being packed, and C is waiting. The average rate alone could not tell us that sequence.

The pause created a **queue**. There's also a lasting mismatch: arrivals every four minutes are faster than packing every five. Even after restarting, packing cannot clear the backlog while that arrival pattern continues.

The smallest capacity still gives us a ceiling, but the earlier output calculation assumed steady operation. To understand a particular item's wait, we also need arrival times, pauses, and how much work is already ahead of it.

One useful next question: if arrivals slowed to one every six minutes, how long would this backlog take to clear?

## A clarification stays small

**User:** Does the bottleneck mean the machine that breaks most often?

**Assistant:**

It means the stage limiting the line's output. Frequent breakdowns can make a machine that constraint, but a machine can also be the bottleneck while running perfectly: our original painter worked continuously and still handled only three items an hour.

## A prediction pause is optional

**User:** Walk me through the factory interactively. Let me guess before you explain.

**Assistant:**

Every item passes through all three machines. They run steadily, with plenty of material and room for work to wait:

```text
       CUT             PAINT            PACK
   [12/hour] ──────→ [3/hour] ──────→ [12/hour]
```

You can double one machine's capacity. Which would you choose to increase finished output, and what rate do you predict?

*The assistant waits here because the user explicitly asked to predict before the reveal.*
