# Arelai

Arelai is a framework for creating games and training agents using reinforcement learning (RL). It includes core components like states, actions, observations, and players that can be customized for specific games.

## Usage

Using the framework is simple.

1. **Create a Custom Game**
   - Subclass `State`, `Action`, `Observation`, and `Game` to define your game’s rules and mechanics.

2. **Define Players**
   - Subclass `Player` to define how players interact with the game.

3. **Run the Game**
   - Create a `Game` object with players and an initial state, then call the `play()` method.

## Example

```python
class MyState(State):
    # Define the game state

class MyAction(Action):
    # Define an action structure
    
class MyObservation(Observation):
    # Define an observation structure
    

class MyPlayer(Player):
    def get_all_actions(self, state: MyState) -> list[MyAction]:
        # Return a list of actions

    def select_action(self, list[MyAction], observation: MyObservation, simulate_action_fnc: Callable[[Action], Observation]) -> MyAction:
        # Select an action for the player

class MyGame(Game):
    def log(self):
        # Define anything that should be logged for the round

    def terminal(self) -> bool:
        # Define the game-ending condition

    def observe(self, player: MyPlayer, state: MyState) -> MyObservation:
        # Return the observation for the player

    def all_actions(self, player: MyPlayer, state: MyState) -> list[MyAction]:
        # Return all possible actions for the player

    def apply_action(self, state: State, action: Action) -> State:
        # Apply the action profile and return the new state

    def calculate_reward(self,player: Player, old_state: MyState, action: MyAction, new_state: MyState) -> float:
        # Calculate the reward from the environment for the player
```
