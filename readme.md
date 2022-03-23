## Design pattern
Package by feature: Package-by-feature uses packages to reflect the feature set. It tries to place all items related to a single feature (and only that feature) into a single directory/package. This results in packages with high cohesion and high modularity, and with minimal coupling between packages.


## Application features
-   [x] Create a new user
-   [x] Send e-mail when a new user is created


## SOLID principles applied
- Single responsability principle: A class CreateUserUseCase tem uma única responsabilidade que é a criação do usuário. Para ela não importa como o usuário será salvo, ex.: database, json file, third party API... etc. A única responsabilidade que esta classe possui é verificar se o usuário existe e criá-lo.

- Liskov substitution principle: Quando a classe recebe no userRepository um tipo IUsersRepository, uma interface, um contrato que define quais são os métodos que irão existir no repositório, não interessa qual repositório eu passar pra ele, ex.: postgres, mysql, mongo... etc, se houver esses métodos ele vai funcionar.

- Dependency invertion principle: Eu recebo a interface ao invés de depender da sua implementação. Não há CRUD executado diretamente no CreateUserUseCase, estou dependendo de uma outra classe que faz a implementação. Dependo apenas da abstração dessa implementação.


OBS.: Desconectamos a camada de infraestrutura da camada de domínio. Todas as funcionalidades externas ficam abstraídas.


## Commands
- yarn init -y
- yarn add express
- yarn add typescript ts-node-dev -D
- yarn tsc --init
- yarn add @types/express -D
- yarn add v4 (antigo uuidv4)
