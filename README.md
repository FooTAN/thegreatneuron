# The Great Neuron

- [The Great Neuron](#the-great-neuron)
  - [Scenario](#scenario)
  - [The solution](#the-solution)
  - [The Plan](#the-plan)
  - [Services](#services)
    - [Auth service](#auth-service)
    - [Article service](#article-service)
    - [Admin Service](#admin-service)
    - [Client Service](#client-service)
    - [Picture labeling service](#picture-labeling-service)

## Scenario
At the "The Great Neuron Corporation", they have a problem.<br/>
All those at TGNC love cats and dogs, but they are terrible at identifying either cats, or dogs.<br/>
To the TGNC great dismay a great portion of the day goes toward solving arguments pertaining wether a picture is a cat, or a dog. This will not do!<br/>

## The solution
The dev department comes up with a solution. What if we create an internal website where you can upload a picture, then we use AI to identify wether it is a cat, or a dog. We could also have articles explaining the difference between cats, and dogs.

## The Plan
The Devs goes back into their developer room and start churning their developer brains.

To start off we'll only care that our apps works locally on the developer machine.
We'll create our app as services.
We'll use kubernetes, and skaffold to help set it up.

## Services

### Auth service
We'll make our own, It doesn't have to be perfectly secure, app will not be accessible to the outside world. There is plenty more secure auth services to choose from if we need it to be secure. It's simply for the challenge.
- admin users, and client users share database.
- We'll use Tokens to identify users.
- We'll use Tokens stored in cookies.(probably)
- Will have CRUD.
- Users have Roles.
- Only admin can create accounts.
- Use mysql as the database.

### Article service
- Allow user with correct role to create and edit articles.

### Admin Service
- We'll server render with Next.js
### Client Service
- We'll either use Next.js or client side rendering served by nginx.(undecided)
### Picture labeling service
Most likely we'll not be training any model in this service. We'll be using an already trained model.
- Identifires wether a picture is a cat, or a dog.
