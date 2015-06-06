This is a fork of https://github.com/Bigel0w/fluent-plugin-snmptrap

# Differences

1. Commented out the [m.join](../master/lib/fluent/plugin/in_snmptrap.rb#L27)
 1. since on RHEL 6.6, the [join method](http://www.rubydoc.info/github/hallidave/ruby-snmp/SNMP/TrapListener#join-instance_method) seems to hang
     1. The user visible symptom is that ```service td-agent stop``` takes forever
     1. Although ```service td-agent start``` appears to complete without any indication of unusualness
1. Change the ```m``` to an instance variable
 1. since otherwise it would cause ```undefined local variable or method `m'``` in ```shutdown```
1. Warning: The above changes have been made by someone who has no Ruby / Fluentd background
