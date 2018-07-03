---
title: 'Paso 1: Modificar el proyecto vPrev de BizTalk para invocar una RFC | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migration, modifying previous version of BizTalk project for invoking an RFC
- migration
ms.assetid: 2d4a6cd7-d216-4e0f-8f82-41e044cd325b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e2624ede6d2710db2d82311c2f452f8be372aa2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969653"
---
# <a name="step-1-modify-the-vprev-biztalk-project-for-invoking-an-rfc"></a>Paso 1: Modificar el proyecto vPrev de BizTalk para invocar una RFC
![Paso 1 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **Tiempo en completarse:** 10 minutos  
  
 **Objetivo:** en este paso, realice los siguientes cambios en el proyecto de BizTalk vPrev existente:  
  
- Generar metadatos para RFC SD_RFC_CUSTOMER_GET mediante basada en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
- Asignar el mensaje de solicitud para invocar la solicitud de cambio con un adaptador SAP vPrev para un mensaje de solicitud para invocar la solicitud de cambio con el basado en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
- Asignar el mensaje de respuesta recibido con el basado en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] al mensaje de respuesta para el adaptador SAP vPrev.  
  
## <a name="prerequisite"></a>Requisito previo  
  
-   Debe tener un proyecto de BizTalk vPrev para invocar la RFC SD_RFC_CUSTOMER_GET en el sistema SAP.  
  
### <a name="to-modify-the-vprev-biztalk-project"></a>Para modificar el proyecto vPrev de BizTalk  
  
1. Generar metadatos para RFC SD_RFC_CUSTOMER_GET mediante basada en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Puede usar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para generar los metadatos.  
  
    Para obtener instrucciones sobre cómo generar metadatos para RFC, consulte [examinar, buscar y obtener metadatos para operaciones de RFC de SAP](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md). Una vez generado el esquema, un archivo con el nombre similar a *SapBindingSchema.xsd* se agrega al proyecto de BizTalk. Este archivo contiene el esquema para invocar el SD_RFC_CUSTOMER_GET mediante basada en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
2. Generar los metadatos para la solicitud de cambio SD_RFC_CUSTOMER_GET también crea un archivo de enlace de puerto. En el paso siguiente, se usará este archivo de enlace para crear un puerto de envío WCF-Custom para enviar mensajes al sistema SAP. También se establece la acción SOAP para la operación a la operación para el que genera los metadatos. Por ejemplo, si genera los metadatos para la solicitud de cambio SD_RFC_CUSTOMER_GET, el nombre de la operación en la acción de SOAP en el puerto de envío será "SD_RFC_CUSTOMER_GET". Sin embargo, la operación de nombre en el puerto de envío lógico que cree como parte de la orquestación podría ser diferente, por ejemplo, "Operation_1". Como resultado, al enviar mensajes al sistema SAP mediante el puerto de envío, obtendrá un error. Para evitarlo, asegúrese de que el nombre de la operación en la operación lógica puerto de envío en la orquestación está el mismo que el nombre de la operación para el que genera los metadatos.  
  
    Por lo tanto, en el caso de este tutorial, dado que generan los metadatos para la solicitud de cambio SD_RFC_CUSTOMER_GET, cambie el nombre de la operación de puerto de envío lógico a "SD_RFC_CUSTOMER_GET".  
  
3. Para el mensaje de solicitud, asignar el esquema generado con el adaptador SAP vPrev para el esquema generado con el basado en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
   1. Agregue a un asignador de BizTalk para el proyecto de BizTalk. Haga clic en el proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
       En el **Agregar nuevo elemento** cuadro de diálogo, en el panel izquierdo, seleccione **archivos de asignación**. En el panel derecho, seleccione **mapa**. Especifique un nombre para la asignación, como **RequestMap.btm**. Haga clic en **Agregar**.  
  
   2. En el panel Esquema de origen, haga clic en **Abrir esquema de origen**.  
  
   3. En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nombre del proyecto, **esquemas**y seleccione el esquema del mensaje de solicitud para el adaptador SAP vPrev. Para este tutorial, seleccione *SAP_Migration.SD_RFC_CUSTOMER_GET__x32003*y, a continuación, haga clic en **Aceptar**.  
  
   4. En el **nodo raíz para esquema de origen** cuadro de diálogo, seleccione *SD_RFC_CUSTOMER_GET_Request*y, a continuación, haga clic en **Aceptar**.  
  
   5. En el panel Esquema de destino, haga clic en **Abrir esquema de destino**.  
  
   6. En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nombre del proyecto, **esquemas**y seleccione el esquema del mensaje de solicitud basado en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Para este tutorial, seleccione *SAP_Migration.SapBindingSchema*y, a continuación, haga clic en Aceptar.  
  
   7. En el **nodo raíz para esquema de destino** cuadro de diálogo, seleccione *SD_RFC_CUSTOMER_GET*y, a continuación, haga clic en **Aceptar**.  
  
       Asignar los elementos correspondientes en los esquemas como se muestra en la ilustración siguiente. Asignar el elemento CUSTOMER_T mediante un functoid de recorte izquierdo de cadena. Para ello, en el **cuadro de herramientas**, arrastre el **recorte izquierdo de cadena** functoid y colóquela en la cuadrícula del asignador. Conectar el **CUSTOMER_T** elemento del esquema de origen hasta el functoid. De forma similar, conecte el **CUSTOMER_T** elemento del esquema de destino hasta el functoid. La ilustración siguiente muestra cómo se asignan los dos elementos mediante el functoid.  
  
       ![Asignar los mensajes de solicitud entre versiones de adaptador](../../adapters-and-accelerators/adapter-sap/media/f12f280d-766f-4647-bced-435354206fb9.gif "f12f280d-766f-4647-bced-435354206fb9")  
  
      > [!NOTE]
      >  Para obtener más información sobre el functoid de recorte izquierdo de cadena, vea "Functoid de recorte de cadena izquierda" en [ http://go.microsoft.com/fwlink/?LinkId=105774 ](http://go.microsoft.com/fwlink/?LinkId=105774).  
  
   8. Guarde el mapa.  
  
4. Para el mensaje de respuesta, asignar el esquema generado con el adaptador SAP vPrev para el esquema generado con el basado en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
   1. Agregue a un asignador de BizTalk para el proyecto de BizTalk. Haga clic en el proyecto de BizTalk, seleccione **agregar**y haga clic en **nuevo elemento**.  
  
       En el **Agregar nuevo elemento** cuadro de diálogo, en el panel izquierdo, seleccione **archivos de asignación**. En el panel derecho, seleccione **mapa**. Especifique un nombre para la asignación, como **ResponseMap.btm**. Haga clic en **Agregar**.  
  
   2. En el panel Esquema de origen, haga clic en **Abrir esquema de origen**.  
  
   3. En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nombre del proyecto, **esquemas**y seleccione el esquema para el mensaje de respuesta basado en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Para este tutorial, seleccione *SAP_Migration.SapBindingSchema*y, a continuación, haga clic en **Aceptar**.  
  
   4. En el **nodo raíz para esquema de origen** cuadro de diálogo, seleccione *SD_RFC_CUSTOMER_GETResponse*y, a continuación, haga clic en **Aceptar**.  
  
   5. En el panel Esquema de destino, haga clic en **Abrir esquema de destino**.  
  
   6. En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nombre del proyecto, **esquemas**y seleccione el esquema para el mensaje de respuesta para el adaptador SAP vPrev. Para este tutorial, seleccione *SAP_Migration.SD_RFC_CUSTOMER_GET__x32003*y, a continuación, haga clic en **Aceptar**.  
  
   7. En el **nodo raíz para esquema de destino** cuadro de diálogo, seleccione *SD_RFC_CUSTOMER_GET_Response*y, a continuación, haga clic en **Aceptar**.  
  
   8. Asignar los elementos correspondientes en los esquemas como se muestra en la ilustración siguiente.  
  
       ![Asignar los mensajes de respuesta entre versiones de adaptador](../../adapters-and-accelerators/adapter-sap/media/d8dddaba-d978-4159-bcc6-6a6bfee36564.gif "d8dddaba-d978-4159-bcc6-6a6bfee36564")  
  
   9. Guarde el mapa.  
  
5. Guarde y compile la solución de BizTalk. Haga clic en la solución y, a continuación, haga clic en **compilar solución**.  
  
6. Implementar la solución. Haga clic en la solución y, a continuación, haga clic en **implementar solución**.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Crear un puerto de envío WCF-Custom y configurarlo para usar las asignaciones que creó en este paso, como se describe en [paso 2: configurar la orquestación en la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-sap/step-2-configure-the-orchestration-in-biztalk-server-administration-console1.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 2: Migración de un proyecto de BizTalk RFC de SAP](../../adapters-and-accelerators/adapter-sap/tutorial-2-migrating-an-sap-rfc-biztalk-project.md)