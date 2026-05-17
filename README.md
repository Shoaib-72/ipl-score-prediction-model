# 🏏 IPL Score Prediction Model

ML-based system to predict IPL final innings score and chase win probability — live, mid-innings.

---

## 📊 Model Performance

| Task | Algorithm | Score |
|---|---|---|
| Final Score Prediction | XGBoost v2 | MAE **±12.5 runs**, R² **0.71** |

---

## 📁 Repo Structure

```
ipl-score-prediction-model/
├── app.py                  # Streamlit web app
├── model.pkl               # Trained XGBoost model
├── encoders.pkl            # Label encoders (teams, venues, toss)
├── meta.json               # Feature list, team/venue averages, stats
├── IPL_clean.csv.gz        # Ball-by-ball IPL dataset (2008–2024)
├── compressed_data.csv.gz  # Compressed training data
├── requirements.txt        # Python dependencies
└── model/                  # Score-prediction model files
```

---

## 🚀 Setup & Run

```bash
# 1. Clone
git clone https://github.com/Shoaib-72/ipl-score-prediction-model.git
cd ipl-score-prediction-model

# 2. Install dependencies
pip install -r requirements.txt

# 3. Run the app
streamlit run app.py
```

---

## 🔮 What It Predicts

- **Final innings score** with confidence range (e.g. *174, range 165–183*)
- **Plain-English verdict** — ✅ Likely / ⚖️ Could go either way / ❌ Unlikely

---

## ⚙️ Key Features (33 engineered)

- Current match state — runs, wickets, run rate, overs remaining
- **Momentum** — last-3-over run rate, boundaries, dot balls, wickets
- **Pressure index** — composite of recent wickets + dot balls
- Phase flags — powerplay, death overs
- Historical priors — team avg score, venue avg score
- Interaction terms — run rate × wickets remaining

---

## 🌐 Live Demo
> Try the app live — no setup needed!

🔗 **[https://your-app-link.streamlit.app](https://ipl-score-prediction-model-ss.streamlit.app/)**

---


---

## 📈 Data

- **16 seasons** — IPL 2008 to 2024
- **19 teams · 59 venues · 283,507 balls**
- Source: ball-by-ball IPL dataset (`IPL_clean.csv.gz`)

---

⭐ Star this repo if you find it useful!
