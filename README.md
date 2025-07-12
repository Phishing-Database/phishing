<img src="https://github.com/Phishing-Database/assets/raw/master/phishing-logo.jpg" alt="Phishing Domain Status Testing Repo"/>

# Phishing.Database: Phishing <!-- omit in toc -->

This is the central repository for adding or removing domains, links, and IPs from the [Phishing.Database](https://github.com/Phishing-Database) project.

Since pushing to the main repository is prohibited, this repository serves as an
area for anyone to submit changes to the Phishing Database.

> [!CAUTION]
> We are in the process of migrating this repository to a new structure. The files at the top-level directories will be removed in the future. Please use the new structure for contributions.

# Table of Contents <!-- omit in toc -->

- [Additions and False Positives](#additions-and-false-positives)
  - [Additions](#additions)
    - [Domains](#domains)
    - [Links](#links)
    - [IPs](#ips)
  - [False Positives](#false-positives)
    - [Domains](#domains-1)
    - [Links](#links-1)
    - [IPs](#ips-1)
- [Repository Operations](#repository-operations)


# Additions and False Positives

We now categorize contributions into two main directories:

- `additions/`: Contains files for adding phishing domains, links, and IPs.
- `falsepositives/`: Contains files for whitelisting false positives.

Within these directories, we categorize contributions further into 2 timeframes:

- `permanent/`: For contributions that are expected to remain valid indefinitely.
- `temporary/`: For contributions that are expected to be valid for a short period of time. Please be aware that the content of the files in this directory will be removed at the beginning of each month.

Within the above directories, you can find the files listed bellow.

## Additions

### Domains

| Filename                             | Description                                                                                    |
| ------------------------------------ | ---------------------------------------------------------------------------------------------- |
| `additions/**/domains.list`          | Container a list of domains to be added to the Phishing.Database.                              |
| `additions/**/domains.wildcard.list` | Contains a list of domains to be added and considered as wildcards - as we meet them overtime. |


### Links

| Filename                  | Description                                                           |
| ------------------------- | --------------------------------------------------------------------- |
| `additions/**/links.list` | Contains a list of links / URLs to be added to the Phishing.Database. |


### IPs

| Filename                          | Description                                                                                                   |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| `additions/**/ips.list`           | Contains a list of IPs to be added to the Phishing.Database.                                                  |
| `additions/**/ips.cidr.list`      | Contains a list of IPs to be added to the Phishing.Database in CIDR notation. _(cf: RFC-5737)_                |
| `additions/**/ips.arpa.list`      | Contains a list of IPs to be added to the Phishing.Database in ARPA/PTR format. _(cf: RFC-5737)_              |
| `additions/**/ips.cidr.arpa.list` | Contains a list of IPs to be added to the Phishing.Database in CIDR notation in ARPA format. _(cf: RFC-5737)_ |


## False Positives

> [!NOTE]
> The Phishing.Database project uses the [Givilsta](https://github.com/funilrys/givilsta) project to process any files in the `falsepositives/` directory against the main repository. Please keep that in mind when you are tented to add huge lists of domains, links, or IPs.

### Domains

| Filename                              | Description                                                                                                                                                         |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `falsepositives/**/domains.list`      | Contains a list of domains to be whitelisted as false positives. This is a 1:1 match.                                                                               |
| `falsepositives/**/domains.all.list`  | Contains a list of domains to be whitelisted as false positives. Any entry in this file will be prefixed with Givilsta's `ALL` flag _(cf: see Givilsta's readme)_.  |
| `falsepositives/**/domains.reg.list`  | Contains a list of domains to be whitelisted as false positives. Any entry in this file will be prefixed with Givilsta's `REG` flag _(cf: see Givilsta's readme)_.  |
| `falsepositives/**/domains.rzdb.list` | Contains a list of domains to be whitelisted as false positives. Any entry in this file will be prefixed with Givilsta's `RZDB` flag _(cf: see Givilsta's readme)_. |

### Links

| Filename                       | Description                                                                         |
| ------------------------------ | ----------------------------------------------------------------------------------- |
| `falsepositives/**/links.list` | Contains a list of links to be whitelisted as false positives. This is a 1:1 match. |

### IPs

| Filename                               | Description                                                                                                   |
| -------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| `falsepositives/**/ips.list`           | Contains a list of IPs to be whitelisted as false positives. This is a 1:1 match.                             |
| `falsepositives/**/ips.cidr.list`      | Contains a list of IPs to be whitelisted as false positives in CIDR notation. _(cf: RFC-5737)_                |
| `falsepositives/**/ips.arpa.list`      | Contains a list of IPs to be whitelisted as false positives in ARPA/PTR format. _(cf: RFC-5737)_              |
| `falsepositives/**/ips.cidr.arpa.list` | Contains a list of IPs to be whitelisted as false positives in CIDR notation in ARPA format. _(cf: RFC-5737)_ |


# Repository Operations

The state of the `master` branch will be automatically fetched every few hours and integrated into
the next update of the main repository. The latest state of the fetched data will
be reflected in the [frozen-dataset](https://github.com/Phishing-Database/frozen-datasets) repository.