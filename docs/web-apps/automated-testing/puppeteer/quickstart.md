---
id: quickstart
title: Puppeteer Quickstart
sidebar_label: Quickstart
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';
import useBaseUrl from '@docusaurus/useBaseUrl';

Use `saucectl` — the Sauce Labs test orchestrator CLI — to run [Puppeteer](https://github.com/puppeteer) tests directly from your existing Puppeteer project.

- Don't have Puppeteer tests but want to try? The Puppeteer Demo Repo includes a sample project structure, working configuration file, and sample Puppeteer test so you can get up and running in less than 10 minutes!
- Already running Puppeteer? Let `saucectl` run your tests in Docker and then publish the results in your Sauce Labs account, where you can easily analyze 30 days worth of test results and data analytics.

## What You'll Need

- A Sauce Labs account ([Log in](https://accounts.saucelabs.com/am/XUI/#login/) or sign up for a [free trial license](https://saucelabs.com/sign-up))
- Your Sauce Labs [Username and Access Key](https://app.saucelabs.com/user-settings)
- [Node.js](https://nodejs.org/en/) to use the NPM package manager
- A [GitHub](https://github.com/signup?ref_cta=Sign+up&ref_loc=header+logged+out&ref_page=%2F&source=header-home) account
- [Git](https://git-scm.com/downloads)
- [Docker](https://docs.docker.com/get-docker/) For now, Puppeteer is only supported for local testing.

:::note
Ensure the [Docker daemon](https://docs.docker.com/config/daemon/) is running (e.g., `docker info` works in your terminal / command prompt)
:::

## Step 1: Install `saucectl`

```
npm install -g saucectl
```

## Step 2: Link Your Sauce Labs Account

`saucectl` requires access to a valid Sauce Labs account.

:::tip Use Environment Variables
`saucectl` detects your Sauce Labs credentials [environment variables](/basics/environment-variables) and prioritizes them over values in the `credentials.yml` file when both are present. **If you have set them, you may skip this step.** Not sure if you have them set? Run the following command to check:

```
echo $SAUCE_USERNAME
echo $SAUCE_ACCESS_KEY
```

If a value is returned for both variables, they are set.
:::

1. Run the `configure` command:

   ```
   saucectl configure
   ```

1. Enter your Sauce Labs Username and Access Key at the prompts.

## Step 3: Clone the Puppeteer Demo Project

<Tabs
defaultValue="https"
values={[
{label: 'HTTPS', value: 'https'},
{label: 'SSH', value: 'ssh'},
]}>

<TabItem value="https">

```
git clone https://github.com/saucelabs/saucectl-puppeteer-example.git
```

</TabItem>
<TabItem value="ssh">

```
git clone git@github.com:saucelabs/saucectl-puppeteer-example.git
```

</TabItem>
</Tabs>

## Step 4: Run Tests

Navigate to the root of the Puppeteer project you just cloned, then use the `run` command to execute the sample test included with the `saucectl` example.

```
cd saucectl-puppeteer-example
saucectl run
```

The console displays the executing tests, distinguishing which mode is running.

The results and test assets are available immediately following test completion in your [Sauce Labs account](https://app.saucelabs.com/dashboard/tests/vdc).
