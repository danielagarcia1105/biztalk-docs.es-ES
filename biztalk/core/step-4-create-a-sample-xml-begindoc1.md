---
title: 'Paso 4: Crear un BeginDoc1 XML de ejemplo | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e494b4b2-4c83-4293-8ae8-acae29018e7f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a48a4ee378560ad2d0360445e3fb732bb46e79f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-create-a-sample-xml-begindoc"></a><span data-ttu-id="f0c19-102">Paso 4: Crear un XML de ejemplo de BeginDoc</span><span class="sxs-lookup"><span data-stu-id="f0c19-102">Step 4: Create a Sample XML BeginDoc</span></span>
<span data-ttu-id="f0c19-103">Guarde lo siguiente en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="f0c19-103">Save the following into an XML file.</span></span> <span data-ttu-id="f0c19-104">Si su prueba sigue los pasos de este ejemplo y usa la selección de objetos J.D. Edwars EnterpriseOne del ejemplo,</span><span class="sxs-lookup"><span data-stu-id="f0c19-104">If your test uses the steps in this example, and uses the example's J.D.</span></span> <span data-ttu-id="f0c19-105">Selección de objetos de Edwards OneWorld, [JDE://CSALES/B4200310], podrá colocarlo en la carpeta de entrada y lo que salió de la carpeta Out designada (la carpeta enlazada al puerto EndDocOut).</span><span class="sxs-lookup"><span data-stu-id="f0c19-105">Edwards OneWorld object selection, [JDE://CSALES/B4200310], you can drop this into the Input folder and what it come out the designated Out folder (the folder bound to the EndDocOut port).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0c19-106">Tendrá que modificar algunos de los valores para que señalen a su servidor J.D.</span><span class="sxs-lookup"><span data-stu-id="f0c19-106">You will have to modify some of the values to point to your J.D.</span></span> <span data-ttu-id="f0c19-107">Servidor de Edwards OneWorld, por ejemplo, el valor establecido en szCMComputerID.</span><span class="sxs-lookup"><span data-stu-id="f0c19-107">Edwards OneWorld server, for example, the value set in szCMComputerID.</span></span>  
  
```  
<ns0:F4211FSBeginDoc xmlns:ns0="http://schemas.microsoft.com/  
   [JDE://CSALES/B4200310]">  
   <ns0:mnCMJobNumber></ns0:mnCMJobNumber>  
   <ns0:cCMDocAction>A</ns0:cCMDocAction>  
   <ns0:cCMProcessEdits>1</ns0:cCMProcessEdits>  
   <ns0:szCMComputerID>BVISION01</ns0:szCMComputerID>  
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
  
## <a name="see-also"></a><span data-ttu-id="f0c19-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0c19-108">See Also</span></span>  
 <span data-ttu-id="f0c19-109">[Paso 1: Hacer referencia al esquema DLL](../core/step-1-reference-the-schema-dll2.md) </span><span class="sxs-lookup"><span data-stu-id="f0c19-109">[Step 1: Reference the Schema DLL](../core/step-1-reference-the-schema-dll2.md) </span></span>  
 <span data-ttu-id="f0c19-110">[Paso 2: Crear la orquestación](../core/step-2-create-the-orchestration1.md) </span><span class="sxs-lookup"><span data-stu-id="f0c19-110">[Step 2: Create the Orchestration](../core/step-2-create-the-orchestration1.md) </span></span>  
 [<span data-ttu-id="f0c19-111">Paso 3: Completar y ejecutar el proyecto</span><span class="sxs-lookup"><span data-stu-id="f0c19-111">Step 3: Complete and Run the Project</span></span>](../core/step-3-complete-and-run-the-project2.md)