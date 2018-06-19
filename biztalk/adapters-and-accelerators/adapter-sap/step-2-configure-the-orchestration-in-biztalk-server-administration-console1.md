---
title: 'Paso 2: Configurar la orquestación en BizTalk Server Administration Consola1 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestration, configruing in BizTalk Server Administration console
- WCF-Custom port, creating
- migration
ms.assetid: fb057bce-5702-4ea0-8ed5-e299d3a78a11
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1783e56891ffd6d5d27058eab1df8a60663f481b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217716"
---
# <a name="step-2-configure-the-orchestration-in-biztalk-server-administration-console"></a>Paso 2: Configurar la orquestación en la consola de administración de BizTalk Server
![Paso 2 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **Tiempo en completarse:** 10 minutos  
  
 **Objetivo:** en este paso, realizará las tareas siguientes:  
  
-   Crear un WCF-Custom envío y recepción de puerto para enviar y recibir mensajes desde el sistema SAP mediante el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Configurar este puerto para utilizar las asignaciones que creó en el paso anterior.  
  
-   Configurar la orquestación implementada en el último paso para usar el puerto WCF-Custom.  
  
## <a name="prerequisite"></a>Requisito previo  
  
-   Implementar la orquestación de BizTalk para el que desea configurar el puerto de WCF-Custom.  
  
### <a name="to-create-a-wcf-custom-port"></a>Para crear un puerto de WCF-Custom  
  
1.  Al generar el esquema para un RFC mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], un archivo de enlace también se agrega al proyecto de BizTalk. Puede importar este archivo de enlace en el BizTalk aplicación para crear un WCF-Custom envío y recepción de puerto. Para obtener instrucciones sobre cómo importar un archivo de enlace, consulte [importar enlaces](http://msdn.microsoft.com/library/c927efde-29bd-4efe-9da5-942e7da65dbf).  
  
2.  Después de importar el archivo de enlace, se crea un puerto de envío en el **puertos de envío** carpeta en la consola de administración de BizTalk Server.  
  
3.  Haga clic en el puerto personalizado de WCF y, a continuación, haga clic en **propiedades**.  
  
4.  En el panel izquierdo del cuadro de diálogo de propiedades de puerto de envío, haga clic en el **General** ficha. En el panel derecho, haga clic en **configurar**.  
  
5.  En el **propiedades de transporte de WCF-Custom** cuadro de diálogo, haga clic en el **credenciales** ficha y especifique las credenciales para conectarse a un sistema SAP.  
  
6.  Haga clic en **Aceptar**.  
  
7.  En el panel izquierdo del cuadro de diálogo de propiedades de puerto de envío, haga clic en **asignaciones de entrada**. En el panel derecho, haga clic en el campo en el **mapa** columna y en la lista desplegable, seleccione **ResponseMap**.  
  
     ![Configurar la asignación de entrada en el puerto WCF personalizado](../../adapters-and-accelerators/adapter-sap/media/10129a7d-211b-464b-b05a-b3ea72f46873.gif "10129a7d-211b-464b-b05a-b3ea72f46873")  
  
8.  En el panel izquierdo del cuadro de diálogo de propiedades de puerto de envío, haga clic en **asignaciones de salida.** En el panel derecho, haga clic en el campo en el **mapa** columna y en la lista desplegable, seleccione **RequestMap**.  
  
     ![Configurar la asignación de salida en el puerto WCF personalizado](../../adapters-and-accelerators/adapter-sap/media/4ffcb4cd-4f53-4b67-92e2-3225d15d97ee.gif "4ffcb4cd-4f53-4b67-92e2-3225d15d97ee")  
  
9. Haga clic en **Aceptar**.  
  
### <a name="to-configure-the-biztalk-application"></a>Para configurar la aplicación de BizTalk  
  
1.  En la consola de administración de BizTalk Server, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda la aplicación de BizTalk donde se implementa la orquestación.  
  
2.  Haga clic en la aplicación de BizTalk y, a continuación, seleccione **configurar**.  
  
3.  En el panel izquierdo, haga clic en la orquestación que se va a configurar. En el panel derecho, desde el **Host** lista desplegable, seleccione una instancia de host de BizTalk.  
  
4.  En el **enlaces** cuadro, asigne los puertos lógicos de la orquestación de BizTalk a los puertos físicos en la consola de administración de BizTalk Server.  
  
    1.  Seleccione el puerto de archivo donde se colocará un mensaje de solicitud. La orquestación de BizTalk consumirá el mensaje de solicitud y enviar al sistema SAP.  
  
    2.  Seleccione el puerto de archivo donde la orquestación de BizTalk quitará el mensaje de respuesta que contiene la respuesta desde el sistema SAP.  
  
    3.  Seleccione el puerto de envío WCF-custom que creó anteriormente en este tema.  
  
    4.  Haga clic en **Aceptar**.  
  
     Para obtener más información acerca de cómo configurar una aplicación, consulte "Cómo configurar una aplicación" en [http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360).  
  
## <a name="next-steps"></a>Pasos siguientes  
 Ahora ha completado la migración de su proyecto de BizTalk vPrev a un proyecto de BizTalk que envía mensajes al sistema SAP mediante basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. A continuación, debe probar la aplicación migrada de BizTalk mediante el envío de un mensaje de solicitud para invocar la RFC SD_RFC_CUSTOMER_GET, como se describe en [paso 3: probar la aplicación migran](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application6.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 2: Migrar un proyecto de BizTalk RFC de SAP](../../adapters-and-accelerators/adapter-sap/tutorial-2-migrating-an-sap-rfc-biztalk-project.md)