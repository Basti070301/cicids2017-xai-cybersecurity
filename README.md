# Explainable AI zur Cyberangriffserkennung mit CICIDS2017

Im Rahmen des Moduls **Business Analytics** an der **FOM Hochschule** untersucht dieses Projekt, wie Machine-Learning-Modelle zur Erkennung von Cyberangriffen im Netzwerkverkehr eingesetzt werden können und wie Explainable AI dazu beiträgt, die getroffenen Modellentscheidungen nachvollziehbar zu interpretieren.

## Ziel des Projekts

Ziel ist die binäre Klassifikation von Netzwerkverkehr in:

- **BENIGN** = normaler Netzwerkverkehr
- **ATTACK** = bösartiger Netzwerkverkehr

Anschließend werden die wichtigsten Netzwerkmerkmale mithilfe von **Feature Importance** und **SHAP** analysiert, um die Entscheidungen des Modells transparenter zu machen.

## Datensatz

Verwendet wird der **CICIDS2017-Datensatz** des Canadian Institute for Cybersecurity.

Für das Mini-Projekt werden folgende Dateien verwendet:

- `Friday-WorkingHours-Morning.pcap_ISCX.csv`
- `Friday-WorkingHours-Afternoon-PortScan.pcap_ISCX.csv`
- `Friday-WorkingHours-Afternoon-DDos.pcap_ISCX.csv`

Diese Dateien enthalten normalen Netzwerkverkehr sowie die Angriffstypen:

- Bot
- PortScan
- DDoS

Für die Modellierung werden alle Angriffstypen zu einer gemeinsamen Angriffsklasse zusammengefasst.

Die Originaldaten werden nicht im Repository gespeichert und müssen separat heruntergeladen werden.

## Methodik

Das Projekt orientiert sich an einem typischen Analytics-Workflow:

1. **Data Understanding**  
   Untersuchung der verwendeten CICIDS2017-Dateien, Labels, Spaltenstruktur und Datenqualität.

2. **Data Preparation**  
   Zusammenführung der CSV-Dateien, Bereinigung fehlerhafter Werte und Erstellung einer binären Zielvariable.

3. **Model Training**  
   Training eines Random-Forest-Modells zur Klassifikation von normalem und bösartigem Netzwerkverkehr.

4. **Evaluation**  
   Bewertung des Modells mit Accuracy, Precision, Recall, F1-Score und Confusion Matrix.

5. **Explainable AI**  
   Interpretation der Modellentscheidungen mithilfe von Feature Importance und SHAP.

## Modell

Für die Klassifikation wird ein **Random Forest Classifier** verwendet.

Gründe für die Modellwahl:

- geeignet für tabellarische Netzwerkdaten
- robust gegenüber unterschiedlichen Merkmalsverteilungen
- gute Performance bei Klassifikationsproblemen
- interpretierbar über Feature Importance
- kompatibel mit SHAP

## Ergebnisse

Das trainierte Modell erreicht auf den Testdaten eine sehr hohe Klassifikationsleistung. Die Evaluation zeigt, dass der Großteil der normalen Netzwerk-Flows und Angriffe korrekt erkannt wird.

Zusätzlich zeigt die Explainable-AI-Analyse, welche Netzwerkmerkmale die Modellentscheidung besonders stark beeinflussen. Besonders relevant sind unter anderem paketbezogene Merkmale, TCP-Flags und Verbindungsparameter.

## Projektstruktur

```text
.
├── data/
│   ├── raw/                 # lokale Originaldaten, nicht in GitHub
│   └── processed/           # bereinigte Daten, nicht in GitHub
│
├── notebooks/
│   ├── 01_data_understanding.ipynb
│   ├── 02_data_preparation.ipynb
│   ├── 03_model_training.ipynb
│   ├── 04_evaluation.ipynb
│   └── 05_xai_shap_analysis.ipynb
│
├── outputs/
│   ├── figures/             # erzeugte Grafiken
│   ├── models/              # gespeicherte Modelle, nicht in GitHub
│   └── reports/             # Evaluationsergebnisse
│
├── requirements.txt
├── .gitignore
└── README.md