---
title: Motor de reglas de notas de seguridad importante para la empresa | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- business rules, store administrator
- Business Rule Composer, security
- business rules, security
- Denial of Service attacks
ms.assetid: 8972127a-5569-4b32-bc09-e9265efe9514
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a90090c55dcbb0f8e55296d2711d5e4b36cd346
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="important-security-notes-for-the-business-rule-engine"></a>Notas de seguridad importante para el motor de reglas de negocios
En este tema se resume los problemas de seguridad conocidos en Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] y los pasos que debe seguir para mitigar los riesgos de seguridad.  
  
## <a name="malicious-schema-input-causing-denial-of-service-attack"></a>Entrada de esquema malintencionada que causa un ataque de denegación de servicio  
 Mientras se imponen hechos, cada regla se comprueba con respecto a todos los objetos que coinciden con los tipos admitidos de una directiva. Suponga que hay una regla en una directiva que utiliza uno de los elementos de un esquema pasado mediante un selector. Si la instancia de este elemento/atributo que coincide con el selector se repite miles de veces, cada una de esas instancias se impone, lo que causa una degradación en el rendimiento y, posiblemente, la posterior denegación de servicio.  
  
 Para mitigar este posible problema, necesita validar todas las entradas ambiguas que se pasan mientras se ejecuta una directiva.  
  
## <a name="ruleset-not-validating-objects-before-asserting-the-facts"></a>El conjunto de reglas no valida objetos antes de imponer los hechos  
 Cualquier instancia del esquema que se pasa como un hecho a la **RuleSet** no se valida con respecto al esquema antes de afirmar que cualquier regla que utilice selectores. Debe validar todas las entradas que se pasen mientras se ejecuta una directiva.  
  
## <a name="expected-behaviors-of-the-business-rule-composer-when-rulestore-security-is-on"></a>Comportamientos esperados del Compositor de reglas de negocio cuando está activa la seguridad de RuleStore  
 Puede habilitar la característica de seguridad basada en roles para el almacén de reglas mediante una llamada a la **EnableAuthorization** método de la **RuleStore** clase. Cuando está activa esta característica de seguridad, los comportamientos esperados del Compositor de reglas de negocio son como se indica a continuación:  
  
-   El modelo de objetos filtra conjuntos de reglas y vocabularios a los que el usuario no tiene acceso de lectura. Por lo tanto, no aparecen en el Compositor de reglas de negocio.  
  
-   Si el usuario no tiene acceso de escritura a una directiva o a un vocabulario, cualquier intento de guardar hace que se produzca una excepción.  
  
## <a name="user-types-for-rule-store-administrator"></a>Tipos de usuario para el administrador de almacén de reglas  
 El administrador de almacén de reglas cuenta con el privilegio de definir un grupo de autorización para artefactos guardados en el almacén de reglas. Sin embargo, observe las siguientes diferencias entre dos tipos de usuario a los que puede pertenecer el administrador de almacén de reglas:  
  
-   Cuando el administrador de almacén de reglas es un usuario de Windows, lo que quiere decir que se utiliza la autenticación de Windows para conectarse al almacén de reglas, el administrador de almacén de reglas puede definir un grupo de autorización cuyo usuario sea un grupo de Windows o un usuario de Windows.  
  
-   Cuando el administrador de almacén de reglas es un usuario de SQL, lo que quiere decir que se utiliza la autenticación de SQL para conectarse al almacén de reglas, el administrador de almacén de reglas no puede definir un grupo de autorización cuyo usuario sea un grupo de Windows, pero sí puede definir uno cuyo usuario sea un usuario de Windows.  
  
## <a name="user-cannot-associate-an-authorization-group-with-an-artifact-without-sufficient-rights"></a>El usuario no puede asociar un grupo de autorización con un artefacto sin tener los derechos suficientes  
 Un creador de artefactos que no es ni un usuario dbo de SQL ni un miembro de RE_ADMIN_USERS, y no cuenta con el permiso MODIFY_DELETE para un artefacto, no puede asociar un nuevo grupo de autorización con el artefacto. El siguiente escenario es un ejemplo de este comportamiento:  
  
1.  El creador del conjunto de reglas no es dbo, no pertenece al grupo RE_ADMIN_USERS y no cuenta con el permiso MODIFY_DELETE después de que se haya creado el conjunto de reglas.  
  
2.  El creador crea un conjunto de reglas.  
  
3.  El miembro del grupo RE_ADMIN_USERS crea la autorización AG1 y da permiso MODIFY_DELETE a User2.  
  
4.  El creador asocia AG1 con el conjunto de reglas.  
  
5.  Se activa la autorización de almacén de reglas.  
  
6.  El miembro del grupo RE_ADMIN_USERS crea la autorización AG2 y da permiso READ_EXECUTE a User2.  
  
7.  El creador asocia AG2 con el conjunto de reglas. Aunque el creador no tiene derechos suficientes para hacerlo, no aparece ningún mensaje de error.  
  
8.  Se produce un error en el intento de lectura del conjunto de reglas por parte de User2.