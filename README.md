# Vayitals

An AI-powered contactless vital signs monitoring system that estimates heart rate from facial RGB video using remote photoplethysmography (rPPG). Developed for the IEEE Signal Processing Cup 2027 FaceVitals Challenge, with a focus on improving accuracy under low-light and low-resolution conditions using the UBFC-rPPG dataset.

---

## Folder Structure

| Folder | Purpose |
|---|---|
| `constraints/` | Low-light and low-resolution constraint implementations |
| `datasets/` | Dataset organization and dataset instructions |
| `experiments/` | Experimental scripts and test configurations |
| `notebooks/` | Jupyter notebooks for exploration and analysis |
| `outputs/` | Generated predictions and experiment results |
| `reports/` | Technical reports and documentation |
| `src/` | Core FaceVitals source code |

---

## 🚀 Teammate Quickstart

### 1. Clone the repository
```bash
git clone https://github.com/ATAHOPRINCE-20/Vayitals.git
cd Vayitals
```

### 2. Set up a virtual environment

**On Windows (PowerShell):**
```powershell
python -m venv .venv
.venv\Scripts\activate
```

**On Linux / macOS:**
```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Running the project
```bash
python main.py
```

---

## 🤝 Contribution Workflow

1. Always pull latest changes before starting work:
   ```bash
   git pull origin main --rebase
   ```
2. Create a feature branch for your work:
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. Commit and push your branch:
   ```bash
   git add .
   git commit -m "Descriptive commit message"
   git push origin feature/your-feature-name
   ```
4. Open a Pull Request on GitHub for review.
