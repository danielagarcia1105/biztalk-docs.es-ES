---
title: 'Paso 2: Configurar un unidireccionales de WCF-Custom puerto de recepción | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-Custom one-way receive port, configuring
- migration
ms.assetid: e2a8f074-64d5-4e6c-84d0-318fb606c0ba
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6edf75f08bdf6a321188e484eb4f363366f8eb95
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218556"
---
# <a name="step-2-configure-a-wcf-custom-one-way-receive-port"></a>Paso 2: Configurar un unidireccionales de WCF-Custom puerto de recepción
![Paso 2 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **Tiempo en completarse:** 10 minutos  
  
 **Objetivo:** en este paso, configurará un puerto personalizado de WCF para recibir un IDOC de archivo sin formato de un sistema SAP. Después de configurar el puerto, configurar BizTalk puerto de recepción de la aplicación para que use WCF-Custom.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe ha creado e implementado el proyecto de BizTalk vPrev para recibir IDOC desde un sistema SAP.  
  
### <a name="to-configure-a-wcf-custom-one-way-receive-port"></a>Para configurar el puerto de recepción de un unidireccionales de WCF-Custom  
  
1.  Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2.  En el árbol de consola, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
3.  Expanda la aplicación en la que desea crear el puerto de recepción.  
  
4.  Haga clic en **puertos de recepción**, seleccione **New**y haga clic en **puerto de recepción unidireccional**.  
  
5.  En el **propiedades de puerto de recepción** cuadro de diálogo, en la **General** ficha, escriba un nombre para el puerto de recepción.  
  
6.  En el **ubicaciones de recepción** , haga clic en **nuevo**. El **propiedades de la ubicación de recepción** aparece el cuadro de diálogo.  
  
7.  En el **propiedades de la ubicación de recepción** diálogo cuadro, realice lo siguiente:  
  
    1.  Especifique un nombre para la ubicación de recepción.  
  
    2.  Desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.  
  
8.  En el **propiedades de transporte de WCF-Custom** diálogo cuadro, realice lo siguiente:  
  
    1.  Haga clic en el **General** ficha y en el **dirección (URI)** campo, especifique el URI de conexión para recibir mensajes desde el sistema SAP. El URI para recibir mensajes desde el sistema SAP de conexión debe estar en el formato siguiente:  
  
        ```  
        sap://Client=800;lang=EN@A/YourSAPHOST/00?ListenerGwHost=YourSAPHOST&ListenerGwServ=SAPGW00&ListenerProgramId=MyProgramId  
        ```  
  
         En la siguiente ilustración muestra el cuadro de diálogo de propiedades de puerto con el URI especificado:  
  
         ![URI de conexión para recibir mensajes de SAP](../../adapters-and-accelerators/adapter-sap/media/91e12582-aea3-4f13-8cdc-af69a9a11a5c.gif "91e12582-aea3-4f13-8cdc-af69a9a11a5c")  
  
         Para obtener más información sobre el URI de conexión, consulte [crear una conexión con el sistema SAP](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md).  
  
    2.  Haga clic en el **enlace** ficha y desde el **BindingType** lista desplegable, seleccione **sapBinding**. Asegúrese de que especificar las siguientes propiedades de enlace para el puerto de recepción.  
  
        |Propiedad de enlace|Establezca el valor a|  
        |----------------------|------------------|  
        |flatFileSegmentIndicator|**SegmentType**. Esto indica que los archivos planos deben contener el tipo de segmento de cada segmento en el IDOC.|  
        |padReceivedIdocWithSpaces|**True**. Especifica si cada línea en el IDOC se rellena con espacios hasta la longitud correcta.|  
        |receiveIDocFormat|**Cadena**. Esto especifica que el mensaje IDOC debe representarse como un campo de cadena único.|  
  
         Para obtener más información acerca de las propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para mySAP Business Suite enlace propiedades](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
    3.  Haga clic en el **otros** ficha y especifique las credenciales para conectarse a un sistema SAP.  
  
    4.  Haga clic en el **mensajes** ficha y en el **cuerpo del mensaje entrante de BizTalk** sección, elija el **ruta de acceso** opción.  
  
    5.  En el **expresión de ruta de acceso del cuerpo** texto, especifique la consulta XPath para extraer el IDOC de archivo sin formato del mensaje XML. Al hacerlo, el puerto de recepción extrae los datos de lo IDOC y recorta la etiqueta XML que forma parte de la **ReceiveIdoc** operación para basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Para obtener más información acerca del esquema de mensaje para la **ReceiveIdoc** operación, vea [esquemas de mensaje para las operaciones de IDOC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md).  
  
         ![XPath de consulta para extraer el plano &#45; IDOC de archivo](../../adapters-and-accelerators/adapter-sap/media/8b5b8165-a1e7-40ef-bcf7-de3149c6deb0.gif "8b5b8165-a1e7-40ef-bcf7-de3149c6deb0")  
  
         Debe especificar la consulta XPath siguiente:  
  
        ```  
        /*[local-name()='ReceiveIdoc']/*[local-name()='idocData']  
        ```  
  
    6.  Desde el **codificación de nodo** lista desplegable, seleccione **cadena**.  
  
    7.  Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.  
  
9. En el cuadro de diálogo Propiedades de la ubicación de recepción, de la **controlador de recepción** lista desplegable, seleccione **BizTalkServerApplication**.  
  
10. Desde el **canalización de recepción** lista desplegable, seleccione **ConvertToXML**. Esta canalización de desensamblador de archivos sin formato ya es una parte del proyecto de BizTalk vPrev para convertir un IDOC de archivo sin formato en un IDOC XML.  
  
11. Haga clic en **Aceptar**.  
  
### <a name="to-configure-the-biztalk-application"></a>Para configurar la aplicación de BizTalk  
  
1.  En la consola de administración de BizTalk Server, expanda **grupo de BizTalk**, expanda **aplicaciones**y expanda la aplicación de BizTalk donde se implementa la orquestación.  
  
2.  Haga clic en la aplicación de BizTalk y, a continuación, seleccione **configurar**.  
  
3.  En el panel izquierdo, haga clic en la orquestación que se va a configurar. En el panel derecho, desde el **Host** lista desplegable, seleccione una instancia de host de BizTalk.  
  
4.  En el **enlaces** cuadro, asigne los puertos lógicos de la orquestación de BizTalk a los puertos físicos en la consola de administración de BizTalk Server.  
  
    1.  Seleccione el WCF-Custom recibir puerto creado anteriormente en este tema.  
  
    2.  Seleccione un puerto de archivos donde recibirá el IDOC de archivo sin formato.  
  
    3.  Haga clic en **Aceptar**.  
  
     Para obtener más información acerca de cómo configurar una aplicación, consulte [http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360).  
  
## <a name="next-steps"></a>Pasos siguientes  
 Ahora ha completado la migración de su proyecto de BizTalk vPrev a un proyecto de BizTalk que recibe los IDOC desde un sistema SAP mediante basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Ahora debe probar la aplicación migrada de BizTalk mediante la recepción de un IDOC de archivo sin formato, como se describe en [paso 3: probar la aplicación migran](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application5.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 4: Migrar una SAP recibir IDOC proyecto de BizTalk](../../adapters-and-accelerators/adapter-sap/tutorial-4-migrating-an-sap-receive-idoc-biztalk-project.md)