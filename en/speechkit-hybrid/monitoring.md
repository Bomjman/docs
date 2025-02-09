# Monitoring {{ sk-hybrid-name }}

{{ sk-hybrid-name }} collects and stores metrics in [Prometheus](https://prometheus.io/) format. {{ sk-hybrid-name }} metrics are available at the following URL: `<IP address>:17002/metrics/prometheus`, where `<IP address>` is the {{ sk-hybrid-name }} IP address on your network.

## Common {{ sk-hybrid-name }} metrics {#metrics}

The metrics collected are either for speech synthesis or speech recognition. The `TYPE grpc_code_*` metric with gRPC response codes is common to all the services. For details, see the [gRPC documentation](https://grpc.github.io/grpc/core/md_doc_statuscodes.html).

## Speech synthesis metrics {#tts-metrics}

* `synthesis_sps`: Number of seconds of synthesized text generated in a second at runtime.
* `synthesis_latency`: Response time distribution [histogram](https://prometheus.io/docs/practices/histograms/) in milliseconds.

## Speech recognition metrics {#stt-metrics}

* `in_flight_requests`: Number of active sessions.
* `recognize_sps`: Number of seconds of recognized speech processed in a second at runtime.
* `recognize_rtf`: [Real Time Factor](https://devopedia.org/speech-recognition) distribution histogram. Describes the ratio of the time it takes to recognize a section of text to the length of the text itself expressed as a percentage. A value greater than 100 means that a server cannot cope with the stream of requests.