---
title: "Configurar un enlace de puerto físico mediante un archivo de enlace de puerto a SAP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- port binding file
- physical port binding, configuring using a port binding file
ms.assetid: c637971c-3ecd-4026-8f74-bd5173774438
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0383ad738140467f17e4ff56ba60f2cc5b9698f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-a-physical-port-binding-using-a-port-binding-file-to-sap"></a>Configurar un enlace de puerto físico mediante un archivo de enlace de puerto a SAP
Cuando se usa el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para generar metadatos para un artefacto SAP, distinto de los archivos de esquema, el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] también genera un archivo de enlace de puerto. Puede importar este archivo de enlace en la aplicación de BizTalk para crear un envío físico o puerto de recepción. [Reutilizar los enlaces del adaptador SAP](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md) incluye pasos para importar archivos de enlace. Si importa este archivo de enlace, no es necesario crear manualmente un envío físico, o puerto de recepción.  
  
> [!IMPORTANT]
>  Al usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], si no especifica un valor para una propiedad de enlace de tipo cadena y cuyo valor predeterminado es null, a continuación, que enlaza la propiedad no estará disponible en el archivo de enlace. Debe agregar manualmente la propiedad de enlace y su valor en el archivo de enlace, si es necesario.  
  
 Crear un puerto mediante el archivo de enlace de puerto siempre crea un envío bidireccional o puerto de recepción. Si desea crear un puerto unidireccional, puede crearla manualmente mediante el uso de los pasos descritos en [configurar manualmente un enlace de puerto físico para el adaptador SAP](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md). O bien, puede seguir las soluciones alternativas que se documentan en este tema para modificar el archivo de enlace de puerto para crear puertos unidireccionales.  
  
> [!IMPORTANT]
>  Mediante el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] no crea un archivo de enlace de puerto con la que puede crear un puerto de SAP de WCF. Sin embargo, podría realizar algunos cambios en el archivo de enlace de puerto generado por el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y usarlo para crear un puerto de SAP de WCF. Para obtener más información, consulte [configurar un puerto de SAP de WCF con el complemento de puerto de enlace archivo generado utilizando Consume Adapter Service](#BKMK_add_wcf_sap).  
  
 Siguientes son algunos puntos clave que debe conocer en relación con el archivo de enlace generado por el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]:  
  
-   Los archivos se crean con una convención de nomenclatura específica. Si genera metadatos para las operaciones de salida, es decir enviar mensajes al sistema SAP, el nombre del archivo es WcfSendPort_SAPBinding_Custom.bindinginfo.xml.  
  
     Si genera metadatos para operaciones de entrada, que se va a recibir mensajes desde el sistema SAP, el nombre del archivo es WcfReceivePort_SAPBinding_Custom.bindinginfo.xml.  
  
-   El archivo contiene información sobre la configuración de enlace, el tipo de enlace, el URI del extremo y la acción de puerto basándose en las operaciones para el que se generan los metadatos. Al importar este archivo de enlace para crear un puerto, toda la información relevante necesaria para configurar un puerto físico se establece automáticamente en el puerto.  
  
    > [!IMPORTANT]
    >  De forma predeterminada, se asigna la acción en el puerto de envío para el nombre de la operación para la que generar los metadatos. Por ejemplo, si genera metadatos para RFC_CUSTOMER_GET, la acción en el puerto se establece en `<Operation Name="RFC_CUSTOMER_GET" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET " />`. Sin embargo, el nombre de la operación en el puerto de envío lógico que se crea en la orquestación de BizTalk podría no ser el mismo. Debe asegurarse de que el nombre de la operación en el puerto lógico (en la orquestación de BizTalk) y el puerto de envío físico (en la consola de administración de BizTalk Server) son los mismos. De lo contrario, recibirá un error al enviar mensajes al sistema SAP a través del puerto de envío.  
  
-   Basta con proporcionar las credenciales para el puerto para conectarse al sistema SAP. Mientras que el archivo de enlace conservan el nombre de usuario con el que se va a conectar, por motivos de seguridad del archivo de enlace no contiene la contraseña.  
  
## <a name="key-considerations-for-using-the-port-binding-file"></a>Consideraciones claves para utilizar el archivo de enlace de puerto  
  
-   Cuando se importa el archivo de enlace, podría obtener un mensaje de cuadro de diálogo en el que se indica que el nombre de la aplicación de BizTalk en el archivo de enlace no coincide con el nombre de la aplicación a la que va a importar el archivo de enlace. Puede omitir este mensaje y continuar.  
  
-   El archivo de enlace también contiene los nombres de puertos y ubicaciones de recepción. Si la aplicación de BizTalk al que va a importar el archivo de enlace crea un puerto o una ubicación de recepción que tiene el mismo nombre que un puerto ya existente en la misma aplicación de BizTalk, obtendrá un error. Debe editar manualmente el archivo de enlaces para especificar un nombre único para los puertos o ubicaciones de recepción.  
  
-   El archivo de enlace también contiene información sobre el URI de conexión. Si el archivo de enlace crea una ubicación de recepción que tiene el mismo URI de recepción como una ubicación de recepción ya existente en la misma aplicación de BizTalk, obtendrá un error. Debe editar manualmente el archivo de enlace para especificar un URI único.  
  
-   De forma predeterminada, el archivo de enlace de puerto siempre contiene definiciones para los puertos bidireccionales (envío o recepción). Al importar este archivo en una aplicación de BizTalk, se crea un envío bidireccional o puerto de recepción. Sin embargo, puede tener una orquestación que tenga un envío unidireccional o puerto de recepción. Por lo tanto, cuando una orquestación de este tipo de configurar y usar el puerto creado importando el archivo de enlace, el puerto no está disponible en la lista. Esto sucede porque el puerto lógico que creó como parte de la orquestación es un puerto unidireccional, mientras que el puerto físico que creó en la orquestación es un puerto bidireccional. En tales casos, puede editar el archivo de enlaces para realizar los siguientes cambios:  
  
    |Para|Haga esto|  
    |--------------|-------------|  
    |Para editar el archivo de enlaces de puerto para configurar un puerto de envío unidireccional|1.  En el extracto siguiente, cambie el valor de **IsTwoWay** propiedad **false**. Originalmente, se establece en **true**.<br />     `<SendPort Name="port_name" IsStatic="true" IsTwoWay="false" BindingOption="0">`<br />2.  Comente los extractos de siguientes:<br />     `<ReceivePipeline Name="Microsoft.BizTalk.DefaultPipelines.XMLReceive"    FullyQualifiedName="Microsoft.BizTalk.DefaultPipelines.XMLReceive,    Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral,    PublicKeyToken=token" Type="1" TrackingOption="None" Description=""/>`<br />     `<ReceivePipelineData xsi:nil="true" />`|  
    |Para editar el archivo de enlaces de puerto para configurar un puerto de recepción unidireccional|1.  En el extracto siguiente, cambie el valor de **IsTwoWay** propiedad **false**. Originalmente, se establece en **true**.<br />     `<ReceivePort Name="port_name" IsTwoWay="false" BindingOption="1">`<br />2.  Comente los extractos de siguientes:<br />     `<SendPipeline Name="Microsoft.BizTalk.DefaultPipelines.XMLTransmit"    FullyQualifiedName="Microsoft.BizTalk.DefaultPipelines.XMLTransmit,    Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral,    PublicKeyToken=token" Type="2" TrackingOption="None" Description="" />`<br />     `<SendPipelineData xsi:nil="true" />`<br />     `<SendPipelineData xsi:nil="true" />`|  
  
##  <a name="BKMK_add_wcf_sap"></a>Configurar un puerto de SAP de WCF mediante el archivo de enlace de puerto generado mediante Consume Adapter Service complemento  
 El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] también crea un archivo de enlace de puerto que se puede importar en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Puede usar el mismo archivo de enlace de puerto para crear el puerto de SAP de WCF de BizTalk en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Sin embargo, antes de crear el puerto de SAP de WCF debe realizar las siguientes tareas para modificar el archivo de enlace de puerto.  
  
1.  Abra el archivo de enlace de puerto en un editor de texto.  
  
2.  Buscar y reemplazar "WCF-Custom" con el nombre con el que agregó el adaptador de WCF-SAP [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Por ejemplo, si ha agregado el adaptador SAP de WCF como "SAPAdapter", reemplace "WCF-Custom" con "SAPAdapter".  
  
3.  Busque el atributo "ConfigurationClsid" y reemplace el valor existente del atributo con "A5F15999-8879-472d-8C62-3B5EA9406504".  
  
4.  Guarde y cierre el archivo de enlace.  
  
5.  Importar el archivo de enlace en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. [Reutilizar los enlaces del adaptador SAP](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md) se enumeran los pasos.
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para crear aplicaciones de SAP](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)