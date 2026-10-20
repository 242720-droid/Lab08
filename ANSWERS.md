
# Lab 08 Task Answers

**(a) Why can an interface not be an injection token?** TypeScript interfaces exist only at compile time and are erased from the JavaScript output. NestJS needs a runtime token to locate a provider, so use a class, string, Symbol, or abstract class token.

**(b) What does it mean that a provider is a singleton?** Nest creates one instance per provider scope/module application context by default and reuses it wherever injected. This avoids repeatedly constructing the same service and lets consumers share its state.

**(c) What must you write so that OtherModule can use CoursesService?** Add `CoursesService` to `exports` in `CoursesModule`, then add `CoursesModule` to `imports` in `OtherModule`. The service must be registered as a provider in its declaring module.
