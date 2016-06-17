# metrics-boundary

Report dropwizard metrics to TrueSight pulse.

# Prerequisites

A TrueSight Pulse meter is expected to be running locally.

# Installation
## Maven

```xml

    <dependency>
        <groupId>com.boundary</groupId>
        <artifactId>dropwizard-boundary</artifactId>
        <version>0.8</version>
    </dependency>
```

# Usage
## configuration example

```yml
metrics:
  reporters:
    - type: boundary
      durationUnit: milliseconds
      rateUnit: seconds
      excludes:
        - "logback"
      includes:
        - "*.KafkaObservationSink\.metrics\.received"
        - "jvm.memory.heap.usage"
      useRegexFilters: true
      frequency: 1 second
      prefix: my_app_name
      extensions:
        - Count
        - Median
        - 1MinuteRate        
```
# Tests

To run the tests, clone the repo and run `mvn test` from the parent directory.

# LICENSE

&copy; Copyright 2015-2016 BMC SOFTWARE INC.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
