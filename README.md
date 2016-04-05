# NRO Transfer Log Format

The NRO transfer log is a common format to publish IP address and Autonomous System transfers within RIRs and between RIRs. The format of this log accomodates the description of transfers by both an RIR and the aggregate of transfers from all RIRs by the NRO.

The serialization format of this log is JSON, and the JSON is formally defined using [JSON Content Rules](http://codalogic.github.io/jcr/).

## Specifiction

The formal specification can be found [here](https://github.com/nro-ecg/transfer_log/blob/master/transfer_log.jcr). A full example can be found [here](https://github.com/nro-ecg/transfer_log/blob/master/transfer_example.json).