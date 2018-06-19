---
title: 'Paso 2: Configurar un puerto de envío unidireccional de WCF-Custom | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-Custom one-way send port, configuring
- migration
ms.assetid: ae13222e-42e7-45a7-9b2a-0a6779b21736
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8aab14799076d3f774130b357ab90c5ed5335f4a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962794"
---
# <a name="step-2-configure-a-wcf-custom-one-way-send-port"></a>Paso 2: Configurar un puerto de envío unidireccional de WCF-Custom
![Paso 2 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **Tiempo en completarse:** 10 minutos  
  
 **Objetivo:** en este paso, configurará un puerto personalizado de WCF para enviar el IDOC de archivo sin formato a un sistema SAP. Después de configurar el puerto, configure la aplicación de BizTalk para utilizar el puerto de envío WCF-Custom.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe ha creado e implementado el proyecto de BizTalk vPrev para enviar los IDOC a un sistema SAP.  
  
### <a name="to-configure-a-wcf-custom-one-way-send-port"></a>Para configurar un puerto de envío unidireccional de WCF-Custom  
  
1.  Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2.  En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
3.  Expanda la aplicación en la que desea crear el puerto de envío.  
  
4.  Haga clic en **puertos de envío**, seleccione **New**y haga clic en **puerto de envío unidireccional estático**.  
  
5.  En el **propiedades de puerto de envío** cuadro de diálogo, en la **General** ficha, escriba un nombre para el puerto de envío.  
  
6.  Desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.  
  
7.  En el **propiedades de transporte de WCF-Custom** diálogo cuadro, realice lo siguiente:  
  
    1.  Haga clic en el **General** ficha y en el **dirección (URI)** campo, especifique el URI de conexión para enviar mensajes al sistema SAP. Para obtener más información sobre el URI de conexión, consulte [cree el URI de conexión del sistema SAP](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).  
  
         ![URI de conexión especificado en el puerto de envío](../../adapters-and-accelerators/adapter-sap/media/53ae71e1-89ec-49c5-8096-ff04a2c94c0a.gif "53ae71e1-89ec-49c5-8096-ff04a2c94c0a")  
  
    2.  En el **General** ficha la **acción** texto, escriba la acción para la operación. Para enviar un IDOC de archivo sin formato, debe usar el **SendIdoc** operación expuesta por basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. **SendIdoc** operación permite a los clientes de adaptador enviar los IDOC que tengan un esquema débilmente tipada. Para obtener más información, consulte [operaciones en IDOC en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md). La siguiente ilustración muestra la **acción** cuadro de texto con la acción para el **SendIdoc** operación.  
  
         ![Especificar la acción en el puerto de envío](../../adapters-and-accelerators/adapter-sap/media/94dd1505-5529-43cf-a27b-2588a022dfb9.gif "94dd1505-5529-43cf-a27b-2588a022dfb9")  
  
    3.  Haga clic en el **enlace** ficha y desde el **BindingType** lista desplegable, seleccione **sapBinding**.  
  
    4.  Haga clic en el **credenciales** ficha y especifique las credenciales para conectarse a un sistema SAP.  
  
    5.  Haga clic en el **mensajes** ficha y en el **cuerpo del mensaje saliente de WCF** sección, elija el **plantilla** opción.  
  
    6.  En el **XML** texto, especifique la plantilla que se usará para construir el mensaje WCF. Al hacerlo, cree un mensaje que se ajusta a la **SendIdoc** operación para basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Para obtener más información acerca de la estructura del mensaje para la **SendIdoc** operación, vea [esquemas de mensaje para las operaciones de IDOC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md).  
  
         ![Especificar plantilla para mensaje WCF saliente](../../adapters-and-accelerators/adapter-sap/media/909835c3-a941-49dc-87f0-858fe0e1fc63.gif "909835c3-a941-49dc-87f0-858fe0e1fc63")  
  
         Para la operación SendIdoc, debe especificar la siguiente plantilla:  
  
        ```  
        <SendIdoc xmlns="http://Microsoft.LobServices.Sap/2007/03/Idoc/">  
        <idocData><bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="string"/></idocData>  
        </SendIdoc>  
        ```  
  
         En la plantilla anterior, el `bts-msg-body` es puerto de recepción de XML IDOC que se crea utilizando el Desensamblador de archivos sin formato asociado al archivo. El XML IDOC se encapsula en el mensaje SendIdoc.  
  
    7.  Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.  
  
8.  En el **propiedades de puerto de envío** cuadro de diálogo, desde el **controlador de envío** lista desplegable, seleccione **BizTalkServerApplication**.  
  
9. Desde el **canalización de envío** lista desplegable, seleccione **ConvertToFlatFile**. Esta canalización de ensamblador de archivo sin formato ya forma parte del proyecto de BizTalk vPrev y se utiliza para convertir un IDOC XML en un IDOC de archivo sin formato.  
  
10. Haga clic en **Aceptar**.  
  
### <a name="to-configure-the-biztalk-application"></a>Para configurar la aplicación de BizTalk  
  
1.  En la consola de administración de BizTalk Server, expanda **grupo de BizTalk**, expanda **aplicaciones**y expanda la aplicación de BizTalk donde se implementa la orquestación.  
  
2.  Haga clic en la aplicación de BizTalk y, a continuación, seleccione **configurar**.  
  
3.  En el panel izquierdo, haga clic en la orquestación que se va a configurar. En el panel derecho, desde el **Host** lista desplegable, seleccione una instancia de host de BizTalk.  
  
4.  En el **enlaces** cuadro, asigne los puertos lógicos de la orquestación de BizTalk a los puertos físicos en la consola de administración de BizTalk Server.  
  
    1.  Seleccione el puerto de archivo donde se colocará el IDOC de archivo sin formato.  
  
    2.  Seleccione el puerto de envío WCF-Custom que creó anteriormente en este tema.  
  
    3.  Haga clic en **Aceptar**.  
  
     Para obtener más información acerca de cómo configurar una aplicación, consulte "Cómo configurar una aplicación" en [http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360).  
  
## <a name="next-steps"></a>Pasos siguientes  
 Ahora ha completado la migración de su proyecto de BizTalk vPrev a un proyecto de BizTalk que envía el IDOC a un sistema SAP mediante basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Ahora debe probar la aplicación migrada de BizTalk mediante el envío de un IDOC de archivo sin formato, como se describe en [paso 3: probar la aplicación migran](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application2.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 3: Migración de un proyecto de BizTalk SAP IDOC de envío](../../adapters-and-accelerators/adapter-sap/tutorial-3-migrating-an-sap-send-idoc-biztalk-project.md)