### Домашнее задание к занятию "08.02 Работа с Playbook"

## Переменные

### All:

java_jdk_version: 11.0.12
java_oracle_jdk_package: jdk-11.0.12_linux-x64_bin.tar.gz

### Elasticsearch:

elastic_version: "7.10.1"
elastic_home: "/opt/elastic/{{ elastic_version }}"

### Kibana:

kibana_version: "7.14.1"
kibana_home: "/opt/kibana/{{ kibana_version }}"

## Что делает Playbook

Устанавливает Java, Elastic и Kibana на выбранные хосты

## Команды

`ansible-lint -w site.yml`

`ansible-playbook site.yml -i inventory/prod.yml`

## Вывод

```
% ansible-playbook site.yml -i inventory/prod.yml

PLAY [Install Java] ********************************************************************************************************************************************************

TASK [Gathering Facts] *****************************************************************************************************************************************************
[DEPRECATION WARNING]: Distribution Ubuntu 18.04 on host ubuntu1 should use /usr/bin/python3, but is using /usr/bin/python for backward compatibility with prior Ansible
releases. A future Ansible release will default to using the discovered platform python for this host. See https://docs.ansible.com/ansible-
core/2.11/reference_appendices/interpreter_discovery.html for more information. This feature will be removed in version 2.12. Deprecation warnings can be disabled by
setting deprecation_warnings=False in ansible.cfg.
ok: [ubuntu1]
[DEPRECATION WARNING]: Distribution Ubuntu 18.04 on host ubuntu2 should use /usr/bin/python3, but is using /usr/bin/python for backward compatibility with prior Ansible
releases. A future Ansible release will default to using the discovered platform python for this host. See https://docs.ansible.com/ansible-
core/2.11/reference_appendices/interpreter_discovery.html for more information. This feature will be removed in version 2.12. Deprecation warnings can be disabled by
setting deprecation_warnings=False in ansible.cfg.
ok: [ubuntu2]

TASK [Set facts for Java 11 vars] ******************************************************************************************************************************************
ok: [ubuntu1]
ok: [ubuntu2]

TASK [Upload .tar.gz file containing binaries from local storage] **********************************************************************************************************
ok: [ubuntu2]
ok: [ubuntu1]

TASK [Ensure installation dir exists] **************************************************************************************************************************************
ok: [ubuntu2]
ok: [ubuntu1]

TASK [Extract java in the installation directory] **************************************************************************************************************************
skipping: [ubuntu2]
skipping: [ubuntu1]

TASK [Export environment variables] ****************************************************************************************************************************************
changed: [ubuntu2]
changed: [ubuntu1]

PLAY [Install Elasticsearch] ***********************************************************************************************************************************************

TASK [Gathering Facts] *****************************************************************************************************************************************************
ok: [ubuntu1]

TASK [Upload tar.gz Elasticsearch from remote URL] *************************************************************************************************************************
changed: [ubuntu1]

TASK [Create directrory for Elasticsearch] *********************************************************************************************************************************
changed: [ubuntu1]

TASK [Extract Elasticsearch in the installation directory] *****************************************************************************************************************
changed: [ubuntu1]

TASK [Set environment Elastic] *********************************************************************************************************************************************
changed: [ubuntu1]

PLAY [Install Kibana] ******************************************************************************************************************************************************

TASK [Gathering Facts] *****************************************************************************************************************************************************
ok: [ubuntu2]

TASK [Upload tar.gz Kibana from remote URL] ********************************************************************************************************************************
changed: [ubuntu2]

TASK [Create directrory for Kibana] ****************************************************************************************************************************************
changed: [ubuntu2]

TASK [Extract Kibana in the installation directory] ************************************************************************************************************************
changed: [ubuntu2]

TASK [Set environment kibana] **********************************************************************************************************************************************
changed: [ubuntu2]

PLAY RECAP *****************************************************************************************************************************************************************
ubuntu1                    : ok=10   changed=5    unreachable=0    failed=0    skipped=1    rescued=0    ignored=0
ubuntu2                    : ok=10   changed=5    unreachable=0    failed=0    skipped=1    rescued=0    ignored=0

```
