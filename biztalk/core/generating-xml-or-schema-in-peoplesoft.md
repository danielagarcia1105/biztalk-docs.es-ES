---
title: Generar XML o esquema en PeopleSoft | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- generating schemas
- schemas, generating
- generating XML
- XML, generating
ms.assetid: adfe2936-0dc2-42d2-b26a-718f8cc57eff
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fadd89a1e929d672f1b2c8839248d5d03cb27d1c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005637"
---
# <a name="generating-xml-or-schema-in-peoplesoft"></a>Generación de XML o esquema en PeopleSoft
En el procedimiento siguiente se describe cómo usar PeopleSoft Enterprise para crear un archivo XML y desencadenar un evento de PeopleSoft. Para ello, se debe realizar un cambio en el entorno de PeopleSoft. El cambio activa el archivo XML, que se envía a la carpeta de archivos que estableció en la orquestación que se va a supervisar. Después, en BizTalk Server, se importa el XML y se genera un esquema.  
  
> [!NOTE]
>  Cuando se asocia la ubicación al nodo MSEXTERNAL, cualquier cambio realizado en el valor de ubicación genera un documento XML, lo que desencadena un evento. Después de dar de alta e iniciar la orquestación, puede navegar por las pantallas de PeopleSoft hasta la pantalla LOCATION. Si realiza un cambio para el valor de ubicación y lo guarda, aparece un XML correspondiente en el directorio \out.  
  
### <a name="to-generate-xml-or-schema-in-peoplesoft"></a>Para generar XML o esquemas en PeopleSoft  
  
1. En la aplicación PeopleSoft, apunte a **configurar operaciones financieras**, apunte a **Supply Chain**, apunte a **definiciones comunes**, apunte a **ubicación**y, a continuación, seleccione **ubicación**.  
  
2. En el **ubicación** pantalla, escriba la siguiente información:  
  
   - **Id. de conjunto:** escriba **SHARE**.  
  
   - **Código ubicación:** escriba un código que comienza con `WKLOC`.  
  
     ![](../core/media/psadapter-18-task-sharesearch.gif "PSAdapter_18_Task_ShareSearch")  
  
3. Haga clic en **búsqueda**y, a continuación, haga clic en **corregir historial** para colocar la pantalla **editar** modo.  
  
    ![](../core/media/psadapter-19-task-correcthistory.gif "PSAdapter_19_Task_CorrectHistory")  
  
4. Realice un cambio en un campo en la pantalla y, a continuación, haga clic en **guardar**.  
  
5. Seleccione **PeopleTools**, apunte a **Integration Broker**, apunte a **Monitor**y, a continuación, seleccione **Monitor Message**.  
  
    ![](../core/media/psadapter-20-task-monitormessage.gif "PSAdapter_20_Task_MonitorMessage")  
  
6. Asegúrese de que **tipo de canal** es **instancia de mensaje**y, a continuación, haga clic en **actualizar**.  
  
7. En el **realiza** columna, haga clic en el número.  
  
8. Desplácese hasta la parte inferior de la lista y haga clic en el **detalles** vincular en un **LOCATION_SYNC** mensaje.  
  
    ![](../core/media/psadapter-21-task-detailslink.gif "PSAdapter_21_Task_DetailsLink")  
  
9. Haga clic en **ver XML** en un **MSEXTERNAL** nodo.  
  
     ![](../core/media/psadapter-22-task-viewxml.gif "PSAdapter_22_Task_ViewXML")  
  
     Copie y pegue el contenido del XML en un archivo al que pueda obtener acceso el proyecto de BizTalk Server.  
  
     ![](../core/media/psadapter-23-task-xmlresult.gif "PSAdapter_23_Task_XMLResult")  
  
10. Recuerde la ubicación del archivo al que hace referencia en BizTalk Server.  
  
## <a name="see-also"></a>Vea también  
 [Apéndice B: Uso de la aplicación PeopleSoft](../core/appendix-b-using-the-peoplesoft-application.md)