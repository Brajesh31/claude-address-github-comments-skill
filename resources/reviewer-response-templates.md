# Reviewer Response Templates

Use these as starting points. Adjust every response to match the actual change and test evidence. Never claim that a change was made or verified when it was not.

## Fix implemented

~~~text
Addressed in [commit or change reference].

I updated [file/component] to [brief explanation of the fix]. I verified it by [test or validation performed].
~~~

## Clarification requested

~~~text
Could you clarify the expected behavior for [specific case]?

The current implementation supports [current behavior]. I see two possible interpretations: [option A] and [option B]. Which one should the change follow?
~~~

## Alternative approach

~~~text
I understand the concern. I propose [alternative] because [technical reason].

This preserves [required behavior] while addressing [underlying issue]. Please confirm whether this approach meets the intent of the comment.
~~~

## Cannot reproduce

~~~text
I tried to reproduce this using [environment, steps, and relevant version], but I could not observe the reported behavior.

Could you share the expected input, environment, or exact reproduction steps? I will re-test with that information.
~~~

## Not applicable

~~~text
This suggestion does not apply to [specific context] because [evidence or project constraint].

I documented the reason and left the implementation unchanged. Please let me know if there is another scenario I should account for.
~~~

## Test limitation

~~~text
The implementation change is complete. I could not run [specific test] because [reason].

I did run [available checks]. The remaining validation is [next step] and should be completed before merge if it is required for this change.
~~~

## Final review summary

~~~text
I reviewed the open feedback and addressed the actionable items.

- Updated: [files or components]
- Verified with: [tests / checks]
- Still open: [items requiring clarification or reviewer decision]

The remaining threads have not been marked as resolved because they still need confirmation.
~~~
