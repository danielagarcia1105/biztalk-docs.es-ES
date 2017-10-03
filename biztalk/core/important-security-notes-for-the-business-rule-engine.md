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
# <a name="important-security-notes-for-the-business-rule-engine"></a><span data-ttu-id="8d751-102">Notas de seguridad importante para el motor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="8d751-102">Important Security Notes for the Business Rule Engine</span></span>
<span data-ttu-id="8d751-103">En este tema se resume los problemas de seguridad conocidos en Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] y los pasos que debe seguir para mitigar los riesgos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8d751-103">This topic summarizes known security issues in Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] and the steps you must take to mitigate the security risks.</span></span>  
  
## <a name="malicious-schema-input-causing-denial-of-service-attack"></a><span data-ttu-id="8d751-104">Entrada de esquema malintencionada que causa un ataque de denegación de servicio</span><span class="sxs-lookup"><span data-stu-id="8d751-104">Malicious schema input causing Denial of Service attack</span></span>  
 <span data-ttu-id="8d751-105">Mientras se imponen hechos, cada regla se comprueba con respecto a todos los objetos que coinciden con los tipos admitidos de una directiva.</span><span class="sxs-lookup"><span data-stu-id="8d751-105">While asserting facts, each rule is verified against every object that matches the supported types within a policy.</span></span> <span data-ttu-id="8d751-106">Suponga que hay una regla en una directiva que utiliza uno de los elementos de un esquema pasado mediante un selector.</span><span class="sxs-lookup"><span data-stu-id="8d751-106">Suppose there is a rule in a policy that uses one of the elements in a schema passed by using a selector.</span></span> <span data-ttu-id="8d751-107">Si la instancia de este elemento/atributo que coincide con el selector se repite miles de veces, cada una de esas instancias se impone, lo que causa una degradación en el rendimiento y, posiblemente, la posterior denegación de servicio.</span><span class="sxs-lookup"><span data-stu-id="8d751-107">Now if the instance if this element/attribute that matches the selector is repeated thousands of times, every such instance is asserted, causing performance degradation and subsequent possible Denial of Service (DoS).</span></span>  
  
 <span data-ttu-id="8d751-108">Para mitigar este posible problema, necesita validar todas las entradas ambiguas que se pasan mientras se ejecuta una directiva.</span><span class="sxs-lookup"><span data-stu-id="8d751-108">To mitigate this potential issue, you need to validate all ambiguous input that is passed while executing a policy.</span></span>  
  
## <a name="ruleset-not-validating-objects-before-asserting-the-facts"></a><span data-ttu-id="8d751-109">El conjunto de reglas no valida objetos antes de imponer los hechos</span><span class="sxs-lookup"><span data-stu-id="8d751-109">RuleSet not validating objects before asserting the facts</span></span>  
 <span data-ttu-id="8d751-110">Cualquier instancia del esquema que se pasa como un hecho a la **RuleSet** no se valida con respecto al esquema antes de afirmar que cualquier regla que utilice selectores.</span><span class="sxs-lookup"><span data-stu-id="8d751-110">Any schema instance passed as a fact to the **RuleSet** is not validated against the schema before asserting any rules using selectors.</span></span> <span data-ttu-id="8d751-111">Debe validar todas las entradas que se pasen mientras se ejecuta una directiva.</span><span class="sxs-lookup"><span data-stu-id="8d751-111">You should validate all input that is passed while executing a policy.</span></span>  
  
## <a name="expected-behaviors-of-the-business-rule-composer-when-rulestore-security-is-on"></a><span data-ttu-id="8d751-112">Comportamientos esperados del Compositor de reglas de negocio cuando está activa la seguridad de RuleStore</span><span class="sxs-lookup"><span data-stu-id="8d751-112">Expected behaviors of the Business Rule Composer when RuleStore security is on</span></span>  
 <span data-ttu-id="8d751-113">Puede habilitar la característica de seguridad basada en roles para el almacén de reglas mediante una llamada a la **EnableAuthorization** método de la **RuleStore** clase.</span><span class="sxs-lookup"><span data-stu-id="8d751-113">You can enable the role-based security feature for the rule store by calling the **EnableAuthorization** method of the **RuleStore** class.</span></span> <span data-ttu-id="8d751-114">Cuando está activa esta característica de seguridad, los comportamientos esperados del Compositor de reglas de negocio son como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="8d751-114">When this security feature is enabled, the expected behaviors in the Business Rule Composer are as follows:</span></span>  
  
-   <span data-ttu-id="8d751-115">El modelo de objetos filtra conjuntos de reglas y vocabularios a los que el usuario no tiene acceso de lectura.</span><span class="sxs-lookup"><span data-stu-id="8d751-115">The object model filters out rule sets and vocabularies to which the user does not have read access.</span></span> <span data-ttu-id="8d751-116">Por lo tanto, no aparecen en el Compositor de reglas de negocio.</span><span class="sxs-lookup"><span data-stu-id="8d751-116">Therefore, they do not appear in the Business Rule Composer.</span></span>  
  
-   <span data-ttu-id="8d751-117">Si el usuario no tiene acceso de escritura a una directiva o a un vocabulario, cualquier intento de guardar hace que se produzca una excepción.</span><span class="sxs-lookup"><span data-stu-id="8d751-117">If the user does not have write access to a policy or a vocabulary, any save attempt causes an exception to be thrown.</span></span>  
  
## <a name="user-types-for-rule-store-administrator"></a><span data-ttu-id="8d751-118">Tipos de usuario para el administrador de almacén de reglas</span><span class="sxs-lookup"><span data-stu-id="8d751-118">User types for rule store administrator</span></span>  
 <span data-ttu-id="8d751-119">El administrador de almacén de reglas cuenta con el privilegio de definir un grupo de autorización para artefactos guardados en el almacén de reglas.</span><span class="sxs-lookup"><span data-stu-id="8d751-119">The rule store administrator has the privilege to define an authorization group for artifacts saved in the rule store.</span></span> <span data-ttu-id="8d751-120">Sin embargo, observe las siguientes diferencias entre dos tipos de usuario a los que puede pertenecer el administrador de almacén de reglas:</span><span class="sxs-lookup"><span data-stu-id="8d751-120">However, note the following differences between two types of user to which the rule store administrator can belong:</span></span>  
  
-   <span data-ttu-id="8d751-121">Cuando el administrador de almacén de reglas es un usuario de Windows, lo que quiere decir que se utiliza la autenticación de Windows para conectarse al almacén de reglas, el administrador de almacén de reglas puede definir un grupo de autorización cuyo usuario sea un grupo de Windows o un usuario de Windows.</span><span class="sxs-lookup"><span data-stu-id="8d751-121">When the rule store administrator is a Windows user, which means using Windows authentication to connect the rule store, the rule store administrator can define an authorization group whose user is a Windows group or a Windows user.</span></span>  
  
-   <span data-ttu-id="8d751-122">Cuando el administrador de almacén de reglas es un usuario de SQL, lo que quiere decir que se utiliza la autenticación de SQL para conectarse al almacén de reglas, el administrador de almacén de reglas no puede definir un grupo de autorización cuyo usuario sea un grupo de Windows, pero sí puede definir uno cuyo usuario sea un usuario de Windows.</span><span class="sxs-lookup"><span data-stu-id="8d751-122">When the rule store administrator is a SQL user, which means using SQL authentication to connect the rule store, the rule store administrator cannot define an authorization group whose user is a Windows group, but can define an authorization group whose user is a Windows user.</span></span>  
  
## <a name="user-cannot-associate-an-authorization-group-with-an-artifact-without-sufficient-rights"></a><span data-ttu-id="8d751-123">El usuario no puede asociar un grupo de autorización con un artefacto sin tener los derechos suficientes</span><span class="sxs-lookup"><span data-stu-id="8d751-123">User cannot associate an authorization group with an artifact without sufficient rights</span></span>  
 <span data-ttu-id="8d751-124">Un creador de artefactos que no es ni un usuario dbo de SQL ni un miembro de RE_ADMIN_USERS, y no cuenta con el permiso MODIFY_DELETE para un artefacto, no puede asociar un nuevo grupo de autorización con el artefacto.</span><span class="sxs-lookup"><span data-stu-id="8d751-124">An artifact creator that is neither a SQL dbo user nor a member of RE_ADMIN_USERS, and does not have MODIFY_DELETE permission to an artifact, cannot associate a new authorization group with the artifact.</span></span> <span data-ttu-id="8d751-125">El siguiente escenario es un ejemplo de este comportamiento:</span><span class="sxs-lookup"><span data-stu-id="8d751-125">The following scenario is an example of this behavior:</span></span>  
  
1.  <span data-ttu-id="8d751-126">El creador del conjunto de reglas no es dbo, no pertenece al grupo RE_ADMIN_USERS y no cuenta con el permiso MODIFY_DELETE después de que se haya creado el conjunto de reglas.</span><span class="sxs-lookup"><span data-stu-id="8d751-126">Rule set creator is not dbo, is not in the RE_ADMIN_USERS group, and does not have MODIFY_DELETE permission after the rule set is created.</span></span>  
  
2.  <span data-ttu-id="8d751-127">El creador crea un conjunto de reglas.</span><span class="sxs-lookup"><span data-stu-id="8d751-127">Creator creates a rule set.</span></span>  
  
3.  <span data-ttu-id="8d751-128">El miembro del grupo RE_ADMIN_USERS crea la autorización AG1 y da permiso MODIFY_DELETE a User2.</span><span class="sxs-lookup"><span data-stu-id="8d751-128">Member of the RE_ADMIN_USERS group creates authorization AG1 with MODIFY_DELETE permission to User2.</span></span>  
  
4.  <span data-ttu-id="8d751-129">El creador asocia AG1 con el conjunto de reglas.</span><span class="sxs-lookup"><span data-stu-id="8d751-129">Creator associates AG1 with the rule set.</span></span>  
  
5.  <span data-ttu-id="8d751-130">Se activa la autorización de almacén de reglas.</span><span class="sxs-lookup"><span data-stu-id="8d751-130">Enable the rule store authorization.</span></span>  
  
6.  <span data-ttu-id="8d751-131">El miembro del grupo RE_ADMIN_USERS crea la autorización AG2 y da permiso READ_EXECUTE a User2.</span><span class="sxs-lookup"><span data-stu-id="8d751-131">Member of the RE_ADMIN_USERS group creates authorization AG2 with READ_EXECUTE permission to User2.</span></span>  
  
7.  <span data-ttu-id="8d751-132">El creador asocia AG2 con el conjunto de reglas.</span><span class="sxs-lookup"><span data-stu-id="8d751-132">Creator associates AG2 with the rule set.</span></span> <span data-ttu-id="8d751-133">Aunque el creador no tiene derechos suficientes para hacerlo, no aparece ningún mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="8d751-133">Although the creator does not have sufficient right to do so, no error message appears.</span></span>  
  
8.  <span data-ttu-id="8d751-134">Se produce un error en el intento de lectura del conjunto de reglas por parte de User2.</span><span class="sxs-lookup"><span data-stu-id="8d751-134">Attempt to read the rule set by User2 fails.</span></span>