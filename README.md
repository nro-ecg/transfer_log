# NRO Transfer Log Format

The NRO transfer log is a common format to publish IP address and Autonomous System transfers within RIRs and between RIRs. The format of this log accomodates the description of transfers by both an RIR and the aggregate of transfers from all RIRs by the NRO.

The serialization format of this log is JSON, and the JSON is formally defined using [JSON Content Rules](http://codalogic.github.io/jcr/).

## JSON Specifiction

The formal JSON specification can be found [here](https://github.com/nro-ecg/transfer_log/blob/master/transfer_log.jcr). A full example can be found [here](https://github.com/nro-ecg/transfer_log/blob/master/transfer_example.json).

## File Naming Conventions and Processes

Each RIR will publish the transfer log on their FTP server (it should be noted, that each RIR makes the contents of their FTP server available via HTTP as well). Each RIR will create a `/pub/stats/RIR/transfers` directory, where "RIR" is the name of the RIR (e.g. APNIC, LACNIC, etc).

Within that directory there will be a file called `transfers_latest.json`. This file will be the cummulative transfer log and is expected grow over time.

Each RIR will also create archive directories based on the year in the `YYYY` format. The contents of the archive directories will contain snapshots of the `transfers_latest.json` file. Each snapshot file is to have a file name in the form of `transfers_`, followed by a UTC date/time stamp, followed by the `.json` file extension.

The format for the date/time stamp is to follow the [RFC 3339](https://www.ietf.org/rfc/rfc3339.txt) format but with the colon characters removed from the time portion for filename portability. This data/time stamp is to be specified as a UTC offset (using the 'Z' character).

The following is an example of the directory.

```
pub/
  stats/
    /<rir>
      transfers/
        transfers_latest.json
        2017/
          transfers_20170322T060000Z.json
          transfers_20170321T060000Z.json
          ...
        2016/
          transfers_20160322T060000Z.json
          transfers_20160321T060000Z.json
          ...
```
