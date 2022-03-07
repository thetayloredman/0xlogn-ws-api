# Reducing Sequence Ambiguity

I have had a few people questioning how the `seq` (sequence) system works.

This document exists to clear this up.

## In the case of an incorrect sequence...

**the connection should be terminated** by the server when it notices this.

Logically, the connection has been bricked up by something if the sequencer becomes invalid.&#x20;

## In the case of the client forgetting the sequencer...

**the client should terminate the connection** because there is no way to fetch a new one without giving it another sequencer.
