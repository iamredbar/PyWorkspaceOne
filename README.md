# PyWorkspaceOneUEM

=========

PyWorkspaceOneUEM is a Python API library for [VMware Workspace ONE UEM](https://www.vmware.com/content/vmware/vmware-published-sites/us/products/workspace-one.html.html) formerly known as [AirWatch](https://www.air-watch.com/)

## Credit

A huge credit goes to John Richrads [@jprichards](https://github.com/jprichards) and his project [PyVMwareAirWatch](https://github.com/jprichards/PyVMwareAirWatch) from which a majority of the codebase was adopted.

## Usage

example.py

```python
from pyws1uem.client import WorkspaceOneAPI

a = WorkspaceOneAPI(env='your_environment_url',
                    apikey='your_api_token_key',
                    username='username',
                    password='password')


# Get the OG ID for a specified Group ID
a.groups.get_id_from_groupid(groupid='testog')

# Create a Child OG for a specified Parent OG Group ID (Type/Name optional)
a.groups.create_child_og(parent_groupid='testog', groupid='newog', og_type='Container', name='newog')

# Get the Smart Group ID for a specified OG ID and Smart Group Name
a.smartgroups.get_id_from_og_id(og_id=7, sg_name='apitest')

# Get a Device ID via an alternate device identifier
a.devices.get_id_by_alt_id(serialnumber='C09Z1TC8FJWT')
```

## Supported Functionality

* Devices
  * Get Device Details by Alt ID (Macaddress, Udid, Serialnumber, ImeiNumber, EasId)
  * Get Device ID by Alt ID (Macaddress, Udid, Serialnumber, ImeiNumber, EasId)
  * Clear Device Passcode
  * Send Commands To devices via Device ID or by Alt ID
  * Get Device FileVualt Recover Key
  * Get Security Info Sample by Device ID or Alt ID
  * GET Bulk Security Info Sample
  * Switch device From Staging User to End User
  * Get Network info Sample by Device ID
* Users
  * Search for users by Username, Firstname, Lastname, Email,
  OrganizationGroupID, or Role
  * Delete user
* Groups
  * Get OG ID from Group ID
  * Create Customer type OG (On-Prem only)
  * Create Child OG
  * Get UUID from OG ID
* Smart Groups
  * Get SG ID by Name and OG ID
  * Get SG Details
  * Get Devices that are included in SG
  * Add Device to SG Device Additions
* Info
  * Get Environment Information

## Requirements

* [requests](http://docs.python-requests.org/en/latest/)
