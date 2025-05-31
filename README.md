<h1 align="center">CodeInsight 🚀💻 — FAANG-Level AI Code Pattern Detector & Explainer</h1>

<p align="center">
  <b>Elite AI-powered code explainer for developers who want to understand code like a FAANG engineer.</b><br/>
  CodeInsight detects algorithmic patterns (like DFS, DP, Greedy, Backtracking) and explains code with clean, professional documentation.<br/>
  Whether you're preparing for interviews — CodeInsight delivers structured insights, high-level takeaways, sample I/O, and complexity analysis.<br/>
  Built for clarity. Powered by AI. Crafted for serious developers.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Pattern%20Detection-DFS%2C%20DP%2C%20Greedy%2C%20Backtracking-blue?style=flat-square" />
  <img src="https://img.shields.io/badge/License-MIT-yellow?style=flat-square" />
</p>

<p align="center">
  Detects common algorithmic patterns and explains them like a FAANG engineer — backed by MIT License.
</p>

---

## 🧠 What is CodeInsight?

**CodeInsight** is an AI-powered tool that analyzes source code and generates structured, professional-grade explanations — the kind you'd expect from senior engineers at companies like Google, Amazon, or Microsoft.

Whether you're prepping for interviews, building dev tools, or documenting algorithms, **CodeInsight** delivers high-quality, pattern-aware breakdowns of your code.

---

## 🚀 Features

- 🔍 **Pattern Detection**  
  Recognizes standard patterns: DFS, BFS, DP, Greedy, Two Pointers, Backtracking, Graph Traversals, and more.

- 🧠 **AI-Powered Explanations**  
  Outputs code with inline comments + summary — explained like a FAANG SDE-2/3 would.

- 📐 **Segmented Output Format**  
  - `// Pattern Detected:` – Classification (e.g., "Dynamic Programming – 0/1 Knapsack")  
  - **Inline commented code** – Clear and intentional explanation  
  - `// Key Insights:` – High-level bullet points  
  - `// Sample Input and Output:` – Concrete usage examples  
  - `// Time and Space Complexity:` – Formal analysis

- 🧱 **Language Support**  
  Currently supports: Python, JavaScript, Java, C++

---

## 📦 Example Output

> Input: Python code solving 0/1 Knapsack using bottom-up DP

```python
// Pattern Detected: Dynamic Programming — 0/1 Knapsack using Bottom-Up Tabulation

def knapsack(weights, values, capacity):
    n = len(weights)
    dp = [[0 for _ in range(capacity + 1)] for _ in range(n + 1)]  # Initialize DP table

    for i in range(1, n + 1):  # Iterate through items
        for w in range(1, capacity + 1):  # Iterate through capacities
            if weights[i - 1] <= w:
                # Choose max between not including or including the item
                dp[i][w] = max(
                    dp[i - 1][w],
                    dp[i - 1][w - weights[i - 1]] + values[i - 1]
                )
            else:
                # Item too heavy; carry forward previous best
                dp[i][w] = dp[i - 1][w]

    return dp[n][capacity]  # Final result

// Key Insights:
- Uses bottom-up dynamic programming to build optimal substructure.
- Iterates through item/capacity pairs to maximize value within limits.
- Avoids repeated subproblem computation by storing intermediate results.
- Works well for standard 0/1 constraints (items cannot be reused).
- Space can be optimized to 1D DP if required.

// Sample Input and Output:
weights = [1, 3, 4, 5]
values = [10, 40, 50, 70]
capacity = 8
Output: 110

// Time and Space Complexity:
Time: O(n * capacity)
Space: O(n * capacity)
```

---

## 🧩 Use Cases

- ✅ Competitive programming prep  
- ✅ Automated codebase documentation  
- ✅ Coding platform + devtool integrations  
- ✅ Interview-ready explanations for portfolio and GitHub  
- ✅ Improving technical communication

---

## 🛠 Tech Stack

- 💬 **AI Models**: GPT-4 / Claude / Local LLMs (via OpenRouter or LMStudio)  
- ⚙️ **Backend**: FastAPI (Python)  
- 💻 **Frontend (optional)**: React.js + Tailwind CSS + Framer Motion  
- 🚀 **Deployment**: Vercel (Frontend), Render or Localhost (Backend)  
- 🧠 **Language Support**: Python (Current), Java & JavaScript (Coming Soon)

---

## 🧪 Getting Started

```bash
# Clone the repository
git clone https://github.com/sreedatthap/codeinsight-ai.git
cd codeinsight-ai

# Install dependencies
pip install -r requirements.txt

# Run the backend server
uvicorn app.main:app --reload

# Open the interactive docs
http://localhost:8000/docs
```

---

## 📄 License

MIT License — free to use for personal and commercial projects.

---

## 💬 Credits

Built with ❤️ by **Sree Dattha P** — inspired by the way FAANG engineers explain code during interviews, whiteboarding rounds, and code reviews.

---

## 🌟 Like This Project?

If you find this helpful:

- 🌟 Star this repo
- 🍴 Fork it
- 📢 Share with other devs preparing for interviews!

---

<div align="center">
  <sub>Made with precision & love by <a href="https://github.com/sreedatthap">Sree Dattha P</a> | 2025</sub>
</div>
