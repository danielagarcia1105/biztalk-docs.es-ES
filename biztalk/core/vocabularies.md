---
title: Vocabularios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, vocabularies
- vocabularies, about vocabularies
- vocabularies
- Business Rules Engine, vocabularies
ms.assetid: 591673a0-2c4d-41ca-9997-b363c086dd66
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9e20dfead51d54822d3316c8819d04a259cfa83
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288012"
---
# <a name="vocabularies"></a><span data-ttu-id="efc1a-102">Vocabularios</span><span class="sxs-lookup"><span data-stu-id="efc1a-102">Vocabularies</span></span>
<span data-ttu-id="efc1a-103">Los términos usados para definir condiciones y acciones de reglas se expresan normalmente con una nomenclatura específica del dominio o del sector.</span><span class="sxs-lookup"><span data-stu-id="efc1a-103">The terms used to define rule conditions and actions are usually expressed by domain or industry-specific nomenclature.</span></span> <span data-ttu-id="efc1a-104">Por ejemplo, un usuario de correo electrónico escribe reglas en términos de mensajes "recibidos de" y mensajes "recibidos después de", mientras que un analista de seguros escribe reglas en términos de "factores de riesgo" e "importe de cobertura".</span><span class="sxs-lookup"><span data-stu-id="efc1a-104">For example, an e-mail user writes rules in terms of messages "received from" and messages "received after," while an insurance business analyst writes rules in terms of "risk factors" and "coverage amount."</span></span>  
  
 <span data-ttu-id="efc1a-105">Subyacentes a esta terminología específica del dominio se encuentran los artefactos tecnológicos (objetos, tablas de base de datos y documentos XML) que implementan condiciones y acciones de reglas.</span><span class="sxs-lookup"><span data-stu-id="efc1a-105">Underlying this domain-specific terminology are the technology artifacts (objects, database tables, and XML documents) that implement rule conditions and rule actions.</span></span> <span data-ttu-id="efc1a-106">Vocabulariesare diseñado para salvar la brecha entre la semántica del negocio y la implementación.</span><span class="sxs-lookup"><span data-stu-id="efc1a-106">Vocabulariesare designed to bridge the gap between business semantics and implementation.</span></span>  
  
 <span data-ttu-id="efc1a-107">Por ejemplo, un enlace de datos para un estado de aprobación puede apuntar a una determinada columna en una determinada fila de una determinada base de datos, representada como una consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="efc1a-107">For example, a data binding for an approval status might point to a certain column in a certain row in a certain database, represented as an SQL query.</span></span> <span data-ttu-id="efc1a-108">En lugar de insertar este tipo de representación compleja de una regla, puede crear una definición de vocabulario asociada con ese enlace de datos, con un nombre descriptivo de "Estado".</span><span class="sxs-lookup"><span data-stu-id="efc1a-108">Instead of inserting this sort of complex representation in a rule, you might instead create a vocabulary definition, associated with that data binding, with a friendly name of "Status."</span></span> <span data-ttu-id="efc1a-109">A continuación, puede incluir "Estado" en cualquier número de reglas y el motor de reglas puede recuperar los datos correspondientes de la tabla.</span><span class="sxs-lookup"><span data-stu-id="efc1a-109">Subsequently you can include "Status" in any number of rules, and the rule engine can retrieve the corresponding data from the table.</span></span>  
  
 <span data-ttu-id="efc1a-110">A *vocabulario* es una colección de definiciones que consta de nombres descriptivos de hechos utilizados en condiciones de regla y las acciones.</span><span class="sxs-lookup"><span data-stu-id="efc1a-110">A *vocabulary* is a collection of definitions consisting of friendly names for the facts used in rule conditions and actions.</span></span> <span data-ttu-id="efc1a-111">Las definiciones de vocabulario facilitan la lectura, la comprensión y el compartimiento de reglas entre personas de un dominio empresarial concreto.</span><span class="sxs-lookup"><span data-stu-id="efc1a-111">Vocabulary definitions make the rules easier to read, understand, and share by people in a particular business domain.</span></span>  
  
 <span data-ttu-id="efc1a-112">Puede usar el Compositor de reglas de negocio para definir vocabularios que se ponen después en el almacén de reglas compartidas.</span><span class="sxs-lookup"><span data-stu-id="efc1a-112">You can use the Business Rule Composer to define vocabularies that are then placed in the shared rule store.</span></span> <span data-ttu-id="efc1a-113">También pueden usar vocabularios los programadores de herramientas responsables de integrar la creación de reglas en aplicaciones nuevas o existentes.</span><span class="sxs-lookup"><span data-stu-id="efc1a-113">Vocabularies can also be consumed by tool developers responsible for integrating rule authoring into new or existing applications.</span></span>  
  
 <span data-ttu-id="efc1a-114">Para poder usar un vocabulario, se le debe poner la versión y se debe publicar en el almacén de reglas.</span><span class="sxs-lookup"><span data-stu-id="efc1a-114">Before you can use a vocabulary, it must be stamped with a version and published in your rule store.</span></span> <span data-ttu-id="efc1a-115">Esto es para garantizar que las definiciones del vocabulario no cambiarán y para mantener la integridad referencial.</span><span class="sxs-lookup"><span data-stu-id="efc1a-115">This is to guarantee that the definitions in the vocabulary will not change, and to preserve referential integrity.</span></span> <span data-ttu-id="efc1a-116">Esto significa que las directivas que usan una versión concreta del vocabulario no darán errores de forma inesperada debido a cambios en el vocabulario subyacente.</span><span class="sxs-lookup"><span data-stu-id="efc1a-116">This means that any policies that use that particular version of the vocabulary will not fail unexpectedly due to changes in the underlying vocabulary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efc1a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="efc1a-117">See Also</span></span>  
 [<span data-ttu-id="efc1a-118">Motor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="efc1a-118">Business Rules Engine</span></span>](../core/business-rules-engine.md)