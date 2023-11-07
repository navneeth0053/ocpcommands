# ocpcommands
decode to base 64
oc get machineconfig 99-master-registries-config -o jsonpath='{.spec.config.storage.files[?(@.path=="/etc/containers/registries.conf.d/01-imagsearchregistries.conf")].contents.source}' | sed 's;data:text/plain;charset=utf-8;base64,;;' | base64 -d > current-01-imagsearchregistries.conf
encode command:
base64 -w0 current-01-imagsearchregistries.conf > new-01-imagsearchregistries.conf.b64



oc get machineconfig 99-master-registries-config -o jsonpath='{.spec.config.storage.files[?(@.path=="/etc/containers/registries.conf.d/01-imagsearchregistries.conf")].contents.source}'

