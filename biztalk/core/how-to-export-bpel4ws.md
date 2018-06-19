---
title: Cómo exportar BPEL4WS | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BPEL4WS, exporting
- BPEL4WS, restrictions
- orchestrations, BPEL4WS
ms.assetid: 4648dfcf-cf48-4471-b088-07252c080fb8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b16c2e34b498a9fb8d5fd3f6e69f022c2876a763
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253836"
---
# <a name="how-to-export-bpel4ws"></a><span data-ttu-id="4c13f-102">Cómo exportar BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="4c13f-102">How to Export BPEL4WS</span></span>
<span data-ttu-id="4c13f-103">Puede exportar una orquestación de BizTalk existente al lenguaje BPEL4WS.</span><span class="sxs-lookup"><span data-stu-id="4c13f-103">You can export an existing BizTalk orchestration to BPEL4WS.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4c13f-104">Esta versión de BizTalk Server es compatible con BPEL4WS 1.1.</span><span class="sxs-lookup"><span data-stu-id="4c13f-104">This release of BizTalk Server supports BPEL4WS 1.1.</span></span> <span data-ttu-id="4c13f-105">No es compatible con BPEL4WS 1.0 para realizar importaciones o exportaciones.</span><span class="sxs-lookup"><span data-stu-id="4c13f-105">You cannot import or export BPEL4WS 1.0.</span></span>  
  
 <span data-ttu-id="4c13f-106">Si está exportando, la compatibilidad con BPEL4WS para la compilación requiere que las orquestaciones solo contengan características comunes entre XLANG/s y BPEL4WS, o características que se puedan traducir a BPEL4WS sin que se vea afectado el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="4c13f-106">If you are exporting, BPEL4WS compliance for compilation requires that orchestrations contain only features that are common between XLANG/s and BPEL4WS, or features that can be translated into BPEL4WS without affecting behavior.</span></span>  
  
## <a name="export-restrictions-on-orchestrations-for-bpel4ws-compliance"></a><span data-ttu-id="4c13f-107">Restricciones de exportación en las orquestaciones para la compatibilidad con BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="4c13f-107">Export restrictions on orchestrations for BPEL4WS compliance</span></span>  
  
-   <span data-ttu-id="4c13f-108">No puede usar la forma Orquestación de llamada ni la forma Iniciar orquestación.</span><span class="sxs-lookup"><span data-stu-id="4c13f-108">You cannot use the Call Orchestration shape or the Start Orchestration shape.</span></span>  
  
-   <span data-ttu-id="4c13f-109">No puede utilizar la forma Transformación.</span><span class="sxs-lookup"><span data-stu-id="4c13f-109">You cannot use the Transform shape.</span></span>  
  
-   <span data-ttu-id="4c13f-110">No puede invocar métodos en componentes .NET personalizados.</span><span class="sxs-lookup"><span data-stu-id="4c13f-110">You cannot invoke methods on custom .NET components.</span></span>  
  
-   <span data-ttu-id="4c13f-111">No puede aplicar un tiempo de espera a una transacción de larga ejecución.</span><span class="sxs-lookup"><span data-stu-id="4c13f-111">You cannot apply a timeout to a long-running transaction.</span></span>  
  
-   <span data-ttu-id="4c13f-112">La orquestación no acepta parámetros.</span><span class="sxs-lookup"><span data-stu-id="4c13f-112">Your orchestration cannot take parameters.</span></span>  
  
-   <span data-ttu-id="4c13f-113">Los controladores de compensación que se pueden llamar no pueden tener parámetros.</span><span class="sxs-lookup"><span data-stu-id="4c13f-113">Callable compensation handlers cannot have parameters.</span></span>  
  
-   <span data-ttu-id="4c13f-114">Los tipos de variables deben ser compatibles en XPATH.</span><span class="sxs-lookup"><span data-stu-id="4c13f-114">Variable types must be supportable in XPATH.</span></span>  
  
-   <span data-ttu-id="4c13f-115">No puede usar la forma Suspender.</span><span class="sxs-lookup"><span data-stu-id="4c13f-115">You cannot use the Suspend shape.</span></span>  
  
-   <span data-ttu-id="4c13f-116">Los valores literales deben ser de uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="4c13f-116">Literal values must be one of the following types:</span></span>  
  
     <span data-ttu-id="4c13f-117">boolean, char, byte, sbyte, int32, uint32, int64, uint64, single, double o string</span><span class="sxs-lookup"><span data-stu-id="4c13f-117">boolean, char, byte, sbyte, int32, uint32, int64, uint64, single, double, string</span></span>  
  
-   <span data-ttu-id="4c13f-118">Solo se permiten operadores aritméticos en operandos de los siguientes tipos numéricos:</span><span class="sxs-lookup"><span data-stu-id="4c13f-118">Arithmetic operators are allowed only on operands of following numeric types:</span></span>  
  
     <span data-ttu-id="4c13f-119">byte, sbyte, int32, uint32, int64, uint64, single o double</span><span class="sxs-lookup"><span data-stu-id="4c13f-119">byte, sbyte, int32, uint32, int64, uint64, single, double</span></span>  
  
-   <span data-ttu-id="4c13f-120">No se pueden aplicar operadores relacionales al tipo char.</span><span class="sxs-lookup"><span data-stu-id="4c13f-120">Relational operators cannot be applied to type char.</span></span>  
  
-   <span data-ttu-id="4c13f-121">No puede hacer referencia a una propiedad servicelink en una expresión.</span><span class="sxs-lookup"><span data-stu-id="4c13f-121">You cannot make a reference to a servicelink property in an expression.</span></span>  
  
-   <span data-ttu-id="4c13f-122">No se puede realizar ninguna acción entre una **enviar** forma y un **recepción** forma que utilicen el mismo puerto de solicitud-respuesta de salida.</span><span class="sxs-lookup"><span data-stu-id="4c13f-122">You cannot perform any actions between a **Send** shape and a **Receive** shape that use the same outbound request-response port.</span></span>  
  
-   <span data-ttu-id="4c13f-123">No puede hacer referencia de forma indirecta a un servicio Web; por ejemplo, a través de una referencia a otro proyecto que contenga una referencia.</span><span class="sxs-lookup"><span data-stu-id="4c13f-123">You cannot indirectly reference a web service, as through a reference to another project that contains a reference.</span></span> <span data-ttu-id="4c13f-124">Debe hacer referencia de forma explícita al servicio Web en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="4c13f-124">You must explicitly reference the web service in your project.</span></span>  
  
-   <span data-ttu-id="4c13f-125">No puede especificar un valor DateTime o TimeSpan constante en un retraso.</span><span class="sxs-lookup"><span data-stu-id="4c13f-125">You cannot specify a constant DateTime or TimeSpan in a delay.</span></span> <span data-ttu-id="4c13f-126">En su lugar, use una de las clases de conversión en el espacio de nombres System.Xml:</span><span class="sxs-lookup"><span data-stu-id="4c13f-126">Instead, use one of the conversion classes in the System.Xml namespace:</span></span>  
  
     <span data-ttu-id="4c13f-127">Para un valor DateTime constante: System.Xml.XmlConvert.ToDateTime, por ejemplo System.Xml.XmlConvert.ToDateTime("2004-04-15")</span><span class="sxs-lookup"><span data-stu-id="4c13f-127">For a constant DateTime: System.Xml.XmlConvert.ToDateTime, e.g System.Xml.XmlConvert.ToDateTime("2004-04-15")</span></span>  
  
     <span data-ttu-id="4c13f-128">Para un valor TimeSpan constante: System.Xml.XmlConvert.ToTimeSpan, por ejemplo System.Xml.XmlConvert.ToTimeSpan("2004-04-15")</span><span class="sxs-lookup"><span data-stu-id="4c13f-128">For a constant TimeSpan: System.Xml.XmlConvert.ToTimeSpan, e.g System.Xml.XmlConvert.ToTimeSpan("2004-04-15")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c13f-129">Los literales de carácter se exportan como enteros sin signo.</span><span class="sxs-lookup"><span data-stu-id="4c13f-129">Character literals are exported as unsigned integers.</span></span> <span data-ttu-id="4c13f-130">Por ejemplo, "a" se exporta como 97, "b" se exporta como 98, etc.</span><span class="sxs-lookup"><span data-stu-id="4c13f-130">For example, 'a' is exported as 97, 'b' is exported as 98, and so forth.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="4c13f-131">Los nombres de identificador deben ajustarse a la especificación del Lenguaje de marcado extensible (XML) 1.0 de W3C.</span><span class="sxs-lookup"><span data-stu-id="4c13f-131">Identifier names must conform to the W3C Extensible Markup Language (XML) 1.0 specification.</span></span>  
  
#### <a name="to-export-an-orchestration-to-bpel4ws"></a><span data-ttu-id="4c13f-132">Para exportar una orquestación al lenguaje BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="4c13f-132">To export an orchestration to BPEL4WS</span></span>  
  
1.  <span data-ttu-id="4c13f-133">Agregue un nuevo elemento de tipo Orquestación de BizTalk al proyecto.</span><span class="sxs-lookup"><span data-stu-id="4c13f-133">Add a new item of type BizTalk Orchestration to your project.</span></span>  
  
2.  <span data-ttu-id="4c13f-134">Haga clic en la superficie de diseño para abrir la ventana Propiedades de orquestación.</span><span class="sxs-lookup"><span data-stu-id="4c13f-134">Click the design surface to bring up the Orchestration Properties window.</span></span>  
  
3.  <span data-ttu-id="4c13f-135">Establecer **Exportable a módulo** en True.</span><span class="sxs-lookup"><span data-stu-id="4c13f-135">Set **Module Exportable** to True.</span></span>  
  
4.  <span data-ttu-id="4c13f-136">Tipo en el espacio de nombres que desee para **módulo XML Target Namespace**.</span><span class="sxs-lookup"><span data-stu-id="4c13f-136">Type in the namespace you want for **Module XML Target Namespace**.</span></span>  
  
5.  <span data-ttu-id="4c13f-137">Establecer **Exportable a orquestación** en True.</span><span class="sxs-lookup"><span data-stu-id="4c13f-137">Set **Orchestration Exportable** to True.</span></span>  
  
6.  <span data-ttu-id="4c13f-138">Tipo en el espacio de nombres que desee para **orquestación XML Target Namespace**.</span><span class="sxs-lookup"><span data-stu-id="4c13f-138">Type in the namespace you want for **Orchestration XML Target Namespace**.</span></span>  
  
7.  <span data-ttu-id="4c13f-139">En el Explorador de soluciones, haga clic en el. Archivo ODX para la orquestación.</span><span class="sxs-lookup"><span data-stu-id="4c13f-139">In Solution Explorer, right-click the .ODX file for your orchestration.</span></span>  
  
8.  <span data-ttu-id="4c13f-140">Seleccione **exportar a BPEL**.</span><span class="sxs-lookup"><span data-stu-id="4c13f-140">Select **Export to BPEL**.</span></span>  
  
     <span data-ttu-id="4c13f-141">La orquestación se exportará a BPEL4WS.</span><span class="sxs-lookup"><span data-stu-id="4c13f-141">Your orchestration will be exported to BPEL4WS.</span></span> <span data-ttu-id="4c13f-142">Consulte las ventanas Resultados y Lista de tareas para confirmar que la orquestación se ha exportado correctamente o diagnosticar problemas.</span><span class="sxs-lookup"><span data-stu-id="4c13f-142">See the Output Window and Task List to confirm success or diagnose problems.</span></span> <span data-ttu-id="4c13f-143">Una vez finalizada correctamente la exportación, se creará un archivo .WSDL y un archivo .BPEL en el directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4c13f-143">Once your export succeeds, a .WSDL file and a .BPEL file will be created in your project directory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c13f-144">Si la orquestación contiene una asignación a un vínculo de rol (vínculo de servicio) o una asignación literal a un puerto dinámico, BizTalk genera una referencia ficticia de extremo BPEL4WS y una advertencia.</span><span class="sxs-lookup"><span data-stu-id="4c13f-144">If your orchestration contains an assignment to a role link (service link) or a literal assignment to a dynamic port, BizTalk generates a dummy BPEL4WS endpoint reference and raises a warning.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c13f-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c13f-145">See Also</span></span>  
 <span data-ttu-id="4c13f-146">[Cómo importar BPEL4WS](../core/how-to-import-bpel4ws.md) </span><span class="sxs-lookup"><span data-stu-id="4c13f-146">[How to Import BPEL4WS](../core/how-to-import-bpel4ws.md) </span></span>  
 [<span data-ttu-id="4c13f-147">XLANG-s para las conversiones de tipo de BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="4c13f-147">XLANG-s to BPEL4WS Type Conversions</span></span>](../core/xlang-s-to-bpel4ws-type-conversions.md)