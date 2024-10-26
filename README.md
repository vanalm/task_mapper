> "Is what I'm doing getting me closer to what I want?"

# AI Task Navigator

An intelligent agent that helps individuals and organizations determine if their actions are effectively moving them closer to their goals. This tool models states and tasks as a dynamic graph, managed by an LLM-based agent that uses optimization algorithms to find optimal paths toward desired objectives.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Example](#example)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
- [License](#license)

## Overview

The system:

- Builds a **state map** (graph) where each **state (node)** represents a condition or milestone with **tasks (edges)** that have associated attributes:
  - **Probability of Success (`p_success`)**
  - **Time**
  - **Cost**
- Allows dynamic editing of the graph.
- Utilizes optimization algorithms to find the best paths toward goals based on defined criteria.
- Integrates with LLM for natural language interaction, interpretation, and reporting.

This tool is could be applicable to individuals and groups, including families, companies, and governments, to plan and evaluate strategies effectively.

## Potential Features

- Agent receives user objective explicitly via chat
- Agent receives user objective implicitly via chat
- Agent helps uncover root objectives 
- Agent receives tasks and intermediate states explicitly from user
- Agent produces tasks and intermediate states related to root objective(s)
- Agent receives P(success), time, cost for each task explicitly via chat
- Agent produces estimates of P(success), time, cost for each task
- Agent collects data on time cost and success rate for each task
- Agent parses list of edges(tasks) and nodes(states)
- Edges and Nodes are instantiated
- Graph is built
- Tasks and states can be added at any time
- Task attributes can be updated at anytime within the graph.
- Agent can call optimization algorithms/functions
- Agent can report on results from optimization algorithms

## Installation

### Prerequisites

- **umm... maybe Python 3.7 or higher**
- **pip** package installer

### Steps

1. **Clone the Repository** (nothing to clone yet but this readme!)

   ```bash
   git clone https://github.com/yourusername/ai-goal-planner.git
   cd ai-goal-planner
   ```

2. **Create a Virtual Environment (Optional but Recommended)**

   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. **Install Dependencies**

   ```bash
   pip install -r requirements.txt
   ```

## Usage

### Running the Planner

```bash
python main.py
```

### Potential Workflow

1. **Define Your Goal**

   - The system will prompt you to enter your goal in natural language.
   - Example: *"I want to increase my company's revenue by 20% in the next fiscal year."*

2. **Interact with the Agent**

   - The agent may ask clarifying questions to better understand your goal.
   - Provide additional details as needed.

3. **View Generated Plan**

   - The agent will create a state map with tasks and states.
   - It will display optimal paths based on your chosen criteria (e.g., minimizing cost).

4. **Edit the Graph (Optional)**

   - You can add or remove states and tasks.
   - Adjust task attributes like time, cost, and probability of success.

5. **Run Optimization**

   - Request the agent to re-evaluate the optimal path after making changes.
   - The agent will provide updated recommendations.

6. **Generate Reports**

   - The agent can produce a summary report detailing the plan and next steps.

## Example

### Sample Interaction

```bash
Welcome to the AI-Powered Goal Achievement Planner!

Please describe the goal you'd like to accomplish:
> I want to save $10,000 for a down payment on a house within two years.

Based on your goal, here's a proposed plan:

States:
- S0: Current financial state
- S1: Reduced monthly expenses
- S2: Increased income
- S3: Investment growth
- SG: Goal state (saved $10,000)

Tasks:
- T1: Create a budget plan (S0 -> S1)
  - Time: 1 week
  - Cost: $0
  - Success Probability: 90%
- T2: Find a higher-paying job (S0 -> S2)
  - Time: 3 months
  - Cost: $0
  - Success Probability: 60%
- T3: Start a side business (S0 -> S2)
  - Time: 6 months
  - Cost: $500
  - Success Probability: 50%
- T4: Invest in low-risk funds (S1/S2 -> S3)
  - Time: 1 week
  - Cost: $0
  - Success Probability: 70%
- T5: Save monthly surplus (S1/S2/S3 -> SG)
  - Time: 24 months
  - Cost: $0
  - Success Probability: 95%

Would you like to:
1. Accept this plan
2. Modify the plan
3. Run optimization based on a specific criterion

> 3

Please select an optimization criterion:
1. Maximize Success Probability
2. Minimize Time
3. Minimize Cost
4. Weighted Combination

> 1

Optimal Path Based on Maximizing Success Probability:
- T1: Create a budget plan
- T5: Save monthly surplus

Total Estimated Time: 24 months
Total Estimated Cost: $0
Overall Success Probability: 85.5%

Would you like to proceed with this plan? (yes/no)
> yes

Generating report...
```

## Project Structure

```
ai-goal-planner/
├── README.md
├── main.py
├── graph.py
├── agent.py
├── optimization.py
├── requirements.txt
└── examples/
    └── example_scenarios.py
```

- **main.py**: Entry point of the application.
- **graph.py**: Contains classes and methods for graph structures (`State`, `TaskEdge`, `StateGraph`).
- **agent.py**: Manages interactions with the LLM and user.
- **optimization.py**: Implements optimization algorithms.
- **examples/**: Contains example scenarios and usage.

## Contributing

Contributions are welcome! Please follow these steps:

1. **Fork the Repository**

   Click the "Fork" button at the top right of this page.

2. **Clone Your Fork**

   ```bash
   git clone https://github.com/yourusername/ai-goal-planner.git
   ```

3. **Create a Branch**

   ```bash
   git checkout -b feature/your-feature-name
   ```

4. **Make Changes and Commit**

   ```bash
   git add .
   git commit -m "Add your message here"
   ```

5. **Push to Your Fork**

   ```bash
   git push origin feature/your-feature-name
   ```

6. **Submit a Pull Request**

   Go to the original repository and click "New Pull Request".

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

**Disclaimer**: This project is in the development stage. Features and functionalities are subject to change. Contributions and feedback are greatly appreciated.