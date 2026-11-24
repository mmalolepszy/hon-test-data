# hon-test-data Collection
Collection of hOn appliance data for development and testing of [mmalolepszy/pyhon-revived](https://github.com/mmalolepszy/pyhon-revived) and [mmalolepszy/hon-revived](https://github.com/mmalolepszy/hon-revived).

## Contribute
Please add your appliances data to this repository. This helps us to develop new features and not to break compatibility in newer versions.   
The data is automatic anonymized (like serial number, mac address, specific dates, given names and any user specific entry).

### Home Assistant
1. Make sure you installed the [hon integration](https://github.com/mmalolepszy/hon-revived#readme).
2. Navigate to `Settings` -> `Devices & services` -> `Haier hOn Revived` -> _your device_.
3. The _Create Data Archive_ button is disabled by default, so it may not be visible. At the bottom of the _Diagnostic_ card, click _+2 disabled entities_. The button appears greyed out.

    <img src="assets/1-diagnostic-disabled-entities.jpg" alt="+2 disabled entities" width="360"> <img src="assets/2-disabled-entities-shown.jpg" alt="Disabled Create Data Archive button" width="360">

4. Click _Create Data Archive_, then the gear icon. Click _Enable_ next to "This entity is disabled." (On older Home Assistant versions, switch on _Enabled_ and click _Update_ instead.)

    <img src="assets/3-entity-dialog-gear-icon.jpg" alt="Gear icon in the entity dialog" width="440"> <img src="assets/4-entity-settings-enable.jpg" alt="Enable button in the entity settings" width="320">

5. Home Assistant reloads the integration, which can take up to 30 seconds. Then press the _Create Data Archive_ button.

    <img src="assets/5-create-data-archive-enabled.jpg" alt="Press Create Data Archive button" width="360">

6. Open the notifications and download the data archive.

    <img src="assets/6-notification-data-archive.jpg" alt="Download data archive" width="400">

7. Create a GitHub Issue to this repository and add this zip file.
    Alternatively create a pull request with unzipped data.

### pyhOn
1. [Fork](https://github.com/mmalolepszy/hon-test-data/fork) this repository
2. Clone your forked repository
    ```
    $ git clone https://github.com/YOUR-USERNAME/hon-test-data.git
    $ cd hon-test-data/
    ```
3. Make sure you installed [pyhon-revived](https://pypi.org/project/pyhon-revived/)
    ```commandline
    $ pip install pyhon-revived
    ```
4. Create a export of your data with pyhon  
    **Make sure you use the anonymous paramater to protect your personal data!**
    ```commandline
    $ pyhon export --anonymous test_data/
    User for hOn account: your.hon.login@gmail.com
    Password for hOn account: 
    Created test_data/wm_1569/commands.json
    Created test_data/wm_1569/attributes.json
    Created test_data/wm_1569/command_history.json
    Created test_data/wm_1569/statistics.json
    Created test_data/wm_1569/maintenance.json
    Created test_data/wm_1569/appliance_data.json
    Created test_data/wm_1569/favourites.json
    ```
5. Commit and push your data
    ```
    $ git add .
    $ git commit -m "Add appliance data"
    $ git push
    ```
6. Create a pull-request to this repository
