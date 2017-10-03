---
title: "Mediante la validación de datos dinámicos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dynamic data validation
- validating, dynamic data
ms.assetid: 8dac7f74-92a7-447c-97bf-b1f3ce39b614
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c08393b8e6d4b2563d6fb7ccdf49559943538ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-dynamic-data-validation"></a><span data-ttu-id="fba76-102">Mediante la validación de datos dinámicos</span><span class="sxs-lookup"><span data-stu-id="fba76-102">Using Dynamic Data Validation</span></span>
<span data-ttu-id="fba76-103">Una parte importante de la validación de datos dinámicos se está validando contenido del mensaje con datos dinámicos, que incluye validar el formato del mensaje y el contenido del mensaje.</span><span class="sxs-lookup"><span data-stu-id="fba76-103">An important part of dynamic data validation is validating message content against dynamic data, which includes validating the message format and the message content.</span></span> <span data-ttu-id="fba76-104">Un esquema de documento, que [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] implementa en un archivo XSD, define y valida los formatos de mensaje.</span><span class="sxs-lookup"><span data-stu-id="fba76-104">A document schema, which [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] implements in an XSD file, defines and validates message formats.</span></span> <span data-ttu-id="fba76-105">Las reglas de negocios definen el contenido del mensaje, que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] valida a través de directivas de motor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="fba76-105">Business rules define message content, which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] validates through Business Rule Engine policies.</span></span> <span data-ttu-id="fba76-106">Validación de contenido puede incluir la confirmación de que los datos en la instancia de mensaje coincide con los datos que pueden cambiar con relativa frecuencia.</span><span class="sxs-lookup"><span data-stu-id="fba76-106">Content validation can include confirmation that data in the message instance matches data that may change with relative frequency.</span></span> [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="fba76-107">[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]implementa este tipo de validación de forma dinámica, para que pueda actualizar estos datos en un entorno de producción, sin tener que compilar el código o cerrar los servicios.</span><span class="sxs-lookup"><span data-stu-id="fba76-107">[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] implements this type of validation in a dynamic manner, so that you can update this data in a production environment, without having to recompile code or shut down services.</span></span>  
  
## <a name="validate-and-expose-data"></a><span data-ttu-id="fba76-108">Validar y exponer los datos</span><span class="sxs-lookup"><span data-stu-id="fba76-108">Validate and Expose Data</span></span>  
 <span data-ttu-id="fba76-109">Existen dos pasos para realizar la validación de datos dinámicos (DDV):</span><span class="sxs-lookup"><span data-stu-id="fba76-109">There are two steps in performing Dynamic Data Validation (DDV):</span></span>  
  
-   <span data-ttu-id="fba76-110">Exponer los datos.</span><span class="sxs-lookup"><span data-stu-id="fba76-110">Expose the data.</span></span>  
  
-   <span data-ttu-id="fba76-111">Aplicar reglas de validación utilizando esos datos.</span><span class="sxs-lookup"><span data-stu-id="fba76-111">Apply validation rules using that data.</span></span>  
  
 <span data-ttu-id="fba76-112">DDV proporciona la siguiente compatibilidad para almacenar, exponer y almacenar en caché datos dinámicos:</span><span class="sxs-lookup"><span data-stu-id="fba76-112">DDV provides the following support for storing, exposing, and caching dynamic data:</span></span>  
  
-   <span data-ttu-id="fba76-113">El motor de reglas de negocios o la clase de mensaje realiza la validación.</span><span class="sxs-lookup"><span data-stu-id="fba76-113">The Business Rule Engine or Message Class performs validation.</span></span>  
  
-   <span data-ttu-id="fba76-114">El motor de reglas de negocios expone los datos a través del vocabulario de columna de tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="fba76-114">The Business Rule Engine exposes data through the Database table column vocabulary.</span></span> <span data-ttu-id="fba76-115">El motor de reglas de negocios valida estos datos dinámicos frente a mensajes mediante la implementación de un conjunto de reglas que se ejecuta desde una canalización u orquestación.</span><span class="sxs-lookup"><span data-stu-id="fba76-115">The Business Rule Engine validates this dynamic data against messages by implementing a rule set that runs from a pipeline or orchestration.</span></span>  
  
-   <span data-ttu-id="fba76-116">Interfaces de SQL existente, como el Administrador corporativo de SQL y el analizador de consultas, exponer datos dinámicos que es pasivos en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="fba76-116">Existing SQL interfaces, such as SQL Enterprise Manager and Query Analyzer, expose dynamic data that is passive at design time.</span></span>  
  
-   <span data-ttu-id="fba76-117">La definición de vocabulario de motor de reglas de negocios base de datos tabla columna expone datos dinámicos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fba76-117">The Business Rule Engine database table column vocabulary definition exposes dynamic data at run time.</span></span>  
  
-   <span data-ttu-id="fba76-118">El motor de reglas de negocios expone los datos de la instancia de mensaje en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fba76-118">The Business Rule Engine exposes message instance data at run time.</span></span>  
  
-   <span data-ttu-id="fba76-119">Una definición de vocabulario de documento XML de motor de reglas de negocios expone los datos de la instancia de mensaje en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="fba76-119">A Business Rules Engine XML document vocabulary definition exposes message instance data at design time.</span></span>  
  
-   <span data-ttu-id="fba76-120">Puede crear reglas en tiempo de diseño en la interfaz de usuario del compositor de reglas de negocio o directamente en las reglas de lenguaje negocios (BRL) XML en un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="fba76-120">You can compose rules at design time in the Business Rule Composer user interface or directly in Business Rules Language (BRL) XML in a text editor.</span></span>  
  
 <span data-ttu-id="fba76-121">Para obtener más información acerca de las reglas de negocios y el motor de reglas de negocios, vea "Desarrollar con las reglas de negocios" en [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="fba76-121">For more information about business rules and the Business Rule Engine, see "Developing with Business Rules" in [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span>  
  
## <a name="extending-ddv"></a><span data-ttu-id="fba76-122">Extender DDV</span><span class="sxs-lookup"><span data-stu-id="fba76-122">Extending DDV</span></span>  
 <span data-ttu-id="fba76-123">Si cambia la validación de campos cruzados basada en HL7 o validación de tipo de datos, se deben tener en cuenta dos cosas:</span><span class="sxs-lookup"><span data-stu-id="fba76-123">If you change HL7-based cross-field validation or data type validation, you must note two things:</span></span>  
  
-   <span data-ttu-id="fba76-124">Si modifica una regla existente, no es necesario volver a implementar.</span><span class="sxs-lookup"><span data-stu-id="fba76-124">If you modify an existing rule, you do not need to redeploy.</span></span>  
  
-   <span data-ttu-id="fba76-125">Si crea o eliminar una nueva regla que afecta un componente de canalización, a continuación, debe volver a compilar.</span><span class="sxs-lookup"><span data-stu-id="fba76-125">If you create or delete a new rule that a pipeline component affects, then you must recompile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fba76-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="fba76-126">See Also</span></span>  
 <span data-ttu-id="fba76-127">[Guía de programación](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md) </span><span class="sxs-lookup"><span data-stu-id="fba76-127">[Programming Guide](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md) </span></span>  
 [<span data-ttu-id="fba76-128">Tutorial de enriquecimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="fba76-128">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)