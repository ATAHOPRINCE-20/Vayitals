# FaceVitals — IEEE Signal Processing Cup 2027

**Contactless Vital Signs Estimation Using Remote Photoplethysmography (rPPG)**


\


## 1. Project Overview

FaceVitals is a research and development project focused on estimating physiological vital signs from facial RGB video using Remote Photoplethysmography (rPPG).

The project is being developed for the IEEE Signal Processing Cup 2027 FaceVitals Challenge.

Our initial objective is to develop a system that estimates Heart Rate (HR) from facial video. The system will subsequently be extended to estimate oxygen saturation (SpO₂) and blood pressure (BP) in later challenge rounds.

### Round 1 Objectives

- Develop a working contactless heart-rate estimation pipeline.
- Extract physiological signals from facial regions.
- Process and filter the extracted signals.
- Estimate heart rate from facial video.
- Evaluate predictions against reference physiological measurements.
- Investigate performance under at least two challenge constraints.

### Selected Round 1 Constraints

| Constraint         | Assigned Member | Description                                             |
| ------------------ | --------------- | ------------------------------------------------------- |
| C1: Low Light      | SHABELLAH       | Improve performance under low illumination (≤50 lux).   |
| C4: Low Resolution | SHARON          | Investigate performance using reduced-resolution video. |

**Dataset:** UBFC-rPPG Set 2
**Programming Language:** Python

---

## 2. Team Members and Responsibilities

| Member    | Position                             | Assigned Responsibility                                                |
| --------- | ------------------------------------ | ---------------------------------------------------------------------- |
| PRINCE    | Team Lead & Integration Engineer     | Architecture, GitHub management, integration and final submission      |
| HAPPY     | Dataset & Evaluation Engineer        | Dataset management, ground-truth processing and performance evaluation |
| EDRIEN    | Core rPPG & Computer Vision Engineer | Face detection, ROI extraction, signal processing and HR estimation    |
| SHABELLAH | Low-Light Constraint Engineer        | C1 implementation and experiments                                      |
| SHARON    | Low-Resolution Constraint Engineer   | C4 implementation and experiments                                      |

### PRINCE — Team Lead

- Maintain the project architecture and GitHub repository.
- Coordinate team activities and monitor deadlines.
- Integrate modules developed by other members.
- Maintain the main application entry point (`main.py`).
- Review pull requests before merging into `main`.
- Coordinate final testing, documentation and submission.

### HAPPY — Dataset & Evaluation

- Download and organize UBFC-rPPG Set 2.
- Inspect video metadata and ground-truth files.
- Implement dataset loading and reference signal parsing.
- Ensure predictions are correctly aligned with reference measurements.
- Calculate MAE, RMSE and correlation.
- Generate evaluation graphs and result tables.

### EDRIEN — Core rPPG Algorithm

- Implement face detection and tracking.
- Extract forehead and cheek regions of interest.
- Extract RGB signals from facial regions.
- Implement signal detrending and filtering.
- Develop heart-rate estimation algorithms.
- Investigate Green Channel, CHROM and POS methods.
- Provide a tested core processing pipeline.

### SHABELLAH — Low-Light Constraint (C1)

- Investigate the effect of low illumination on rPPG.
- Implement low-light image preprocessing.
- Investigate brightness and contrast enhancement.
- Test HR estimation under low-light conditions.
- Compare results before and after preprocessing.
- Document experimental methodology and limitations.

### SHARON — Low-Resolution Constraint (C4)

- Investigate the effect of reduced resolution on rPPG.
- Implement video resizing and preprocessing.
- Test face detection and ROI extraction at different resolutions.
- Evaluate HR estimation accuracy at reduced resolutions.
- Generate comparison graphs and document findings.

---

## 3. Repository Structure

All team members must follow the agreed project structure.

```text
FaceVitals/
│
├── constraints/
│   ├── README.md
│   ├── low_light.py
│   └── low_resolution.py
│
├── datasets/
│   └── README.md
│
├── experiments/
│   └── README.md
│
├── notebooks/
│   └── README.md
│
├── outputs/
│   ├── README.md
│   ├── graphs/
│   └── predictions/
│
├── reports/
│   └── README.md
│
├── src/
│   ├── README.md
│   ├── video_loader.py
│   ├── face_detection.py
│   ├── roi_extraction.py
│   ├── signal_extraction.py
│   ├── signal_filtering.py
│   ├── heart_rate.py
│   └── evaluation.py
│
├── main.py
├── requirements.txt
├── .gitignore
└── README.md
```

Members may propose additional files or folders, but should communicate structural changes to the team lead before introducing them.

---

## 4. GitHub Branching Strategy

We use a feature-branch workflow to allow members to work independently without directly modifying the stable version of the project.

### Official Branches

| Branch                       | Assigned Member | Purpose                    |
| ---------------------------- | --------------- | -------------------------- |
| `main`                       | PRINCE          | Stable, integrated project |
| `feature/dataset-evaluation` | HAPPY           | Dataset and evaluation     |
| `feature/rppg-algorithm`     | EDRIEN          | Core rPPG implementation   |
| `feature/low-light`          | SHABELLAH       | Low-light constraint       |
| `feature/low-resolution`     | SHARON          | Low-resolution constraint  |

### Important Branch Rules

1. Never work directly on `main`.
2. Every member must work on their assigned branch.
3. Do not push unfinished or untested code to `main`.
4. All contributions must be submitted through Pull Requests.
5. PRINCE is responsible for reviewing and merging Pull Requests.
6. Do not merge another member's work without coordination.
7. Never force-push to shared branches without team approval.

---

## 5. Initial Setup for Team Members

Each member must have installed:

- Git
- Python 3.10 or later
- Visual Studio Code or another Python IDE
- GitHub account with repository access

### Step 1: Clone the Repository

Replace `YOUR-USERNAME` with the GitHub repository owner's username.

```bash
git clone https://github.com/ATAHOPRINCE-20/Vayitals.git
```

Enter the project:

```bash
cd Vayitals
```

### Step 2: Switch to Your Assigned Branch

HAPPY:

```bash
git switch --track origin/feature/dataset-evaluation
```

EDRIEN:

```bash
git switch --track origin/feature/rppg-algorithm
```

SHABELLAH:

```bash
git switch --track origin/feature/low-light
```

SHARON:

```bash
git switch --track origin/feature/low-resolution
```

PRINCE:

```bash
git switch main
```

If a member has already created their local branch, they can use:

```bash
git switch your-branch-name
```

### Step 3: Create a Python Virtual Environment

```bash
python -m venv venv
```

Activate on Windows:

```powershell
.\venv\Scripts\Activate.ps1
```

Activate on Linux/macOS:

```bash
source venv/bin/activate
```

### Step 4: Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 6. Daily Git Workflow

Every team member must follow this workflow.

### A. Before Starting Work

Make sure you are on your assigned branch:

```bash
git branch --show-current
```

Get the latest repository updates:

```bash
git fetch origin
```

Merge the latest stable changes into your working branch:

```bash
git merge origin/main
```

If conflicts occur, resolve them carefully before continuing. Do not overwrite another member's work.

### B. After Making Changes

Check the modified files:

```bash
git status
```

Stage your changes:

```bash
git add .
```

Commit your work with a meaningful message:

```bash
git commit -m "Implement low-light preprocessing"
```

Push your changes:

```bash
git push origin your-branch-name
```

### C. Submitting Completed Work

1. Open the GitHub repository.
2. Navigate to Pull Requests.
3. Click New Pull Request.
4. Select your feature branch as the source.
5. Select `main` as the destination.
6. Write a description of your changes.
7. Submit the Pull Request.
8. Wait for review and approval from PRINCE.

### D. After Your Pull Request Is Merged

Update your working branch:

```bash
git fetch origin
git merge origin/main
```

Continue working only after confirming that your branch contains the latest stable code.

---

## 7. Coding Standards

To maintain consistency across the project:

1. Use meaningful Python variable and function names.
2. Follow Python naming conventions:
   - Functions: `snake_case`
   - Variables: `snake_case`
   - Classes: `PascalCase`
   - Constants: `UPPER_CASE`
3. Add comments where implementation logic is not obvious.
4. Add docstrings to important functions.
5. Avoid duplicating functionality already implemented by another member.
6. Do not hardcode local computer paths.
7. Use relative paths or configuration settings.
8. Test your code before committing it.
9. Keep each module focused on one responsibility.
10. Communicate changes that affect shared function interfaces.

### Example Function Documentation

```python
def estimate_heart_rate(signal, fps):
    """
    Estimate heart rate from a filtered rPPG signal.

    Args:
        signal: Filtered physiological signal.
        fps: Sampling frequency of the signal.

    Returns:
        Estimated heart rate in beats per minute.
    """
    pass
```

---

## 8. Module Integration Requirements

Every member must provide clear input and output interfaces.

| Module            | Expected Input                    | Expected Output             |
| ----------------- | --------------------------------- | --------------------------- |
| Video Loader      | Video file path                   | Video frames and metadata   |
| Face Detection    | Video frames                      | Face coordinates            |
| ROI Extraction    | Frames and face coordinates       | Facial ROI regions          |
| Signal Extraction | Facial ROI frames                 | RGB time-series signals     |
| Signal Filtering  | Raw RGB-derived signal            | Filtered signal             |
| HR Estimation     | Filtered signal and sampling rate | HR in BPM                   |
| Evaluation        | Predicted HR and reference HR     | MAE, RMSE and correlation   |
| Low-Light         | Video frames                      | Processed frames            |
| Low-Resolution    | Video frames                      | Resized or processed frames |

Function interfaces must be agreed upon before integration. Members should not independently change shared interfaces without notifying the team.

---

## 9. Data Management and Security

- Do not upload large raw datasets directly to GitHub.
- Do not commit virtual environments.
- Do not commit passwords, API keys or `.env` files.
- Do not upload restricted challenge data without the required permission.
- Keep generated outputs organized.
- Share dataset acquisition instructions in `datasets/README.md`.
- Use approved public datasets and document their sources.

Where necessary, use Git LFS or approved external storage for large files and artifacts.

---

## 10. Testing and Experimentation

Every experimental result must be reproducible.

For each experiment, document:

- Experiment name.
- Dataset and subjects used.
- Video resolution and frame rate.
- Processing method.
- Parameters and configuration.
- Ground-truth reference.
- Predicted HR.
- Evaluation metrics.
- Observations and limitations.

Do not report simulated conditions as real-world measurements.

For example, digitally darkened video is a simulated low-light experiment and must be distinguished from video recorded at a measured illumination level of 50 lux or below.

---

## 11. Project Timeline

| Date                 | Milestone                                  |
| -------------------- | ------------------------------------------ |
| November 10–12, 2026 | Repository setup and dataset inspection    |
| November 13–16, 2026 | Baseline HR estimation pipeline            |
| November 17–19, 2026 | Low-light and low-resolution modules       |
| November 20–22, 2026 | Integration and constraint experiments     |
| November 23–25, 2026 | Evaluation and algorithm comparisons       |
| November 26–28, 2026 | Technical report, slides and demonstration |
| November 29, 2026    | Final integration and testing              |
| November 30, 2026    | Round 1 submission                         |

---

## 12. Communication and Accountability

Every member should provide regular progress updates.

Progress updates should contain:

1. What I completed.
2. What I am currently working on.
3. What I plan to complete next.
4. Any challenges or blockers.

Members must communicate before changing shared project architecture, interfaces or dependencies.

---

## 13. Definition of Done

A task is considered complete when:

- The implementation is functional.
- The code has been tested.
- The expected output has been verified.
- The code follows project conventions.
- Relevant documentation has been added.
- Changes have been committed and pushed.
- A Pull Request has been submitted for review.

---

## 14. Our Team Goal

Our goal is to develop a reproducible, reliable and scientifically evaluated contactless heart-rate estimation system.

Every team member is responsible for the quality of their assigned module and for contributing to the success of the complete FaceVitals project.

**Team Lead:** PRINCE
**Team Members:** HAPPY, EDRIEN, SHABELLAH, SHARON
**Dataset:** UBFC-rPPG Set 2
**Round 1 Deadline:** 30 November 2026

**Let's build FaceVitals together.**
