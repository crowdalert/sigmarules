# CrowdAlert Sigma Rules

A repository of [Sigma](https://sigmahq.io) detection rules used by [CrowdAlert](https://crowdalert.com)

## How to use the rules:

* Using the native SigmaHQ converter: https://github.com/SigmaHQ/sigma
* In your own code with pySigma: https://pypi.org/project/pySigma
* Using SOC Prime online Sigma converter: https://uncoder.io/
* Using the SOC Prime free Kibana plugin: https://github.com/socprime/SigmaUI

## Extensions to the SigmaHQ specification

### Fields

These will appear in the rules' `custom_attributes` fields to be used in a Sigma backend compiler

- `logsource`
  - `schema`: the normalization schema to be applied to the log before detection rules are evaluated. eg [OCSF](https://ocsf.io)

- `risk`: a dict field intended for more expressive control over risk scoring and objects than high/medium/low allows. for instance `score` to indicate a numerical risk score for use in risk-based alerting

- `message`: a message to display to the analyst or user receiving an alert. May use `{{ }}` template delimiters to reference fields within the log event

### Tag Namespaces

- `detection`: A classification of the detection. For action routing. _eg_ `detection.risk` to apply a risk score  

## Taxonomy

Rules are found in the `rules` folder and generally follow [SigmaHQ filename conventions](https://github.com/SigmaHQ/sigma-specification/blob/main/sigmahq/Sigmahq_filename_rule.md)

Where a logsource may contain multiple vendor products, the filename pattern appends the product in the prefix. For example `aws_ec2_*`
