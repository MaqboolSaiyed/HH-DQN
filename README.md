# Solving the Pickup and Delivery Problem (PDP) using a Hyper-Heuristic and Deep Q-Learning Approach

## 📘 Background

The Pickup and Delivery Problem (PDP) is a challenging NP-hard problem in the field of combinatorial optimization and logistics. It involves planning routes for a vehicle (or a fleet of vehicles) to pick up and deliver goods between different locations while minimizing cost, time, and distance, and obeying various constraints such as vehicle capacity and pickup-delivery precedence.

Conventional heuristic approaches like Nearest Neighbor or Greedy methods often fall short when it comes to adapting to varying problem landscapes. To overcome these limitations, this project explores a **Hyper-Heuristic based Deep Q-Learning (DQN)** framework to dynamically select from a pool of low-level heuristics during the route construction process.

---

## 🚀 Project Objective

The goal is to:
- Generate a synthetic PDP dataset including petrol cost, time cost, and distances.
- Implement and compare:
  - A traditional **Heuristic-based method**, and
  - A **Reinforcement Learning-based solution** using **Deep Q-Learning (DQN)** with a **Hyper-Heuristic** strategy.
- Evaluate performance metrics and understand the effectiveness of the proposed method.

---

## 🧠 Solution Overview

### Dataset Generation
- Synthetic data generated using NumPy and random distributions.
- Includes customer-pickup pairs with:
  - Distance matrix
  - Petrol costs
  - Time cost matrix

### Baseline Heuristic Solution
- A Greedy Nearest-Neighbor style algorithm was implemented to compute the cost-effective path.
- Constraints:
  - Each pickup must be followed by a corresponding delivery.
  - A node (location) can only be visited once.

### DQN + Hyper-Heuristic Model
- **State Representation**: Current node, visited nodes, petrol used, and time.
- **Action**: Selecting the next node (pickup or delivery).
- **Reward Function**: Negative cumulative cost (petrol + time).
- **Policy**: ε-greedy for exploration-exploitation balance.
- **Hyper-Heuristic**: The RL agent learns to select the best low-level heuristic dynamically instead of a fixed strategy.

---

## 📊 Results and Conclusion

- The **DQN-based approach outperformed** the traditional heuristic in terms of minimizing the **overall cost** (distance + petrol + time).
- The model **learned better strategies** over episodes, indicating successful convergence of the Q-learning agent.
- The **Hyper-Heuristic mechanism** provided the flexibility to adapt to varying PDP scenarios by leveraging different low-level heuristics during training.
- This hybrid methodology can be extended to larger PDP instances or integrated with fleet management systems.

---

## 🛠️ Technologies Used

- Python
- NumPy
- Matplotlib
- TensorFlow / PyTorch (based on your implementation)
- Reinforcement Learning (Deep Q-Learning)
- Optimization Techniques

---


---

## 📌 Future Work

- Integrate capacity constraints and time windows.
- Test with real-world datasets (e.g., courier or logistics networks).
- Scale the model for multi-vehicle routing.

---

## 👨‍💻 Author

**Maqbool Husain Saiyed**

This project is part of my ongoing research in AI/ML applications to combinatorial optimization. Feel free to explore, contribute, or reach out for collaboration!

---

## 📄 License

This project is licensed under the MIT License.
