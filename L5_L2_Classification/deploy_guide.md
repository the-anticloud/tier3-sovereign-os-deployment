# Deploy Guide — sovereign-os-deployment
**Platform:** Anticloud sovereign infrastructure | Air-gap capable
**Stack:** Python 3.11, Ansible 9.0+, AIOSS_FORMAT

## Prerequisites
Python 3.11+. See stack: Python 3.11, Ansible 9.0+, AIOSS_FORMAT. AIOSS_FORMAT required. PAX 27B weights for AI-assisted features.

## AIOSS Integration
```bash
aioss init --module sovereign-os-deployment --output ./sovereign_os_deployment.aioss
aioss append --chain ./sovereign_os_deployment.aioss --payload ./output.bin --module sovereign-os-deployment
aioss verify --chain ./sovereign_os_deployment.aioss
```

## Air-Gap Deployment
```bash
# On networked machine:
pip download -r requirements.txt -d ./wheels/
# Transfer wheels/ to air-gap host, then:
pip install --no-index --find-links ./wheels/ -r requirements.txt
```

## PAX 27B Harness Wiring
```python
from anticloud_pax import PAXHarness
harness = PAXHarness(
    model_path="./pax-27b-q4.gguf",
    module="sovereign-os-deployment",
    aioss_chain="./sovereign_os_deployment.aioss",
    classification="L5_NARROW_L2_GENERAL"
)
result = harness.process(input_data)
```

## Verification
```bash
aioss verify --chain ./sovereign_os_deployment.aioss --verbose
python -m sovereign_os_deployment.tests.smoke
```
