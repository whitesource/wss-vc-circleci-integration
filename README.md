# wss-vc-circleci-integration
WhiteSource vulnerability checker integartion for circleci

## General Information
CircleCi is a continuous integration development practice that is used by software teams allowing them to build, test and deploy applications on multiple platforms in an easier and faster method.

## What is an Orb?
Orbs are CircleCI configuration packages that can be shared across projects. Orbs allow you to make a single bundle of jobs, commands, and executors.

## What is the WhiteSource Scanner Orb?
The WhiteSource Scanner Orb is a simple tool that extracts descriptive information from the open source libraries located on your file system and integrates them with WhiteSource.
By using WhiteSource Orb, you can automatically detect all open source components in your code, while running your build. You can configure real time alerts on security risks, policy pitfalls, and software bugs. The orb integrates fully into your build process,  regardless of your programming languages or development environments (see supported languages in this link). It works automatically, continuously, and silently in the background, checking the security, licensing, and quality of your open source components against WhiteSource’s constantly-updated deﬁnitive database of open source repositories.

## How to use the WhiteSource Orb?

### Prerequisites
Registered WhiteSource Account
CircleCI CLI is installed and deployed

### Deployment Process
In order to keep your API token secure, WhiteSource creates a ‘context’ in CircleCI. Contexts provide a mechanism for securing and sharing environment variables across projects. The environment variables are defined as name/value pairs and are injected at runtime.

From CircleCI UI, click on 'Settings' → 'Context', and create a new context.


Add a new variable for the WhiteSource API Token (You can find the API token on the ‘Integrate tab’).
Create a configuration file (the full parameter reference can be found here) with the required parameters for the scan, and set the Configuration file name (including the file path) as a value for the ‘config_file_path’ parameter.

You can now add a comma separated list of directories and/or files to scan.

Commit and push to view the scan results.
In order to view the status, go to the CircleCI GUI and click on ‘jobs’. Click on the relevant job and verify that a ‘success’ message is displayed.

| Parameter        | Description |Required  | Default Value | Type |
| ------------- |:--------------------------------------------------------------------------------------------------------|:-----|:-----|:-----|
| api_key   | Unique identifier of the organization. Can be retrieved from the admin page in your WhiteSource account. | Yes |No default value| String |
| Directory      | Comma separated list of directories and / or files to scan.     |   Yes | . | String |
| config_file_path | Configuration file name (including file path).     |   No | ./whitesource-fs-agent.config| String |

