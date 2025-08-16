# Wumpus World AI Agent

This Jupyter notebook implements an AI agent that navigates a Wumpus World environment using logical knowledge bases (KB) in both CNF and Horn clause forms. The agent explores the environment, gathers percepts (stench, breeze), and updates its KB to make safe moves.

## Key Components

### Knowledge Bases
1. **KB_CNF**: Uses Conjunctive Normal Form with resolution-based inference
2. **KB_Horn**: Uses Horn clauses with forward chaining inference

### Environment
- `gym.make('Wumpus-v0')` creates the Wumpus World grid environment
- The agent moves through the world step-by-step (11 steps shown)

### How It Works
1. The agent starts at (1,1) and receives percepts (stench/breeze)
2. It updates its KB with logical rules about:
   - Wumpus locations based on stench
   - Pit locations based on breeze
   - Safe locations it has visited
3. The KBs answer queries about dangers (`ASK("W12")`, `ASK("P23")` etc.)
4. The agent uses this information to navigate safely

### Rules Implemented
- Stench implies adjacent Wumpus
- Breeze implies adjacent pit
- Visited locations are marked safe
- Eliminates impossible locations as it explores

## Usage
Run the notebook cells sequentially to see the agent explore the world and update its knowledge bases. The environment is rendered after each step.

## Requirements
- Python 3
- gym
- fh_ac_ai_gym (custom Wumpus environment)
