# sap_hana_bone_prepare Ansible Role

Prepare the server for the installation to all required SAP components:

- Installs the required packages needed by ansible SAP HANA and SAP Business One
- Creates some required files and directories
- Generates the SAP Business One parameters file

## Role Variables
### sap_bone_install_software_directory
- _Type:_ `string`
- _Default value:_ `/software/bone`

Directory where the SAP Business One software is located

### sap_bone_install_selected_features
- _Type:_ `string`
- _Default value:_ `B1ServerToolsSLD,B1ServerToolsExtensionManager,B1ServerToolsLicense,B1ServerToolsJobService,B1ServerToolsMobileService,B1ServerToolsXApp,B1SLDAgent,B1WebClient,B1BackupService,B1ServerSHR,B1ServerCommonDB,B1ServerHelp_EN,B1ServerAddons,B1ServerOI,B1AnalyticsOlap,B1AnalyticsTomcatEntSearch,B1AnalyticsTomcatDashboard,B1AnalyticsTomcatReplication,B1AnalyticsTomcatConfiguration,B1AnalyticsTomcatPredictiveAnalysis,B1ServiceLayerComponent,B1ElectronicDocumentService,B1APIGatewayService`

Comma separated list of Business One features to install

### hostname
- _Type:_ `string`
- _Default value:_ "{{ ansible_facts.fqdn }}"

### sap_hana_install_common_master_password
- _Type:_ `string`

### sap_hana_install_sid
- _Type:_ `string`

### sap_hana_install_instance_nr
- _Type:_ `string`

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - sap_hana_bone_prepare
    - vars:
         sap_bone_install_software_directory: /software/sap/bone
        sap_hana_install_common_master_password: 'NewPass$321'
        sap_hana_install_sid: 'H01'
        sap_hana_install_instance_nr: '00'


License
-------



Author Information
------------------

Peter Varkoly <varkoly@suse.com>
