# How do you build a clean system?
How do you keep code clean or design a new system in a way that it ages well. This is a set of principles that were followed by another internal team that I closely work with - gives us an idea on the lines that people think of when creating something new.

1. Write real unit tests – these are tests that operate on a single unit of work and don’t rely on setting up context that involves other classes or dependencies.
2. When dependencies are needed for successful execution, rely on [dependency injection](https://learn.microsoft.com/en-us/dotnet/core/extensions/dependency-injection) and [inversion of control](https://medium.com/@amitkma/understanding-inversion-of-control-ioc-principle-163b1dc97454) principles.
3. When having to inject a dependency that is determined based on dynamic code execution, solve that by leaning on [factory](https://refactoring.guru/design-patterns/factory-method) methods.
4. Any specialized code that is the area of responsibility of the service rather than the kernel should be abstracted via interfaces and the proper implementation injected via constructor injection.
5. Favor constructor injection, because it guarantees objects are in a sane state
6. Lean on [Test Data Builders](https://blog.ploeh.dk/2017/08/15/test-data-builders-in-c/) for code reuse in tests over complex set up methods which allow us to be [DAMP](https://stackoverflow.com/questions/6453235/what-does-damp-not-dry-mean-when-talking-about-unit-tests). Ideally(nice to have, not required) by using AutoFixture
7. Verify that unit test coverage is > 90% before pushing out (exceptions are allowed when hampered by the existing code base)
8. Balance between “Deliver Results” and “Insist on The Highest Standards”. We need to follow the goals above, but we also need to go to prod. If a refactor would take more than 2-3 days to do successfully, it’s acceptable to work around the existing code. 