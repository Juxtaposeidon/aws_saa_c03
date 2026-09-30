# Disaster Recovery Strategies

| Strategy | What's running normally | RTO | Cost |
| --- | --- | --- | --- |
| Backup & Restore | **Nothing** (just backups in S3). For DR, **provision everything from scratch** with the backups: spin up new instances, restore DB from a snapshot | Hours | Cheapest |
| Pilot Light | Only the **most critical core** (e.g. DB) at minimal size in DR. Everything else exists as **AMIs/templates ready to launch** | Tens of minutes | Low |
| Warm Standby | Everything, scaled down (fewer/smaller instances) **but FULLY FUNCTIONAL** | Minutes | Medium |
| Multi-Site Active-Active | Everything, full scale | Near-zero | Most expensive |

---

[← Placement Groups](27-placement-groups.md) · [Contents](../README.md#contents) · [CloudFormation →](29-cloudformation.md)
