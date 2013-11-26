# OpenShift Splunk Cartridge

The `splunk` cartridge provides a base install of the analytic tool Splunk. This cartridge has been created to 'embed' in an existing Application. If you have a larger amount of data that you do not need to retain for more than a month, then I would suggest you look at Splunk Storm. If you have a small amount of data (e.g. Quantified Self data), then this cartridge may be of interest to you.

## Limitations
There are a number of known limitations to running this Splunk cartridge on OpenShift.

1. The free tier only allows 1GB of storage, so you can't use this for massive amounts of log data.
2. OpenShift has a number of restrictions, including blocking direct access to gears. This means there is (to my knowledge) no way to push syslog data directly into Splunk. This doesn't mean you can't get log data in, you would just need to use something like FluenD, or the Syslog Universal Forwarder (untested - 26/11/2013).
3) The Python bindings have a bug (https://github.com/splunk/splunk-sdk-python/issues/65) that is relevant to running Splunk on OpenShift. A patch is on the way, but take note if you intent to connect this way.

## Installation
1. Create an Application based on existing web framework. If in doubt, just pick "Do-It-Yourself 0.1" or "Python 2.7"
2. Click on "Continue to the application overview page."
3. On the Application page, click on "Or, see the entire list of cartridges you can add".
4. Under "Install your own cartridge" enter the following URL: https://raw.github.com/kelvinn/openshift-splunk-cartridge/master/metadata/manifest.yml
5. Next and Add Cartrdige. Wait a few minutes for Splunk to download and install.
6. Logon to Splunk at: https://your-app.rhcloud.com/ui

## Cartridge Details

TODO