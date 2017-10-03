---
title: 'Paso 4: Crear un BeginDoc2 XML de ejemplo | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7cdda509-085f-4485-b488-c045d589ee96
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65598296f7136dc47c747165c9f7aba20602be4f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-create-a-sample-xml-begindoc"></a><span data-ttu-id="9d23c-102">Paso 4: Crear un XML de ejemplo de BeginDoc</span><span class="sxs-lookup"><span data-stu-id="9d23c-102">Step 4: Create a Sample XML BeginDoc</span></span>
<span data-ttu-id="9d23c-103">Guarde el siguiente código en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="9d23c-103">Save the following code into an XML file.</span></span> <span data-ttu-id="9d23c-104">Si su prueba sigue los pasos de este ejemplo y usa la selección de objetos J.D. Edwars EnterpriseOne del ejemplo,</span><span class="sxs-lookup"><span data-stu-id="9d23c-104">If your test uses the steps in this example, and uses the example's J.D.</span></span> <span data-ttu-id="9d23c-105">[JDE://CSALES/B4200310], podrá colocarlo en la carpeta de entrada así como lo que salió de la carpeta Out designada (la carpeta enlazada al puerto EndDocOut).</span><span class="sxs-lookup"><span data-stu-id="9d23c-105">Edwards EnterpriseOne object selection, [JDE://CSALES/B4200310], you can drop this into the Input folder and what it come out the designated Out folder (the folder bound to the EndDocOut port).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9d23c-106">Tendrá que modificar algunos de los valores para que señalen a su servidor J.D.</span><span class="sxs-lookup"><span data-stu-id="9d23c-106">You will have to modify some of the values to point to your J.D.</span></span> <span data-ttu-id="9d23c-107">Edwards EnterpriseOne. Por ejemplo, el valor definido en szCMComputerID.</span><span class="sxs-lookup"><span data-stu-id="9d23c-107">Edwards EnterpriseOne server, for example, the value set in szCMComputerID.</span></span>  
  
```  
<ns0:F4211FSBeginDoc xmlns:ns0="http://schemas.microsoft.com/  
      [JDE://CSALES/B4200310]">  
   <ns0:mnCMJobNumber></ns0:mnCMJobNumber>  
   <ns0:cCMDocAction>A</ns0:cCMDocAction>  
   <ns0:cCMProcessEdits>1</ns0:cCMProcessEdits>  
   <ns0:szCMComputerID>BVISION02</ns0:szCMComputerID>  
   <ns0:cCMUpdateWriteToWF>2</ns0:cCMUpdateWriteToWF>  
   <ns0:szCMProgramID>XMLInterop</ns0:szCMProgramID>  
   <ns0:szCMVersion>ZJDE0001</ns0:szCMVersion>  
   <ns0:szOrderType>SO</ns0:szOrderType>  
   <ns0:szBusinessUnit>M30</ns0:szBusinessUnit>  
   <ns0:szOriginalOrderCo></ns0:szOriginalOrderCo>  
   <ns0:szOriginalOrderNo></ns0:szOriginalOrderNo>  
   <ns0:szOriginalOrderType></ns0:szOriginalOrderType>  
   <ns0:mnAddressNumber>1001</ns0:mnAddressNumber>  
   <ns0:jdOrderDate></ns0:jdOrderDate>  
   <ns0:szReference></ns0:szReference>  
   <ns0:cApplyFreightYN>Y</ns0:cApplyFreightYN>  
   <ns0:szCurrencyCode></ns0:szCurrencyCode>  
   <ns0:cWKSourceOfData></ns0:cWKSourceOfData>  
   <ns0:cWKProcMode></ns0:cWKProcMode>  
   <ns0:mnWKSuppressProcess>0</ns0:mnWKSuppressProcess>  
   <ns0:cRetrieveOrderNo>1</ns0:cRetrieveOrderNo>  
   <ns0:nSourceOfOrder>0</ns0:nSourceOfOrder>  
</ns0:F4211FSBeginDoc>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9d23c-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d23c-108">See Also</span></span>  
 <span data-ttu-id="9d23c-109">[Paso 1: Hacer referencia al esquema DLL](../core/step-1-reference-the-schema-dll1.md) </span><span class="sxs-lookup"><span data-stu-id="9d23c-109">[Step 1: Reference the Schema DLL](../core/step-1-reference-the-schema-dll1.md) </span></span>  
 <span data-ttu-id="9d23c-110">[Paso 2: Crear la orquestación](../core/step-2-create-the-orchestration2.md) </span><span class="sxs-lookup"><span data-stu-id="9d23c-110">[Step 2: Create the Orchestration](../core/step-2-create-the-orchestration2.md) </span></span>  
 [<span data-ttu-id="9d23c-111">Paso 3: Completar y ejecutar el proyecto</span><span class="sxs-lookup"><span data-stu-id="9d23c-111">Step 3: Complete and Run the Project</span></span>](../core/step-3-complete-and-run-the-project1.md)