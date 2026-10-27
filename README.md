# Tony Kenga

**Junior Data Scientist | Aspiring Machine Learning Engineer**
Final-year BSc Data Science student at KCA University · Nairobi, Kenya

I use Python, SQL and applied machine learning to investigate data problems and build reproducible analytical tools. My portfolio includes a final-year technology-trajectory study, a student-support prototype, database design and containerized ML exercises. I document limitations alongside results so project claims stay tied to evidence.

[Email](mailto:tonykenga23@gmail.com) · [GitHub repositories](https://github.com/Tony405-spec?tab=repositories)

## Featured work

### [TechPulse](https://github.com/Tony405-spec/TechPulse)
A final-year research prototype for exploring software-technology trajectories using community activity, developer-survey signals and SQL analytics. It includes a Python data pipeline, scikit-learn model comparisons, explainability artifacts and a Streamlit dashboard.

**Evidence and limits:** the survey aggregation contains 685 technology-year rows across 267 technologies. In the checked local development run, the Random Forest matched the majority-class baseline on accuracy (0.966); its weighted F1 was 0.955 versus 0.949 for that baseline. This small difference does not establish useful predictive performance. The local fallback includes development proxies, so the results are exploratory.

`Python` · `PostgreSQL` · `scikit-learn` · `Streamlit` · `SHAP`

### [Karibu Campus: Student Support and Outcome Modelling](https://github.com/Tony405-spec/kenyan-campus-student-support)
A coursework project pairing a reproducible three-class outcome-modelling pipeline with a separate campus-support prototype. The modelling uses the public UCI student-outcomes dataset from Portugal; the Streamlit support hub includes a deterministic intent-based chat and locally relevant support resources.

**Evaluation:** held-out macro-F1 0.716 and accuracy 0.756 on the reported split. The model has not been validated on Kenyan university data and is not an operational early-warning or clinical system. The app uses synthetic assessment profiles and must not store real student records.

`Python` · `pandas` · `scikit-learn` · `Streamlit` · `pytest`

### [Docker ML Portfolio](https://github.com/Tony405-spec/docker-ml-portfolio)
A four-week learning project using Docker and TensorFlow/CIFAR-10 to practice repeatable ML environments, container configuration, data handling and training scripts. It is an educational exercise, not a production deployment; no benchmark result is claimed.

`Python` · `TensorFlow` · `Docker`

### [Timetable Management System](https://github.com/Tony405-spec/Timetable-Management-System-Project)
A PostgreSQL schema for courses, lecturers, streams, rooms and timetable allocation. It uses uniqueness constraints to prevent several common same-slot conflicts and a trigger to record room allocations. The README documents limits in its text-based time slots and the lack of migration tests and seed data.

`PostgreSQL` · `SQL`

### [AgriPredict Kenya](https://github.com/Tony405-spec/AgriPredict-Kenya)
A Streamlit crop-yield prediction prototype with input validation, a model card and local SQLite analytics. The current model uses generated training data and is not externally validated, so predictions are educational estimates rather than agronomic advice.

`Python` · `scikit-learn` · `Streamlit` · `SQLite`

## Technical toolkit

- **Programming:** Python, SQL, TypeScript, R
- **Data work:** pandas, NumPy, notebook-based analysis, PostgreSQL, SQLite
- **Machine learning:** scikit-learn, TensorFlow; applied classification and model evaluation
- **Apps and engineering:** Streamlit, Docker, GitHub Actions, pytest, Git

## Current focus

Applied model evaluation, leakage-safe validation, SQL analytics and reproducible data-to-application workflows.

## Contact

[tonykenga23@gmail.com](mailto:tonykenga23@gmail.com)
