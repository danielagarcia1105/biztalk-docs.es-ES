---
title: Cómo configurar puertos de envío mediante Windows Sharepoint Services propiedades de contexto | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services adapters, InfoPath forms
- configuring [Windows SharePoint Services adapters], InfoPath forms
- Windows SharePoint Services adapters, Windows SharePoint Services
- InfoPath forms, Windows SharePoint Services adapters
- configuring [Windows SharePoint Services adapters], Windows SharePoint Services
- Windows SharePoint Services adapters, send ports
- configuring [Windows SharePoint Services adapters], send ports
- send ports, Windows SharePoint Services adapters
- Windows SharePoint Services, Windows SharePoint Services adapters
ms.assetid: 1ff50fb8-7ba0-47b8-9476-d57413989346
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e766272f33bf23166ba412a76498e4240ab3343b
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
ms.locfileid: "25970674"
---
# <a name="how-to-configure-send-ports-using-windows-sharepoint-services-context-properties"></a>Cómo configurar puertos de envío mediante las propiedades de contexto de Windows SharePoint Services
En este tema se describe cómo configurar puertos de envío de Windows SharePoint Services en tiempo de ejecución mediante las propiedades de contexto de Windows Sharepoint Service en una orquestación de BizTalk. Se puede usar el mismo mecanismo para configurar los puertos de envío enlazados en tiempo de ejecución. Las propiedades de configuración para un puerto de envío dinámico se establecen en una orquestación en tiempo de ejecución. Propiedades del adaptador que se exponen en la **propiedades de transporte de Windows SharePoint Services** cuadro de diálogo también puede aplicarse a un puerto de envío enlazado en tiempo de ejecución. Para establecer las propiedades de configuración para un puerto de envío enlazado en tiempo de ejecución mediante las propiedades de contexto del adaptador de Windows Sharepoint Services, siga estos pasos:  
  
### <a name="to-set-configuration-properties-for-a-send-port-using-windows-sharepoint-services-adapter-context-properties"></a>Para establecer las propiedades de configuración para un puerto de envío mediante las propiedades de contexto del adaptador de Windows Sharepoint Services  
  
1.  Para los puertos de envío dinámico, para crear un dinámico unidireccional puerto de envío, siga los pasos descritos en el tema [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md).  
  
2.  Use un **asignación de mensajes** forma dentro de un **construir mensaje** forma de una orquestación para establecer las propiedades de configuración para el mensaje saliente. Para obtener un ejemplo de cómo establecer las propiedades de configuración para un mensaje saliente vea [Tutorial: módulo 3: obtener acceso a propiedades de SharePoint desde una orquestación](../core/walkthrough-module-3-accessing-sharepoint-properties-from-an-orchestration.md). El **construir un nuevo mensaje** sección de este tema muestra cómo establecer las propiedades de configuración de un mensaje saliente. Las propiedades de contexto del adaptador que se correlacionan con las propiedades que se pueden establecer en el **propiedades de transporte de Windows SharePoint Services** cuadro de diálogo se muestran en la tabla siguiente:  
  
    |Propiedades de transporte|Propiedad de contexto del adaptador|Tipo de datos|Comentarios|  
    |------------------------|------------------------------|---------------|--------------|  
    |Puerto del servicio Web del adaptador|WSS.ConfigAdapterWSPort|int|Los valores válidos son de 1 a 65535.<br /><br /> El valor predeterminado es 80|  
    |Timeout|WSS.ConfigTimeout|int|Los valores válidos son de 1000 a 2147483647.<br /><br /> El valor predeterminado es 100000<br /><br /> Especifique un valor de 0 para indicar un tiempo de espera infinito.|  
    |Dirección URL de carpeta de destino|N/D|N/D|Para puertos dinámicos, se establece indirectamente estableciendo la **Microsoft.XLANGs.BaseTypes.Address** propiedad del puerto dinámico con una forma de expresión en una orquestación. En puertos enlazados en tiempo de ejecución, esta propiedad no se puede establecer en tiempo de ejecución puesto que siempre se reemplaza por el valor del puerto de envío físico.|  
    |Nombre de archivo|WSS.Filename|String|Admite el uso de todas las macros de nombre de archivo que se puede usar en las propiedades de transporte excepto para la **% Filename %** y **% Extension %** macros.|  
    |Alias de espacios de nombres|WSS.ConfigNamespaceAliases|String|Si un conjunto de alias de espacios de nombres para un mensaje en tiempo de ejecución coincide con el conjunto de alias de espacios de nombres para el puerto de envío al que se enruta el mensaje, los espacios de nombres se combinan y se produce un error de enrutamiento. Pare evitar este problema, asegúrese de que los alias de espacios de nombres no sean idénticos. Por ejemplo, si se usa la siguiente expresión en una orquestación para establecer el alias de espacios de nombres para un mensaje:<br /><br /> `Message_Task(WSS.ConfigNamespaceAliases)= "orchns='http://OrderProcess.PurchaseOrder'";`<br /><br /> y si este mensaje se enruta a un puerto de envío que especifica el siguiente valor para la **alias Namespace** propiedad:<br /><br /> orchns ='http://OrderProcess.PurchaseOrder'<br /><br /> se producirá un error cuando BizTalk Server intente enrutar el mensaje en este puerto de envío. Para resolver este problema podría especificar el siguiente valor para la **alias Namespace** propiedad del puerto de envío:<br /><br /> **orchns2**='http://OrderProcess.PurchaseOrder'|  
    |Sobrescribir|WSS.ConfigOverwrite|String|Los valores válidos son:<br /><br /> -"Sí"<br /><br /> -"no"<br /><br /> -"rename"|  
    |Dirección URL del sitio de SharePoint|WSS.InListUrl|String|Para puertos dinámicos, se establece indirectamente estableciendo la **Microsoft.XLANGs.BaseTypes.Address** propiedad del puerto dinámico con una forma de expresión en una orquestación. En puertos enlazados en tiempo de ejecución, esta propiedad no se puede establecer en tiempo de ejecución puesto que siempre se reemplaza por el valor del puerto de envío físico.|  
    |Integración con Microsoft Office|WSS.ConfigOfficeIntegration|String|Los valores válidos son:<br /><br /> -"Sí"<br /><br /> -"no"<br /><br /> -"yesformlibrary"<br /><br /> -"opcional"|  
    |Biblioteca de documentos de plantillas|WSS.ConfigTemplatesDocLib|String|None|  
    |Biblioteca de documentos de reserva de plantillas|WSS.ConfigCustomTemplatesDocLib|String|None|  
    |Columna de espacio de nombres de reserva de plantillas|WSS.ConfigCustomTemplatesNamespaceCol|String|None|  
    |Columna de espacio de nombres de plantillas|WSS.ConfigTemplatesNamespaceCol|String|None|  
    |Columna `n`|WSS.ConfigPropertiesXml<br /><br /> Nombre de la columna se establece \<PropertyName*x*\>*columnname*\</ PropertyName*x* \> campo.|String|None|  
    |Columna `n` Valor|WSS.ConfigPropertiesXml<br /><br /> Valor de la columna se establece \<PropertySource*x*\>*columnvalue*\</ PropertySource*x* \> campo.|String|Admite el uso de todas las macros de nombre de archivo que se puede usar en las propiedades de transporte excepto para la **% Filename %** y **% Extension %** macros.|  
  
    > [!NOTE]
    >  Los valores para estas propiedades de contexto distinguen entre mayúsculas y minúsculas. Al establecer los valores de configuración para un puerto dinámico con propiedades de contexto, debe asegurarse de que se utilizan las mayúsculas y minúsculas del modo apropiado o, de lo contrario, se producirá un error cuando BizTalk intente enrutar el documento al puerto de envío designado.  
  
3.  Use una forma expresión en una orquestación para establecer el **Microsoft.XLANGs.BaseTypes.Address** propiedad dinámico de puerto de envío. Esta propiedad se usa para especificar el URI en el que el puerto de envío dinámico enruta el mensaje. Para obtener un ejemplo de cómo establecer el **Microsoft.XLANGs.BaseTypes.Address** vea de propiedad para un puerto de envío dinámico la **crear una expresión** sección del tema [Tutorial: módulo 3: Acceso a las propiedades de SharePoint desde una orquestación](../core/walkthrough-module-3-accessing-sharepoint-properties-from-an-orchestration.md). Para obtener más información acerca de las propiedades de contexto del adaptador de Windows Sharepoint Services, vea [referencia de propiedades de adaptador de Windows SharePoint Services](../core/windows-sharepoint-services-adapter-properties-reference.md).  
  
     También es posible establecer de forma dinámica algunas propiedades de un puerto de envío enlazados en tiempo de ejecución de Windows Sharepoint Services en una orquestación. Si lo ha hecho, el puerto de Windows SharePoint Services se configurará dos veces, una a través de las propiedades de contexto de Windows SharePoint Services y otra mediante el cuadro de diálogo Propiedades de transporte Windows SharePoint Services. De forma predeterminada, el cuadro de diálogo Propiedades de transporte Windows SharePoint Services adquiere propiedad sobre las propiedades de configuración especificadas en las propiedades de contexto. Para usar la configuración especificada en las propiedades de contexto, siga estos pasos:  
  
    1.  Para crear una variable Static unidireccional puerto de envío, siga los pasos descritos en el tema [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md).  
  
    2.  Al establecer las propiedades del puerto de envío, defina el URI para el puerto de envío especificando los valores adecuados para el **dirección URL del sitio de Sharepoint** y **dirección URL de la carpeta de destino** propiedades.  
  
    3.  Establezca el valor de la **sobrescribir** propiedad **orquestación** si desea usar el valor definido por la propiedad de contexto **WSS. ConfigOverwrite** en una orquestación.  
  
    4.  Establecer el **integración con Microsoft Office** propiedad **orquestación** si desea usar el valor definido por la propiedad de contexto **WSS. ConfigOfficeIntegration** en una orquestación.  
  
    5.  Escriba un valor de **-1** para cualquier enviar propiedades del puerto que usa el tipo de datos entero si desea establecer estos valores con una propiedad de contexto en una orquestación.  
  
    6.  Deje en blanco cualquier propiedad de puerto de envío que use el tipo de datos de cadena si desea establecer estos valores con una propiedad de contexto en una orquestación. Esto no se aplica a la **dirección URL del sitio de Sharepoint** y **dirección URL de la carpeta de destino** propiedades. Estas propiedades deben especificarse en el **propiedades de transporte de Windows Sharepoint Services** cuadro de diálogo.  
  
    7.  Use un **asignación de mensajes** forma dentro de un **construir mensaje** forma de una orquestación para establecer las propiedades de configuración para el mensaje saliente. Para obtener un ejemplo de cómo establecer las propiedades de configuración para un mensaje saliente vea [Tutorial: módulo 3: obtener acceso a propiedades de SharePoint desde una orquestación](../core/walkthrough-module-3-accessing-sharepoint-properties-from-an-orchestration.md). El **construir un nuevo mensaje** sección de este tema muestra cómo establecer las propiedades de configuración de un mensaje saliente.  
  
    8.  Las propiedades de puerto de envío que se configuran con un valor de -1 (para propiedades que usan el tipo de datos entero) "Orquestación" (para las propiedades de enumeración desplegables) o se han dejado en blanco (para propiedades que usan el tipo de datos de cadena) se establecerán en tiempo de ejecución con la propiedad de contexto que se especificó en la orquestación.  
  
 Si usa el adaptador de Windows SharePoint Services para recibir los formularios de InfoPath con datos adjuntos integrados y los envía a una biblioteca de documentos de SharePoint, complete los siguientes pasos para conservar las instrucciones de procesamiento de InfoPath que estén en el formulario:  
  
### <a name="to-preserve-infopath-processing-instructions-for-infopath-forms-with-embedded-attachments-processed-by-biztalk-server"></a>Para conservar las instrucciones de procesamiento de InfoPath para los formularios de InfoPath con datos adjuntos integrados que procesa BizTalk Server  
  
1.  Si usas un mapa en la orquestación para asignar datos de un formulario de InfoPath a otro formulario de InfoPath, asegúrese de que ha establecido la **copiar instrucciones de procesamiento (PI)** propiedad en el mapa para **Sí**. Este parámetro se establece en el **encabezado personalizado** sección de la **propiedades de cuadrícula** página del mapa.  
  
2.  Si no está usando una asignación en la orquestación, actualice el mensaje de salida mediante la siguiente expresión en una forma de asignación de mensaje:  
  
    ```  
    NewMessage(XMLNORM.ProcessingInstructionOption) = 1;  
    NewMessage(XMLNORM.ProcessingInstruction) = "<?mso-infoPath-file-attachment-present?>"  
    ```  
  
     En la expresión anterior, *NewMessage* es el mensaje de salida que se va a agregar las instrucciones de procesamiento.  
  
## <a name="see-also"></a>Vea también  
 [Cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md)