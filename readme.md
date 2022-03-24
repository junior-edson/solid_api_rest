## Architecture applied (for microservices)
Package by feature: Package-by-feature uses packages to reflect the feature set. It tries to place all items related to a single feature (and only that feature) into a single directory/package. This results in packages with high cohesion and high modularity, and with minimal coupling between packages.


## Application features
-   [x] Create a new user
-   [x] Send e-mail when a new user is created


## SOLID principles applied
- Single responsability principle: The CreateUserUseCase class has a single responsibility which is the creation of the user. It doesn't matter how the user will be saved, eg.: database, json file, third party API... etc. The only responsibility this class has is to check if the user exists and create it.

- Liskov substitution principle: When the CreateUserUseCase class receives in the userRepository an IUsersRepository type, an interface, a contract that defines which methods will exist in the repository, it does not matter which repository I will pass to it, eg.: postgres, mysql, mongo... etc. , if there are these methods it will work.

- Dependency invertion principle: I get the interface rather than depending on its implementation. There is no CRUD executed directly in CreateUserUseCase, I'm depending on another class that does the implementation. I just depend on the abstraction of this implementation.


ps.: We detach the infrastructure layer from the domain layer. All external functionality is abstracted.


## Commands
- yarn init -y
- yarn add express
- yarn add typescript ts-node-dev -D
- yarn tsc --init
- yarn add @types/express -D
- yarn add uuidv4
- yarn add nodemailer
- yarn add @types/nodemailer -D
