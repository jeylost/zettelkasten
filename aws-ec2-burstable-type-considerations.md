---
tags:
  - aws
  - devops
  - ec2
  - issue
  - network
---
Burstable performance instances are well-suited for development and staging environments, where the workload is characterized by occasional spikes. Firstly, they are more cost-effective than instances with similar specifications. Secondly, they allow temporary exceedance of nominal CPU and network bandwidth limits to handle occasional high loads or bursts. These limits are called "baseline". You can find network bandwidth baselines [here](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/general-purpose-instances.html#general-purpose-performance) and CPU baselines [here](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/burstable-credits-baseline-concepts.html)

# Indicators of burstable instance related problems
- Under a high constant load, your instance starts to experience a lot of timeouts over time, dropping connections, etc.
- Your instance's performance gradually decreases over time, nearing zero.
# How to determine it's time to move from burstable type or scale it
1. Burstable instances in the `Monitoring` section contain metrics named `CPU credit usage (count)` and `CPU credit balance (count)`. If your instance doesn't earn enough credits and spends them too often, it's time to consider non-burstable instances. 
2. Network bandwidth is a tricky thing; it's better to read about it [here](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-network-bandwidth.html) first. Unlike CPU metrics, AWS doesn't provide any metrics to see the actual number of credits your instance has earned and spent. Just check the `Monitoring` section to determine whether your instance exceeds the baseline or not, using the `Network In` and `Network Out` metrics.
