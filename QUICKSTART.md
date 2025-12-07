# 🚀 Quick Start Guide

## CloudTrail Threat Detection & Security Analytics

---

## ⚡ 5-Minute Quick Start

### Option 1: Jupyter Notebook (Recommended for Learning)

```bash
# 1. Install dependencies
pip install -r requirements.txt

# 2. Start Jupyter
jupyter notebook

# 3. Open CloudTrail_Threat_Detection_Analytics.ipynb

# 4. Run cells sequentially (starts with Section 1)
```

### Option 2: Docker (Recommended for Production)

```bash
# 1. Build and run
docker-compose up

# 2. Access Jupyter at http://localhost:8888

# 3. Optional: Access Grafana at http://localhost:3000
```

### Option 3: CLI (Recommended for Automation)

```bash
# 1. Install
pip install -r requirements.txt

# 2. Initialize project
python cli.py init

# 3. Run analysis
python cli.py analyze -i data/ -o artifacts/

# 4. Generate report
python cli.py report -i artifacts/ -o report.html
```

---

## 📋 Prerequisites

- **Python**: 3.8 or higher
- **Memory**: 8GB RAM minimum
- **Disk**: 10GB free space
- **OS**: Windows, Linux, or macOS

---

## 🎯 Common Tasks

### Train a Model

```python
from utils import ConfigManager
from sklearn.ensemble import RandomForestClassifier

# Load config
config = ConfigManager('config.yaml')

# Your training code here
```

### Generate Visualizations

```python
from visualization import SecurityDashboard
import pandas as pd

# Create dashboard
dashboard = SecurityDashboard(theme='dark')

# Create anomaly scatter
fig = dashboard.create_anomaly_scatter(
    df,
    x_col='umap_1',
    y_col='umap_2',
    color_col='cluster'
)

fig.show()
```

### Detect Anomalies

```python
from utils import AnomalyDetector
import numpy as np

# Your feature matrix
X = np.random.randn(1000, 10)

# Detect anomalies
scores = AnomalyDetector.isolation_forest_score(X)

# Get top anomalies
top_10_anomalies = np.argsort(scores)[-10:]
```

---

## 🔧 Configuration

### Enable Sample Mode (Fast Testing)

Edit `config.yaml`:

```yaml
global:
  sample_mode: true
  sample_size: 1000  # Start small
```

### Adjust Model Parameters

```yaml
models:
  xgboost:
    n_estimators: 100  # Increase for better performance
    max_depth: 6
    learning_rate: 0.1
```

### Configure Alerts

```yaml
alerting:
  enabled: true
  channels:
    slack:
      enabled: true
      webhook_url: "YOUR_WEBHOOK_URL"
```

---

## 📊 Understanding Outputs

### Artifacts Structure

```
artifacts/
├── section_01/
│   ├── dataset_summary.json      # Data statistics
│   └── executive_summary.txt     # High-level overview
├── section_08/
│   ├── principal_stats.json      # IAM analysis
│   └── suspicious_principals.csv # Flagged users
├── section_17/
│   └── model_comparison.json     # Model performance
└── section_23/
    └── priority_alert_queue.csv  # Top alerts
```

### Key Files to Check

1. **dataset_summary.json** - Start here for data overview
2. **model_comparison.json** - Compare ML model performance
3. **priority_alert_queue.csv** - Top security alerts
4. **cluster_profiles.json** - Anomaly cluster characteristics

---

## 🐛 Troubleshooting

### Issue: Module Not Found

```bash
# Solution: Install dependencies
pip install -r requirements.txt
```

### Issue: Out of Memory

```python
# Solution: Enable sample mode in config.yaml
global:
  sample_mode: true
  sample_size: 5000
```

### Issue: Slow Execution

```bash
# Solution 1: Reduce sample size
# Solution 2: Use Docker with more resources
# Solution 3: Enable parallel processing
```

### Issue: Import Errors in Notebook

```python
# Add at top of notebook
import sys
from pathlib import Path
sys.path.append(str(Path.cwd()))
```

---

## 📚 Learning Path

### For Beginners:

1. **Start**: Run notebook in sample mode (Section 1-6)
2. **Learn**: Review EDA sections (Section 7-11)
3. **Experiment**: Try different models (Section 17)
4. **Visualize**: Explore plots in `plots/` directory

### For Advanced Users:

1. **Optimize**: Tune hyperparameters (Section 18)
2. **Deploy**: Use Docker/Kubernetes configs
3. **Integrate**: Set up SIEM connections
4. **Scale**: Enable distributed processing

---

## 🔗 Key Resources

| Resource | Location | Description |
|----------|----------|-------------|
| **Main Notebook** | `CloudTrail_Threat_Detection_Analytics.ipynb` | Complete workflow |
| **Configuration** | `config.yaml` | All settings |
| **Utilities** | `utils.py` | Helper functions |
| **Visualization** | `visualization.py` | Plot templates |
| **Tests** | `tests/` | Test suite |
| **Documentation** | `README.md` | Full documentation |

---

## 💡 Pro Tips

1. **Always start with sample mode** for quick iterations
2. **Check artifacts after each section** for quality
3. **Use CLI for automation** and batch processing
4. **Enable logging** in config for debugging
5. **Review plots** before making decisions
6. **Run tests** before deployment
7. **Monitor memory usage** with large datasets
8. **Use GPU** for LSTM training (Section 21)

---

## 🎯 Success Checklist

- [ ] Dependencies installed
- [ ] Configuration customized
- [ ] Sample mode tested
- [ ] Artifacts generated
- [ ] Visualizations reviewed
- [ ] Models trained
- [ ] Tests passing
- [ ] Ready for deployment

---

## 📞 Getting Help

1. **Check** ENHANCEMENTS.md for full feature list
2. **Review** CONTRIBUTING.md for development guidelines
3. **Read** README.md for comprehensive documentation
4. **Run** `python cli.py --help` for CLI usage

---

## ⚡ Most Common Commands

```bash
# Install everything
pip install -r requirements-dev.txt

# Run all tests
pytest tests/ -v --cov=.

# Start Jupyter
jupyter notebook

# Run CLI analysis
python cli.py analyze -i data/ -o artifacts/

# Start Docker stack
docker-compose up -d

# Check configuration
python cli.py show-config

# Initialize new project
python cli.py init --output ./new-project
```

---

## 🎉 Ready to Go!

You're all set! Choose your preferred method above and start analyzing CloudTrail logs.

**Need more help?** Check the comprehensive [README.md](README.md)

**Happy Analyzing! 🔒**
