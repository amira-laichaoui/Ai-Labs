# AI in Cybersecurity Labs

Labs from the AI in Cybersecurity course at ESI-SBA (2026).
Tools: Python, Jupyter, [pandas, scikit-learn, ...].

## Lab 1: Intrusion detection on UNSW-NB15
- **Goal:** [classify network traffic as normal or attack]
- **Dataset:** UNSW-NB15. Not included in this repo (too large); download it from the UNSW Canberra website and place the CSV files in `lab1/archive/`.
- **Methods:** [models you trained, preprocessing steps]
- **Results:** [best model and its accuracy / F1 score]
- **Notebook:** `lab1/Lab01_UNSW_NB15.ipynb`

## Lab 2: Visualization of intrusion detection alerts
- **Goal:** turn a large IDS alert log into charts where an attack is easy to see, then detect it automatically with a simple rule.
- **Data:** simulated one-day alert log (1 November 2026) with Python: 600 normal alerts from 40 office computers, 25 alerts from a harmless but noisy backup server, and 150 attack alerts from one external IP. Simulation means the attack location is known, so the rule can be evaluated fairly.
- **Tools:** Python, pandas, matplotlib, Jupyter.
- **Visualizations:** alerts per 10 minutes over 24 hours (the attack appears as a spike at 03:10), and the top 8 source IPs (the attacker has about 6x more alerts than the next IP).
- **Detection rule:** flag an IP that triggers more than N alerts in a 5-minute window.
  - N = 20: caught all 150 attack alerts, but 25 false alarms from the backup server (precision 0.857).
  - N = 40: caught all 150, 0 false alarms (precision 1.00). Every threshold from 30 to 100 gave the same result.
- **Limitations:** simulated data, threshold chosen and evaluated on the same data, only one attack and one noisy machine, so 100% is optimistic. A slow attacker below the threshold would evade the rule, and the rule ignores alert type and severity.
- **Notebook:** `lab2/<your notebook name>.ipynb`

## How to run
1. Clone the repo.
2. Install the requirements: `pip install pandas scikit-learn jupyter`
3. Download the datasets as described above and open the notebooks.
