# Explainable AI zur Cyberangriffserkennung mit CICIDS2017

Dieses Projekt untersucht, wie Machine-Learning-Modelle Cyberangriffe im Netzwerkverkehr erkennen können und wie Explainable AI genutzt werden kann, um Modellentscheidungen nachvollziehbar zu erklären.

## Ziel des Projekts

Ziel ist die binäre Klassifikation von Netzwerkverkehr in:

- BENIGN = normaler Netzwerkverkehr
- ATTACK = bösartiger Netzwerkverkehr

Anschließend werden die wichtigsten Netzwerkmerkmale mithilfe von Feature Importance und SHAP analysiert.

## Datensatz

Verwendet wird der CICIDS2017-Datensatz des Canadian Institute for Cybersecurity.

Für das Mini-Projekt wird zunächst folgende Datei genutzt:

- Friday-WorkingHours-Morning.pcap_ISCX.csv
- Friday-WorkingHours-Afternoon-PortScan.pcap_ISCX.csv
- Friday-WorkingHours-Afternoon-DDos.pcap_ISCX.csv

Die Originaldaten werden nicht im Repository gespeichert und müssen separat heruntergeladen werden.

## Methodik

1. Data Understanding
2. Data Preparation
3. Descriptive Analytics
4. Predictive Analytics mit Random Forest
5. Evaluation mit Accuracy, Precision, Recall und F1-Score
6. Explainable AI mit SHAP

## Projektstruktur

- `data/raw/` enthält lokale Originaldaten, nicht in GitHub
- `notebooks/` enthält die Analyse-Notebooks
- `outputs/figures/` enthält erzeugte Grafiken
- `outputs/reports/` enthält Ergebnisse und Zusammenfassungen