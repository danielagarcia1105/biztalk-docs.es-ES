---
title: 'Paso 3: Probar el Application6 migrados | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migration, testing the migrated application (RFC)
- migration
ms.assetid: 1b1ee59c-a5a3-442d-af2c-0fc4817f3063
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2116888c3e56128b7e474e1370930a39e94a93a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006916"
---
# <a name="step-3-test-the-migrated-application"></a>Paso 3: Probar la aplicación migrada
![Paso 3 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **Tiempo en completarse:** 5 minutos  
  
 **Objetivo:** en este paso, probará la aplicación migrada mediante la invocación de la RFC SD_RFC_CUSTOMER_GET. Para ello, coloque un mensaje de solicitud que se ajusta al esquema generado con el adaptador de SAP vPrev.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
- Configurar la aplicación de BizTalk mediante la asignación de los puertos lógicos de la orquestación de BizTalk a puertos físicos en la consola de administración de BizTalk Server.  
  
- Configurar la aplicación de BizTalk para utilizar el puerto de envío WCF-Custom basado en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
### <a name="to-test-the-migrated-application"></a>Para probar la aplicación migrada  
  
1. En la carpeta SAP_RFC_Migration, copie el mensaje de solicitud Input.xml. Este mensaje de solicitud cumple el esquema generado por el adaptador de SAP vPrev. Mediante la asignación de salida, el WCF-Custom enviar puerto convierte esto para ajustarse al esquema basado en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] y lo envía al sistema SAP.  
  
   ```  
   <ns0:SD_RFC_CUSTOMER_GET_Request xmlns:ns0="http://schemas.microsoft.com/BizTalk/2003">  
     <KUNNR>0000001390</KUNNR>  
     <NAME1/>  
     <CUSTOMER_T/>  
   </ns0:SD_RFC_CUSTOMER_GET_Request>  
   ```  
  
2. Pegar el mensaje de solicitud a la carpeta que se asigna al archivo de la ubicación de recepción.  
  
3. La orquestación consume el mensaje de solicitud y lo envía al sistema SAP. Se recibe la respuesta desde el sistema SAP en el esquema que se ajusta con el esquema de basada en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Mediante la asignación de entrada, el WCF-Custom enviar puerto convierte esto al esquema para el adaptador SAP vPrev. La respuesta desde el sistema SAP se guarda en la otra ubicación de archivo definida como parte de la orquestación. La respuesta para el mensaje de solicitud anterior es:  
  
   ```  
   <?xml version="1.0" encoding="utf-8" ?>   
   <ns0:SD_RFC_CUSTOMER_GET_Response xmlns:ns0="http://schemas.microsoft.com/BizTalk/2003">  
     <CUSTOMER_T>  
       <KUNNR>0000001390</KUNNR>   
       <ANRED>Firma</ANRED>   
       <NAME1>Contoso, Ltd.</NAME1>   
       <PFACH />   
       <STRAS>Strasse 4567</STRAS>   
       <PSTLZ>50000</PSTLZ>   
       <ORT01>Aachen</ORT01>   
       <TELF1>0123-45678</TELF1>   
       <TELFX>0123-56789</TELFX>   
     </CUSTOMER_T>  
   </ns0:SD_RFC_CUSTOMER_GET_Response>  
   ```  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 2: Migración de un proyecto de BizTalk RFC de SAP](../../adapters-and-accelerators/adapter-sap/tutorial-2-migrating-an-sap-rfc-biztalk-project.md)