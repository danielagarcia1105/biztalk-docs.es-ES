---
title: Validación en tiempo de ejecución para el motor de orquestaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, assemblies
- orchestrations, validating
- validating, orchestration engine
- schemas, validating
- correlations, validating
- validating, schemas
- orchestration engine, runtime validation
- assemblies, validating
- validating, correlations
- validating, orchestrations
- validating
ms.assetid: f6085889-05d6-4eba-a528-9d034c4e4225
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e53adb5aa42c7dfe23df50707754bde200ea838a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269268"
---
# <a name="runtime-validation-for-the-orchestration-engine"></a><span data-ttu-id="49565-102">Validación en tiempo de ejecución del motor de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="49565-102">Runtime Validation for the Orchestration Engine</span></span>
<span data-ttu-id="49565-103">Puede configurar el motor de orquestaciones para realizar distintas validaciones en tiempo de ejecución que le ayuden a probar su orquestación y a diagnosticar los errores de datos o de configuración que se puedan producir.</span><span class="sxs-lookup"><span data-stu-id="49565-103">You can configure the orchestration engine to perform various runtime validations that can help you test your orchestration and diagnose configuration or data errors that might arise.</span></span>  
  
 <span data-ttu-id="49565-104">Puede establecer marcas en BTSNTSvc.exe.config, un archivo de configuración que puede crear o editar en el mismo directorio que BTSNTSvc.exe (normalmente en el directorio de implementación de BizTalk).</span><span class="sxs-lookup"><span data-stu-id="49565-104">You can set flags in BTSNTSvc.exe.config, a configuration file that you can create or edit in the same directory as BTSNTSvc.exe (normally in the BizTalk deployment directory).</span></span> <span data-ttu-id="49565-105">Puede establecer las marcas siguientes en el archivo BTSNTSvc.exe.config:</span><span class="sxs-lookup"><span data-stu-id="49565-105">You can set the following flags in the BTSNTSvc.exe.config file:</span></span>  
  
-   <span data-ttu-id="49565-106">Si establece la **ValidateAssemblies** indicador en `True`, el motor intenta cargar todos los ensamblados que se hace referencia a ensamblados dependientes inmediatos de una orquestación y en el error produce Microsoft.XLANGs.Core.AssemblyValidationException.</span><span class="sxs-lookup"><span data-stu-id="49565-106">If you set the **ValidateAssemblies** flag to `True`, the engine tries to load all assemblies referenced by immediate dependent assemblies of an orchestration and upon failure throws Microsoft.XLANGs.Core.AssemblyValidationException.</span></span>  
  
-   <span data-ttu-id="49565-107">Si establece la **ValidateSchemas** indicador en `True`, el motor utiliza System.Xml.XmlValidatingReader para validar cada esquema que representa un tipo de parte de mensaje y en caso de error, inicia System.Xml.XmlException.</span><span class="sxs-lookup"><span data-stu-id="49565-107">If you set the **ValidateSchemas** flag to `True`, the engine uses System.Xml.XmlValidatingReader to validate every schema representing a message part type and upon failure throws System.Xml.XmlException.</span></span>  
  
-   <span data-ttu-id="49565-108">Si establece la **ValidateCorrelations** indicador en `True`, el motor comprueba que en un convoy paralelo todos los mensajes que coinciden con uno de los convoyes recibe tienen los mismos valores de propiedad de correlación y en caso de error produce Microsoft.XLANGs.Core.CorrelationValidationException.</span><span class="sxs-lookup"><span data-stu-id="49565-108">If you set the **ValidateCorrelations** flag to `True`, the engine verifies that in a parallel convoy all messages that match one of the convoy receives have the same correlation property values and upon failure throws Microsoft.XLANGs.Core.CorrelationValidationException.</span></span>  
  
-   <span data-ttu-id="49565-109">Si establece la **ExtendedLogging** indicador en `True`, el motor muestra las propiedades promocionadas en la información para Microsoft.XLANGs.BaseTypes.PublishMessageException para el mensaje que no se pudo publicar.</span><span class="sxs-lookup"><span data-stu-id="49565-109">If you set the **ExtendedLogging** flag to `True`, the engine displays the promoted properties in the information for Microsoft.XLANGs.BaseTypes.PublishMessageException for the message that failed to publish.</span></span>  
  
 <span data-ttu-id="49565-110">Si desea deshabilitar una validación, quite la marca completamente del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="49565-110">If you want to disable a validation, remove the flag entirely from the configuration file.</span></span> <span data-ttu-id="49565-111">Cuando todas las validaciones estén activadas, el motor validará los ensamblados, los esquemas y las correlaciones.</span><span class="sxs-lookup"><span data-stu-id="49565-111">When all validations are on, the engine will validate assemblies, schemas, and correlation.</span></span> <span data-ttu-id="49565-112">Para obtener más información y ejemplos del archivo BTSNTSvc.exe.config, consulte [configuración del motor de orquestación](../core/orchestration-engine-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="49565-112">For more information and examples of BTSNTSvc.exe.config, see [Orchestration Engine Configuration](../core/orchestration-engine-configuration.md).</span></span>  
  
## <a name="validate-assemblies"></a><span data-ttu-id="49565-113">Validar ensamblados</span><span class="sxs-lookup"><span data-stu-id="49565-113">Validate Assemblies</span></span>  
 <span data-ttu-id="49565-114">El motor de orquestaciones comprueba que están disponibles los ensamblados a los que hace referencia la orquestación</span><span class="sxs-lookup"><span data-stu-id="49565-114">The orchestration engine will verify that any assemblies referenced by the orchestration are available.</span></span> <span data-ttu-id="49565-115">Para que la validación se realice correctamente, todos los ensamblados a los que se hace referencia deben estar en la Caché de ensamblados global (GAC) cuando se activa la primera instancia de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="49565-115">For the validation to succeed, all referenced assemblies must be in the Global Assembly Cache (GAC) when the first instance of the orchestration is activated.</span></span> <span data-ttu-id="49565-116">Si se produce un error en la validación, se registrará un error en el registro de la aplicación y se suspenderá la orquestación.</span><span class="sxs-lookup"><span data-stu-id="49565-116">If the validation fails, an error will be logged to the application log and the orchestration will be suspended.</span></span>  
  
## <a name="validate-schemas"></a><span data-ttu-id="49565-117">Validar esquemas</span><span class="sxs-lookup"><span data-stu-id="49565-117">Validate Schemas</span></span>  
 <span data-ttu-id="49565-118">Cada vez que se asigna una parte XSD, el motor de orquestaciones validará los datos de la parte con su esquema.</span><span class="sxs-lookup"><span data-stu-id="49565-118">Any time an XSD part is assigned, the orchestration engine will validate the part's data against its schema.</span></span> <span data-ttu-id="49565-119">Si se produce un error en la validación, se registrará el error en el registro de la aplicación y se producirá una excepción.</span><span class="sxs-lookup"><span data-stu-id="49565-119">If the validation fails, the error will be logged to the application log and an exception will be thrown.</span></span>  
  
## <a name="validate-correlation"></a><span data-ttu-id="49565-120">Validar correlaciones</span><span class="sxs-lookup"><span data-stu-id="49565-120">Validate Correlation</span></span>  
 <span data-ttu-id="49565-121">El motor de orquestaciones confirmará que se reflejan los valores de la propiedad especificados para la correlación con una instancia específica de una orquestación en cualquier mensaje que se envíe desde dicha instancia de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="49565-121">The orchestration engine will confirm that the property values that are specified for correlation with a given instance of an orchestration are reflected in any messages that are sent from that orchestration instance.</span></span> <span data-ttu-id="49565-122">Si **validateCorrelation** no se establece, el motor supondrá que el mensaje enviado contiene los valores de correlación correctos y no se realizará ninguna comprobación.</span><span class="sxs-lookup"><span data-stu-id="49565-122">If **validateCorrelation** is not set, the engine will assume that the sent message contains the correct correlation values, and no check will be performed.</span></span>  
  
 <span data-ttu-id="49565-123">Si se produce un error en ninguna validación de correlación, el motor se registrará un error en el registro de aplicación y producirá una excepción de tipo **CorrelationValidationException**.</span><span class="sxs-lookup"><span data-stu-id="49565-123">If any correlation validation fails, the engine will log an error to the application log and throw an exception of type **CorrelationValidationException**.</span></span>  
  
 <span data-ttu-id="49565-124">De forma predeterminada, **validateCorrelation** no se ha establecido.</span><span class="sxs-lookup"><span data-stu-id="49565-124">By default, **validateCorrelation** is not set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49565-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="49565-125">See Also</span></span>  
 <span data-ttu-id="49565-126">[Depurar orquestaciones](../core/debugging-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="49565-126">[Debugging Orchestrations](../core/debugging-orchestrations.md) </span></span>  
 [<span data-ttu-id="49565-127">Configuración del motor de orquestación</span><span class="sxs-lookup"><span data-stu-id="49565-127">Orchestration Engine Configuration</span></span>](../core/orchestration-engine-configuration.md)