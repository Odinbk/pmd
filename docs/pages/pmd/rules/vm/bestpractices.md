---
title: Best Practices
summary: Rules which enforce generally accepted best practices.
permalink: pmd_rules_vm_bestpractices.html
folder: pmd/rules/vm
sidebaractiveurl: /pmd_rules_vm.html
editmepath: ../pmd-vm/src/main/resources/category/vm/bestpractices.xml
keywords: Best Practices, AvoidReassigningParameters, UnusedMacroParameter
language: VM
---
## AvoidReassigningParameters

**Since:** PMD 5.1

**Priority:** Medium High (2)

Reassigning values to incoming parameters is not recommended.  Use temporary local variables instead.

**This rule is defined by the following Java class:** [net.sourceforge.pmd.lang.vm.rule.bestpractices.AvoidReassigningParametersRule](https://github.com/pmd/pmd/blob/master/pmd-vm/src/main/java/net/sourceforge/pmd/lang/vm/rule/bestpractices/AvoidReassigningParametersRule.java)

**Use this rule by referencing it:**
``` xml
<rule ref="category/vm/bestpractices.xml/AvoidReassigningParameters" />
```

## UnusedMacroParameter

**Since:** PMD 5.1

**Priority:** Medium High (2)

Avoid unused macro parameters. They should be deleted.

**This rule is defined by the following Java class:** [net.sourceforge.pmd.lang.vm.rule.bestpractices.UnusedMacroParameterRule](https://github.com/pmd/pmd/blob/master/pmd-vm/src/main/java/net/sourceforge/pmd/lang/vm/rule/bestpractices/UnusedMacroParameterRule.java)

**Use this rule by referencing it:**
``` xml
<rule ref="category/vm/bestpractices.xml/UnusedMacroParameter" />
```

