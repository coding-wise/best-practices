# SOLID

- **S** ingle responsibility
- **O** pen / closed
- **L** Liskov substitution
- **I** nterface segregation
- **D** ependency inversion

## Single Responsibility

It says that every module or class should have a single responsibility over a functionality. Examples:

- `PersonClass` should not contain a `validateAddress` function/method, addresses are not necessarly only related to a person, it could be the address of a company, event, or other things. If the validation is coupled with Person than that cannot be used elsewhere without repeating code. That could also apply to `validateEmail`
- In a user registration module, if you send an email that should be in a separate module, so you can mantain different things of your system in separated modules with different responsibilities

## Open / Closed

It says that a module/class should be able to be extended without the need to change the source code.

An example of that can be seen in Angular, the `FormControl`. It doesn't have a hard-coded `validate` with limited options, it allows you to pass in functions to validate the field any way you need to

## Liskov (LSP)

It indicates that a subtype behavior should match the base type behavior. So that if we replace the class/module everything should continue to work exactly as before.

LSP doesn't forbid method overrides, it forbids the violation of contracts.

Example:

- Given the classes `Report`, `XMLReport`, `HTMLReport`, `TextReport`, and the method `generate`, they can all output data in different format, but they cannot change the pre-conditions to generate the report

## Interface Segregation (ISP)

It says the client should not be forced to depend on methods it doesn't use.

Example:

- In JavaScript we can use `babel` as an example. In the past there were fewer modules and they had "everything". In `babel@6` they separated some functionality in different modules (presets), so you can import only the modules your application need. `lodash` is another example, you might not need "everything", so you can import only what you really need

## Dependency Inversion

It says modules shouldn't depend on other concrete modules, but it should depend on abstractions.

Example:

- You should NOT: in a class constructor create a instance of a service
- You should: have the class constructor receive services as dependencies
