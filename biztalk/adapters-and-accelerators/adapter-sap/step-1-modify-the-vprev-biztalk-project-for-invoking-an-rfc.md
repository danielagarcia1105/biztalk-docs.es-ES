---
title: 'Paso 1: Modificar el proyecto de BizTalk vPrev para llamar a una solicitud de cambio | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- migration, modifying previous version of BizTalk project for invoking an RFC
- migration
ms.assetid: 2d4a6cd7-d216-4e0f-8f82-41e044cd325b
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1f967a268d8baca3ab12f29bbac4b9eccc3cd75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-modify-the-vprev-biztalk-project-for-invoking-an-rfc"></a>Paso 1: Modificar el proyecto de BizTalk vPrev para llamar a una solicitud de cambio
![Paso 1 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **Tiempo en completarse:** 10 minutos  
  
 **Objetivo:** en este paso, realice los siguientes cambios en el proyecto de BizTalk vPrev existente:  
  
-   Generar metadatos para la solicitud de cambio de SD_RFC_CUSTOMER_GET mediante basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
-   Asignar el mensaje de solicitud para invocar la solicitud de cambio con un adaptador SAP vPrev a un mensaje de solicitud para invocar la solicitud de cambio con basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
-   Asignar el mensaje de respuesta recibido con basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] al mensaje de respuesta para el adaptador SAP vPrev.  
  
## <a name="prerequisite"></a>Requisito previo  
  
-   Debe tener un proyecto de BizTalk vPrev para invocar la RFC SD_RFC_CUSTOMER_GET en el sistema SAP.  
  
### <a name="to-modify-the-vprev-biztalk-project"></a>Para modificar el proyecto de BizTalk vPrev  
  
1.  Generar metadatos para la solicitud de cambio de SD_RFC_CUSTOMER_GET mediante basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Puede usar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para generar los metadatos.  
  
     Para obtener instrucciones sobre cómo generar metadatos para las solicitudes de cambio, consulte [exploración, búsqueda y obtener metadatos para las operaciones de RFC en SAP](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md). Una vez generado el esquema, un archivo con el nombre similar al *SapBindingSchema.xsd* se agrega al proyecto de BizTalk. Este archivo contiene el esquema para invocar la SD_RFC_CUSTOMER_GET mediante basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
2.  Generar los metadatos para la solicitud de cambio de SD_RFC_CUSTOMER_GET también crea un archivo de enlace de puerto. En el paso siguiente, este archivo de enlace se utilizará para crear un puerto de envío WCF-Custom para enviar mensajes al sistema SAP. La acción SOAP para la operación también se establece en la operación para el que generar metadatos. Por ejemplo, si genera metadatos para la solicitud de cambio de SD_RFC_CUSTOMER_GET, el nombre de la operación en la acción de SOAP en el puerto de envío será "SD_RFC_CUSTOMER_GET". Sin embargo, la operación de nombre en el puerto de envío lógico que se crea como parte de la orquestación podría ser diferente, por ejemplo, "Operation_1". Como resultado, cuando se envían mensajes al sistema SAP mediante el puerto de envío, recibirá un error. Para evitar esto, asegúrese de que el nombre de la operación en la operación lógica puerto en la orquestación es el mismo que el nombre de la operación para el que generar metadatos de envío.  
  
     Por lo tanto, en el caso de este tutorial, dado que generar metadatos para la solicitud de cambio de SD_RFC_CUSTOMER_GET, cambiar el nombre de la operación de puerto de envío lógico a "SD_RFC_CUSTOMER_GET".  
  
3.  Para el mensaje de solicitud, asignar el esquema generado con el adaptador SAP vPrev para el esquema generado mediante basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
    1.  Agregue a un asignador de BizTalk al proyecto de BizTalk. Haga clic en el proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
         En el **Agregar nuevo elemento** cuadro de diálogo, en el panel izquierdo, seleccione **archivos de asignación**. En el panel derecho, seleccione **mapa**. Especifique un nombre para la asignación, como **RequestMap.btm**. Haga clic en **Agregar**.  
  
    2.  En el panel de esquema de origen, haga clic en **Abrir esquema de origen**.  
  
    3.  En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nombre del proyecto, **esquemas**y seleccione el esquema del mensaje de solicitud para el adaptador SAP vPrev. Para este tutorial, seleccione *SAP_Migration.SD_RFC_CUSTOMER_GET__x32003*y, a continuación, haga clic en **Aceptar**.  
  
    4.  En el **nodo raíz para esquema de origen** cuadro de diálogo, seleccione *SD_RFC_CUSTOMER_GET_Request*y, a continuación, haga clic en **Aceptar**.  
  
    5.  En el panel de esquema de destino, haga clic en **Abrir esquema de destino**.  
  
    6.  En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nombre del proyecto, **esquemas**y seleccione el esquema del mensaje de solicitud para basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Para este tutorial, seleccione *SAP_Migration.SapBindingSchema*y, a continuación, haga clic en Aceptar.  
  
    7.  En el **nodo raíz para esquema de destino** cuadro de diálogo, seleccione *SD_RFC_CUSTOMER_GET*y, a continuación, haga clic en **Aceptar**.  
  
         Asignar los elementos correspondientes en los esquemas de ambos tal y como se muestra en la ilustración siguiente. Asignar el elemento CUSTOMER_T mediante un functoid de recorte izquierdo de cadena. Para ello, desde la **cuadro de herramientas**, arrastre el **recorte izquierdo de cadena** functoid y colóquela en la cuadrícula del asignador. Conectar el **CUSTOMER_T** elemento en el esquema de origen hasta el functoid. De forma similar, conecte el **CUSTOMER_T** elemento en el esquema de destino hasta el functoid. La ilustración siguiente muestra cómo se asignan los dos elementos mediante el functoid.  
  
         ![Asignar los mensajes de solicitud entre versiones de adaptador](../../adapters-and-accelerators/adapter-sap/media/f12f280d-766f-4647-bced-435354206fb9.gif "f12f280d-766f-4647-bced-435354206fb9")  
  
        > [!NOTE]
        >  Para obtener más información sobre el functoid de recorte izquierdo de cadena, vea "Functoid de recorte de cadena izquierda" en [http://go.microsoft.com/fwlink/?LinkId=105774](http://go.microsoft.com/fwlink/?LinkId=105774).  
  
    8.  Guarde el mapa.  
  
4.  El mensaje de respuesta, asignar el esquema generado con el adaptador SAP vPrev para el esquema generado mediante basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
    1.  Agregue a un asignador de BizTalk al proyecto de BizTalk. Haga clic en el proyecto de BizTalk, seleccione **agregar**y haga clic en **nuevo elemento**.  
  
         En el **Agregar nuevo elemento** cuadro de diálogo, en el panel izquierdo, seleccione **archivos de asignación**. En el panel derecho, seleccione **mapa**. Especifique un nombre para la asignación, como **ResponseMap.btm**. Haga clic en **Agregar**.  
  
    2.  En el panel de esquema de origen, haga clic en **Abrir esquema de origen**.  
  
    3.  En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nombre del proyecto, **esquemas**y seleccione el esquema para el mensaje de respuesta para basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Para este tutorial, seleccione *SAP_Migration.SapBindingSchema*y, a continuación, haga clic en **Aceptar**.  
  
    4.  En el **nodo raíz para esquema de origen** cuadro de diálogo, seleccione *SD_RFC_CUSTOMER_GETResponse*y, a continuación, haga clic en **Aceptar**.  
  
    5.  En el panel de esquema de destino, haga clic en **Abrir esquema de destino**.  
  
    6.  En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nombre del proyecto, **esquemas**y seleccione el esquema para el mensaje de respuesta para el adaptador SAP vPrev. Para este tutorial, seleccione *SAP_Migration.SD_RFC_CUSTOMER_GET__x32003*y, a continuación, haga clic en **Aceptar**.  
  
    7.  En el **nodo raíz para esquema de destino** cuadro de diálogo, seleccione *SD_RFC_CUSTOMER_GET_Response*y, a continuación, haga clic en **Aceptar**.  
  
    8.  Asignar los elementos correspondientes en los esquemas de ambos tal y como se muestra en la ilustración siguiente.  
  
         ![Asignar los mensajes de respuesta entre versiones de adaptador](../../adapters-and-accelerators/adapter-sap/media/d8dddaba-d978-4159-bcc6-6a6bfee36564.gif "d8dddaba-d978-4159-bcc6-6a6bfee36564")  
  
    9. Guarde el mapa.  
  
5.  Guarde y compile la solución de BizTalk. Haga clic en la solución y, a continuación, haga clic en **generar solución**.  
  
6.  Implementar la solución. Haga clic en la solución y, a continuación, haga clic en **implementar solución**.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Crear un puerto de envío WCF-Custom y configúrelo para utilizar las asignaciones creadas en este paso, como se describe en [paso 2: configurar la orquestación en la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-sap/step-2-configure-the-orchestration-in-biztalk-server-administration-console1.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 2: Migrar un proyecto de BizTalk RFC de SAP](../../adapters-and-accelerators/adapter-sap/tutorial-2-migrating-an-sap-rfc-biztalk-project.md)