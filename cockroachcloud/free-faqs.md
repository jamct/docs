---
title: CockroachCloud Free (beta) FAQs
summary: Get answers to frequently asked questions about CockroachCloud Free (beta)
toc: true
---

This page answers the frequently asked questions about CockroachCloud Free (beta) and the paid version of CockroachCloud.

<div class="filters clearfix">
    <a href="free-faqs.html"><button class="filter-button page-level current">CockroachCloud Free (beta)</button></a>
    <a href="frequently-asked-questions.html"><button class="filter-button page-level">CockroachCloud</button></a>
</div>

## General

### What is CockroachCloud Free (beta)?

CockroachCloud Free (beta) delivers free CockroachDB clusters for you and your organization. It is a managed instance of CockroachDB that removes the friction of initial cluster sizing and auto-scales based on your application traffic.

### How do I start using CockroachCloud Free (beta)?

To get started with CockroachCloud Free (beta), <a href="https://cockroachlabs.cloud/signup?referralId=docs_free_faq" rel="noopener" target="_blank">sign up for a CockroachCloud account</a>, click **Create Cluster**, then click **Create your free cluster**. Your cluster will be ready in 20-30 seconds. For more information, see [**Quickstart**](quickstart.html).

### What are the usage limits of Cockroach Cloud Free (beta)?

There is an upper limit of usage of up to 1 vCPU and 5GB storage per free cluster. If you hit the storage limit, you will receive an email asking you to delete enough data to stay under the 5GB limit. If you do not respond within the next 30 days, you will be blocked from accessing your cluster.

### Do I have to pay for CockroachCloud Free (beta)?

No, you do not have to pay anything. CockroachCloud Free (beta) is free forever.

### What can I use CockroachCloud Free (beta) for?

CockroachCloud Free (beta) can be used for proofs-of-concept, toy programs, or to use while completing [Cockroach University](https://www.cockroachlabs.com/cockroach-university/).

For examples of applications that use CockroachCloud Free (beta), check out the following [Hack the North](https://hackthenorth.com/) projects:

- [flock](https://devpost.com/software/flock-figure-out-what-film-to-watch-with-friends)
- [mntr.tech](https://devpost.com/software/mntr-tech)
- [curbshop.online](https://devpost.com/software/curbshop-online)

### What are the limitations of CockroachCloud Free (beta)?

CockroachCloud Free is currently in beta and there are capabilities we are still working on enabling, such as no-downtime upgrades to a paid cluster. If you want to try out a paid cluster, you can get a [30-day trial of CockroachCloud](quickstart-trial-cluster.html).

### How do I connect to my cluster?

To connect to a cluster, download the CA certificate, and then generate a connection string or parameters. You can use this information to connect to your cluster through the CockroachDB SQL client or a Postgres-compatible driver or ORM. For more details, see [Connect to Your CockroachCloud Cluster](connect-to-your-cluster.html).

## Beta release

### Where can I submit feedback or bugs on the beta?

You can submit feedback or log any bugs you find through [this survey](https://forms.gle/jWNgmCFtF4y15ePw5).

## Security

### Is my cluster secure?

Yes, we use separate certificate authorities for each cluster, and all connections to the cluster over the internet use TLS 1.2.

### Is encryption-at-rest enabled on CockroachCloud Free (beta)?

Yes. All data on CockroachCloud is encrypted-at-rest using the tools provided by the cloud provider that your cluster is running in.

- Data stored in clusters running in GCP are encrypted-at-rest using [persistent disk encryption](https://cloud.google.com/compute/docs/disks#pd_encryption).
- Data stored in clusters running in AWS are encrypted-at-rest using [EBS encryption-at-rest](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html).

Because we are relying on the cloud provider's encryption implementation (as noted above), we do not enable CockroachDB's [internal implementation of encryption-at-rest](../{{site.versions["stable"]}}/encryption.html#encryption-at-rest-enterprise). This means that encryption will appear to be disabled in the [DB Console](../{{site.versions["stable"]}}/ui-overview.html), since it is unaware of cloud provider encryption.

### Is my cluster isolated? Does it share resources with any other clusters?

CockroachCloud Free (beta) is a multi-tenant offering and resources are shared between clusters.

## Cluster maintenance

### How do I add nodes?

You cannot add nodes to your CockroachCloud Free (beta) cluster, and there is an upper limit of usage of up to 1 vCPU and 5GB storage. If you exceed this limit or want a more powerful cluster, you can create a cluster using the paid version of [CockroachCloud](create-your-cluster.html).

### Can I upgrade my cluster from CockroachCloud Free (beta) to the paid version of CockroachCloud?

At this time, a CockroachCloud Free (beta) cluster cannot be upgraded. In the future, you will have the ability to move from CockroachCloud Free (beta) to a paid version of CockroachCloud.

## Product features

### Are partitioning or change data capture available to me?

No, change data capture and partitioning are not available on CockroachCloud Free (beta) clusters, but will be in the future.

### Do you have a UI? How can I see details?

Yes, you can view and your clusters in the [CockroachCloud Console](https://cockroachlabs.cloud/). However, [DB Console](../{{site.versions["stable"]}}/ui-overview.html) pages (e.g., **Statements** or **Database** pages) are not currently available for CockroachCloud Free (beta) clusters.

### Can I backup my CockroachCloud Free (beta) cluster? Does Cockroach Labs take backups of my cluster?

Cockroach Labs takes full cluster backups of all CockroachCloud Free (beta) clusters for our own purposes. Currently, these backups are not available to you. We support [`BACKUP`](../{{site.versions["stable"]}}/backup.html) and [`RESTORE`](../{{site.versions["stable"]}}/restore.html) of databases and tables on CockroachCloud Free (beta) clusters through [`userfile`](../{{site.versions["stable"]}}/use-userfile-for-bulk-operations.html) storage. For an example on using `userfile` for backups, see [Backup and restore with `userfile`](run-bulk-operations.html#backup-and-restore-with-userfile).
