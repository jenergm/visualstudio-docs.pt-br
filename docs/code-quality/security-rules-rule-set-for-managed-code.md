---
title: Conjunto de regras de segurança para código gerenciado
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 564aeac6-03fa-41b0-b655-88179f0ab01b
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 45c51a6c5496686ef84b17341c97f00680a80bdd
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59366036"
---
# <a name="security-rules-rule-set-for-managed-code"></a>Conjunto de regras de segurança para código gerenciado
Você deve incluir as regras de segurança da Microsoft conjunto de regras para maximizar o número de possíveis problemas de segurança que são relatados.

|Regra|Descrição|
|----------|-----------------|
|[CA2100](../code-quality/ca2100-review-sql-queries-for-security-vulnerabilities.md)|Examinar consultas SQL em busca de vulnerabilidades de segurança|
|[CA2102](../code-quality/ca2102-catch-non-clscompliant-exceptions-in-general-handlers.md)|Capturar exceções não CLSCompliant em manipuladores gerais|
|[CA2103](../code-quality/ca2103-review-imperative-security.md)|Examinar a segurança imperativa|
|[CA2104](../code-quality/ca2104-do-not-declare-read-only-mutable-reference-types.md)|Não declarar tipos de referência mutáveis somente leitura|
|[CA2105](../code-quality/ca2105-array-fields-should-not-be-read-only.md)|Campos de matrizes não devem ser somente leitura|
|[CA2106](../code-quality/ca2106-secure-asserts.md)|Declarações seguras|
|[CA2107](../code-quality/ca2107-review-deny-and-permit-only-usage.md)|Examinar uso de deny e permit only|
|[CA2108](../code-quality/ca2108-review-declarative-security-on-value-types.md)|Examinar a segurança declarativa em tipos de valor|
|[CA2109](../code-quality/ca2109-review-visible-event-handlers.md)|Examinar manipuladores de eventos visíveis|
|[CA2111](../code-quality/ca2111-pointers-should-not-be-visible.md)|Ponteiros não devem ser visíveis|
|[CA2112](../code-quality/ca2112-secured-types-should-not-expose-fields.md)|Tipos protegidos não devem expor campos|
|[CA2114](../code-quality/ca2114-method-security-should-be-a-superset-of-type.md)|A segurança do método deve ser um superconjunto do tipo|
|[CA2115](../code-quality/ca2115-call-gc-keepalive-when-using-native-resources.md)|Chamar GC.KeepAlive ao usar recursos nativos|
|[CA2116](../code-quality/ca2116-aptca-methods-should-only-call-aptca-methods.md)|Métodos APTCA devem chamar somente métodos APTCA|
|[CA2117](../code-quality/ca2117-aptca-types-should-only-extend-aptca-base-types.md)|Tipos APTCA devem estender somente tipos base APTCA|
|[CA2118](../code-quality/ca2118-review-suppressunmanagedcodesecurityattribute-usage.md)|Examinar o uso de SuppressUnmanagedCodeSecurityAttribute|
|[CA2119](../code-quality/ca2119-seal-methods-that-satisfy-private-interfaces.md)|Selar métodos que atendem a interfaces particulares|
|[CA2120](../code-quality/ca2120-secure-serialization-constructors.md)|Construtores de serialização seguros|
|[CA2121](../code-quality/ca2121-static-constructors-should-be-private.md)|Construtores estáticos devem ser particulares|
|[CA2122](../code-quality/ca2122-do-not-indirectly-expose-methods-with-link-demands.md)|Não expor indiretamente métodos com demandas de link|
|[CA2123](../code-quality/ca2123-override-link-demands-should-be-identical-to-base.md)|As demandas de link de substituição devem ser idênticas à base|
|[CA2124](../code-quality/ca2124-wrap-vulnerable-finally-clauses-in-outer-try.md)|Encapsular cláusulas finally vulneráveis em try externo|
|[CA2126](../code-quality/ca2126-type-link-demands-require-inheritance-demands.md)|As demandas de link de tipo exigem demandas de herança|
|[CA2130](../code-quality/ca2130-security-critical-constants-should-be-transparent.md)|Constantes críticas de segurança devem ser transparentes|
|[CA2131](../code-quality/ca2131-security-critical-types-may-not-participate-in-type-equivalence.md)|Tipos críticos de segurança podem não participar da equivalência de tipo|
|[CA2132](../code-quality/ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors.md)|Construtores padrão devem ser pelo menos tão críticos quanto construtores padrão do tipo base|
|[CA2133](../code-quality/ca2133-delegates-must-bind-to-methods-with-consistent-transparency.md)|Representantes devem ser associados a métodos com transparência consistente|
|[CA2134](../code-quality/ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods.md)|Os métodos devem manter uma transparência consistente durante a substituição dos métodos base|
|[CA2135](../code-quality/ca2135-level-2-assemblies-should-not-contain-linkdemands.md)|Os assemblies de nível 2 não devem conter LinkDemands|
|[CA2136](../code-quality/ca2136-members-should-not-have-conflicting-transparency-annotations.md)|Membros não devem ter anotações de transparência conflitantes|
|[CA2137](../code-quality/ca2137-transparent-methods-must-contain-only-verifiable-il.md)|Métodos transparentes devem conter apenas a IL verificável|
|[CA2138](../code-quality/ca2138-transparent-methods-must-not-call-methods-with-the-suppressunmanagedcodesecurity-attribute.md)|Métodos transparentes não devem chamar métodos com o atributo SuppressUnmanagedCodeSecurity|
|[CA2139](../code-quality/ca2139-transparent-methods-may-not-use-the-handleprocesscorruptingexceptions-attribute.md)|Métodos transparentes podem não usar o atributo HandleProcessCorruptingExceptions|
|[CA2140](../code-quality/ca2140-transparent-code-must-not-reference-security-critical-items.md)|O código transparente não deve referenciar itens críticos de segurança|
|[CA2141](../code-quality/ca2141-transparent-methods-must-not-satisfy-linkdemands.md)|Métodos transparentes não devem atender a LinkDemands|
|[CA2142](../code-quality/ca2142-transparent-code-should-not-be-protected-with-linkdemands.md)|O código transparente não deve ser protegido com LinkDemands|
|[CA2143](../code-quality/ca2143-transparent-methods-should-not-use-security-demands.md)|Métodos transparentes não devem usar demandas de segurança|
|[CA2144](../code-quality/ca2144-transparent-code-should-not-load-assemblies-from-byte-arrays.md)|O código transparente não deve carregar assemblies de matrizes de bytes|
|[CA2145](../code-quality/ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute.md)|Métodos transparentes não devem ser decorados com o SuppressUnmanagedCodeSecurityAttribute|
|[CA2146](../code-quality/ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces.md)|Os tipos devem ser pelo menos tão críticos quanto seus tipos base e interfaces|
|[CA2147](../code-quality/ca2147-transparent-methods-may-not-use-security-asserts.md)|Métodos transparentes podem não usar declarações de segurança|
|[CA2149](../code-quality/ca2149-transparent-methods-must-not-call-into-native-code.md)|Métodos transparentes não devem chamar código nativo|
|[CA2210](../code-quality/ca2210-assemblies-should-have-valid-strong-names.md)|Assemblies devem ter nomes fortes válidos|
|[CA2300](ca2300-do-not-use-insecure-deserializer-binaryformatter.md)|Não usar o desserializador BinaryFormatter não seguro|
|[CA2301](ca2301-do-not-call-binaryformatter-deserialize-without-first-setting-binaryformatter-binder.md)|Não chamar BinaryFormatter.Deserialize sem antes definir BinaryFormatter.Binder|
|[CA2302](ca2302-ensure-binaryformatter-binder-is-set-before-calling-binaryformatter-deserialize.md)|Verificar se o BinaryFormatter.Binder está definido antes de chamar BinaryFormatter.Deserialize|
|[CA3001](../code-quality/ca3001-review-code-for-sql-injection-vulnerabilities.md)|Examinar código quanto a vulnerabilidades de injeção de SQL|
|[CA3002](../code-quality/ca3002-review-code-for-xss-vulnerabilities.md)|Examinar código quanto a vulnerabilidades de XSS|
|[CA3003](../code-quality/ca3003-review-code-for-file-path-injection-vulnerabilities.md)|Examinar código quanto a vulnerabilidades de injeção de caminho|
|[CA3004](../code-quality/ca3004-review-code-for-information-disclosure-vulnerabilities.md)|Examinar código quanto a vulnerabilidades de divulgação de informações|
|[CA3005](../code-quality/ca3005-review-code-for-ldap-injection-vulnerabilities.md)|Examinar código quanto a vulnerabilidades de injeção de LDAP|
|[CA3006](../code-quality/ca3006-review-code-for-process-command-injection-vulnerabilities.md)|Examinar código quanto a vulnerabilidades de injeção de comando de processo|
|[CA3007](../code-quality/ca3007-review-code-for-open-redirect-vulnerabilities.md)|Examinar código quanto a vulnerabilidades de redirecionamento aberto|
|[CA3008](../code-quality/ca3008-review-code-for-xpath-injection-vulnerabilities.md)|Examinar código quanto a vulnerabilidades de injeção de XPath|
|[CA3009](../code-quality/ca3009-review-code-for-xml-injection-vulnerabilities.md)|Examinar código quanto a vulnerabilidades de injeção de XML|
|[CA3010](../code-quality/ca3010-review-code-for-xaml-injection-vulnerabilities.md)|Examinar código quanto a vulnerabilidades de injeção de XAML|
|[CA3011](../code-quality/ca3011-review-code-for-dll-injection-vulnerabilities.md)|Examinar código quanto a vulnerabilidades de injeção de DLL|
|[CA3012](../code-quality/ca3012-review-code-for-regex-injection-vulnerabilities.md)|Examinar código quanto a vulnerabilidades de injeção de regex|
