# Jenkins Email Notification Pipeline

A minimal Jenkins pipeline that demonstrates sending automated email notifications after each build stage using the [Email Extension Plugin](https://plugins.jenkins.io/email-ext/).

## What it does

The pipeline runs two stages — **Test** and **Security Scan** — and after each one, regardless of pass/fail, it emails the build result along with the stage's log file as an attachment.

## Requirements

- Jenkins with the **Email Extension Plugin** installed and configured (SMTP server set up under *Manage Jenkins → Configure System*)
- A Windows Jenkins agent (the pipeline uses `bat` steps)

## Setup

1. Create a new Pipeline job in Jenkins.
2. Point it at this repository, or paste the contents of [`Jenkinsfile`](Jenkinsfile) into the pipeline script.
3. Update the `to:` address in each `emailext` block to the recipient you want notified.
4. Run the pipeline.

## Pipeline stages

| Stage | Purpose |
|---|---|
| Test | Runs the test step and emails `test.log` with the result |
| Security Scan | Runs the security scan step and emails `scan.log` with the result |

## License

MIT
