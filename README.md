# Writing clean code
What does it take to write clean code that is readable and ages well?
In all my time writing software, some of the most gnarly pieces of code that I have encountered is when I tried adding a small change or a new feature on top of it and was shit scared about what might break. It was guess work - there was not enough test coverage to give me more confidence that I wouldn't end up breaking some critical flow. And to add to the stress of breaking existing flows, the code was authored in such a way that what should have been a one line change ended up becoming a multiple file pull request adding way more scrutiny to what should be a simple feature addition. All because the code was not "open" to extension (there's a subtle reference to SOLID here; my go-to daily reminder-to-self principles when I write code).

This is me, trying to collect information on what makes a code avoid these smells. What are the best practices, what are some of the important design patterns.
