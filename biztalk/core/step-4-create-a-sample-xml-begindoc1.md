---
title: 'Paso 4: Crear un BeginDoc1 XML de ejemplo | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e494b4b2-4c83-4293-8ae8-acae29018e7f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a48a4ee378560ad2d0360445e3fb732bb46e79f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276732"
---
# <a name="step-4-create-a-sample-xml-begindoc"></a>Paso 4: Crear un XML de ejemplo de BeginDoc
Guarde lo siguiente en un archivo XML. Si su prueba sigue los pasos de este ejemplo y usa la selección de objetos J.D. Edwars EnterpriseOne del ejemplo, Selección de objetos de Edwards OneWorld, [JDE://CSALES/B4200310], podrá colocarlo en la carpeta de entrada y lo que salió de la carpeta Out designada (la carpeta enlazada al puerto EndDocOut).  
  
> [!NOTE]
>  Tendrá que modificar algunos de los valores para que señalen a su servidor J.D. Servidor de Edwards OneWorld, por ejemplo, el valor establecido en szCMComputerID.  
  
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
  
## <a name="see-also"></a>Vea también  
 [Paso 1: Hacer referencia al esquema DLL](../core/step-1-reference-the-schema-dll2.md)   
 [Paso 2: Crear la orquestación](../core/step-2-create-the-orchestration1.md)   
 [Paso 3: Completar y ejecutar el proyecto](../core/step-3-complete-and-run-the-project2.md)