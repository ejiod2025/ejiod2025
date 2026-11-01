# Warehouse visibility and carton recovery

[Back to profile](https://github.com/ejiod2025) · [Explore the synthetic demo](https://github.com/ejiod2025/warehouse-exception-lab)

**Context:** Nordstrom · Senior Analytics Engineer

**Focus:** Operational analytics, SQL correctness, and AI-assisted triage

## The problem

When operational data is spread across systems, a carton exception can be difficult to investigate. Teams need to connect what happened during scanning with the wider warehouse record, determine whether a carton is invalid or missing, and identify the next useful action.

## My contribution

I led a unified data analytics platform that brought previously siloed operational data into a centralized view for warehouse investigations. I also led and carried out operational triage using that platform.

The work enabled teams to identify invalid cartons proactively during scanning and trace cartons that had previously been considered lost. I built AI agents to support the triage workflow, extending the platform into AI-assisted operations.

Alongside these investigations, I worked with 34 SQL metric definitions for warehouse reporting, including item preparation and productivity. One concrete correction addressed item-preparation overcounting caused by a fan-out join.

## Why the join correction matters

A metric can be wrong even when a SQL query runs successfully. If one item joins to several scan records, summing an item-level quantity after the join can count that same quantity repeatedly.

For example, in a **fictional illustration**, a carton containing 10 units with three matching scans can appear to contain 30 units after a naive join and sum. Keeping the aggregation at the intended business grain prevents scan activity from inflating the unit total. The public demo includes an executable example of this issue and a correct calculation.

## Outcome

The platform improved warehouse visibility, supported earlier recognition of carton exceptions, and helped locate and recover inventory previously considered lost. The SQL work improved the accuracy of operational reporting.

The business result is the ability to move from an unexplained exception toward a traceable investigation and recovery.

## Public demonstration

[Warehouse Exception Lab](https://github.com/ejiod2025/warehouse-exception-lab) illustrates related engineering concepts using fictional manifests and scan events. It is a separate Python/SQLite project, not a reproduction of Nordstrom’s platform, data model, or AI agents.

The next area I want to develop publicly is evaluation for AI-assisted investigations: whether an answer cites the right events, how it handles missing evidence, and when it should ask for human review.
