---
title: Mediante la validación de datos dinámicos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- dynamic data validation
- validating, dynamic data
ms.assetid: 8dac7f74-92a7-447c-97bf-b1f3ce39b614
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3387117648329828c9276545eafddca6872c4aa2
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009045"
---
# <a name="using-dynamic-data-validation"></a><span data-ttu-id="99445-102">Mediante la validación de datos dinámicos</span><span class="sxs-lookup"><span data-stu-id="99445-102">Using Dynamic Data Validation</span></span>
<span data-ttu-id="99445-103">Una parte importante de la validación de datos dinámicos se está validando contenido del mensaje con datos dinámicos, que incluye validar el formato del mensaje y el contenido del mensaje.</span><span class="sxs-lookup"><span data-stu-id="99445-103">An important part of dynamic data validation is validating message content against dynamic data, which includes validating the message format and the message content.</span></span> <span data-ttu-id="99445-104">Un esquema de documento, que [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Server se implementa en un archivo XSD, define y valida los formatos de mensaje.</span><span class="sxs-lookup"><span data-stu-id="99445-104">A document schema, which [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Server implements in an XSD file, defines and validates message formats.</span></span> <span data-ttu-id="99445-105">Las reglas de negocios definen el contenido del mensaje, que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] valida a través de directivas de motor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="99445-105">Business rules define message content, which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] validates through Business Rule Engine policies.</span></span> <span data-ttu-id="99445-106">Validación de contenido puede incluir la confirmación de que los datos en la instancia de mensaje coincide con los datos que pueden cambiar con relativa frecuencia.</span><span class="sxs-lookup"><span data-stu-id="99445-106">Content validation can include confirmation that data in the message instance matches data that may change with relative frequency.</span></span> [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="99445-107">[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]implementa este tipo de validación de forma dinámica, para que pueda actualizar estos datos en un entorno de producción, sin tener que compilar el código o cerrar los servicios.</span><span class="sxs-lookup"><span data-stu-id="99445-107">[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] implements this type of validation in a dynamic manner, so that you can update this data in a production environment, without having to recompile code or shut down services.</span></span>  
  
## <a name="validate-and-expose-data"></a><span data-ttu-id="99445-108">Validar y exponer los datos</span><span class="sxs-lookup"><span data-stu-id="99445-108">Validate and Expose Data</span></span>  
 <span data-ttu-id="99445-109">Existen dos pasos para realizar la validación de datos dinámicos (DDV):</span><span class="sxs-lookup"><span data-stu-id="99445-109">There are two steps in performing Dynamic Data Validation (DDV):</span></span>  
  
-   <span data-ttu-id="99445-110">Exponer los datos.</span><span class="sxs-lookup"><span data-stu-id="99445-110">Expose the data.</span></span>  
  
-   <span data-ttu-id="99445-111">Aplicar reglas de validación utilizando esos datos.</span><span class="sxs-lookup"><span data-stu-id="99445-111">Apply validation rules using that data.</span></span>  
  
 <span data-ttu-id="99445-112">DDV proporciona la siguiente compatibilidad para almacenar, exponer y almacenar en caché datos dinámicos:</span><span class="sxs-lookup"><span data-stu-id="99445-112">DDV provides the following support for storing, exposing, and caching dynamic data:</span></span>  
  
-   <span data-ttu-id="99445-113">El motor de reglas de negocios o la clase de mensaje realiza la validación.</span><span class="sxs-lookup"><span data-stu-id="99445-113">The Business Rule Engine or Message Class performs validation.</span></span>  
  
-   <span data-ttu-id="99445-114">El motor de reglas de negocios expone los datos a través del vocabulario de columna de tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="99445-114">The Business Rule Engine exposes data through the Database table column vocabulary.</span></span> <span data-ttu-id="99445-115">El motor de reglas de negocios valida estos datos dinámicos frente a mensajes mediante la implementación de un conjunto de reglas que se ejecuta desde una canalización u orquestación.</span><span class="sxs-lookup"><span data-stu-id="99445-115">The Business Rule Engine validates this dynamic data against messages by implementing a rule set that runs from a pipeline or orchestration.</span></span>  
  
-   <span data-ttu-id="99445-116">Interfaces de SQL existente, como el Administrador corporativo de SQL y el analizador de consultas, exponer datos dinámicos que es pasivos en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="99445-116">Existing SQL interfaces, such as SQL Enterprise Manager and Query Analyzer, expose dynamic data that is passive at design time.</span></span>  
  
-   <span data-ttu-id="99445-117">La definición de vocabulario de motor de reglas de negocios base de datos tabla columna expone datos dinámicos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="99445-117">The Business Rule Engine database table column vocabulary definition exposes dynamic data at run time.</span></span>  
  
-   <span data-ttu-id="99445-118">El motor de reglas de negocios expone los datos de la instancia de mensaje en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="99445-118">The Business Rule Engine exposes message instance data at run time.</span></span>  
  
-   <span data-ttu-id="99445-119">Una definición de vocabulario de documento XML de motor de reglas de negocios expone los datos de la instancia de mensaje en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="99445-119">A Business Rules Engine XML document vocabulary definition exposes message instance data at design time.</span></span>  
  
-   <span data-ttu-id="99445-120">Puede crear reglas en tiempo de diseño en la interfaz de usuario del compositor de reglas de negocio o directamente en las reglas de lenguaje negocios (BRL) XML en un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="99445-120">You can compose rules at design time in the Business Rule Composer user interface or directly in Business Rules Language (BRL) XML in a text editor.</span></span>  
  
 <span data-ttu-id="99445-121">Para obtener más información acerca de las reglas de negocios y el motor de reglas de negocios, vea "Desarrollar con reglas de negocios" en la Ayuda de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="99445-121">For more information about business rules and the Business Rule Engine, see "Developing with Business Rules" in BizTalk Server Help.</span></span>  
  
## <a name="extending-ddv"></a><span data-ttu-id="99445-122">Extender DDV</span><span class="sxs-lookup"><span data-stu-id="99445-122">Extending DDV</span></span>  
 <span data-ttu-id="99445-123">Si cambia la validación de campos cruzados basada en HL7 o validación de tipo de datos, se deben tener en cuenta dos cosas:</span><span class="sxs-lookup"><span data-stu-id="99445-123">If you change HL7-based cross-field validation or data type validation, you must note two things:</span></span>  
  
-   <span data-ttu-id="99445-124">Si modifica una regla existente, no es necesario volver a implementar.</span><span class="sxs-lookup"><span data-stu-id="99445-124">If you modify an existing rule, you do not need to redeploy.</span></span>  
  
-   <span data-ttu-id="99445-125">Si crea o eliminar una nueva regla que afecta un componente de canalización, a continuación, debe volver a compilar.</span><span class="sxs-lookup"><span data-stu-id="99445-125">If you create or delete a new rule that a pipeline component affects, then you must recompile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99445-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="99445-126">See Also</span></span>  
 <span data-ttu-id="99445-127">[Guía de programación](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md) </span><span class="sxs-lookup"><span data-stu-id="99445-127">[Programming Guide](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md) </span></span>  
 [<span data-ttu-id="99445-128">Tutorial de enriquecimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="99445-128">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)