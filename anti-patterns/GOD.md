# God

God object is an object that knows too much.

For example a `Registration` module/class that handles users, validate strings, import csv files, send emails. A class like that has too many responsibilities and if the code needs to change it might cause side-effects.

Following the (good) Single Responsibility Principle there should be a module/class for:

- users
- validation
- csv files
- email

And the registration could use the (good) Dependency Inversion Principle to receive abstraction of those modules and handle the process.
