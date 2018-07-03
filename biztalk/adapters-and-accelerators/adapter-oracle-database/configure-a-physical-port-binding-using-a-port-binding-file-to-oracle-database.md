---
title: Configurar un enlace de puerto físico mediante un archivo de enlace de puerto a la base de datos de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- physical port binding, configuring by using a port binding file
ms.assetid: 154d219e-c6f3-4f70-9ac5-d9345f5260e9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 846c77040527694822381cfd55c805f78d96e69d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001493"
---
# <a name="configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database"></a>Configurar un enlace de puerto físico mediante un archivo de enlace de puerto a la base de datos de Oracle
Cuando se usa el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para generar los metadatos de un artefacto de la base de datos de Oracle, que no sean los archivos de esquema, el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] también genera un archivo de enlace de puerto. Puede importar este archivo de enlace en la aplicación de BizTalk para crear un envío físico o puerto de recepción. Para obtener instrucciones sobre cómo importar archivos de enlace, consulte [enlaces del adaptador de base de datos de Oracle reutilizar](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md). Si importa este archivo de enlace, es necesario crear manualmente un envío físico o bien el puerto de recepción.  
  
> [!IMPORTANT]
>  Al usar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], si no especifica un valor para una propiedad de enlace de tipo cadena y cuyo valor predeterminado es null, que enlaza la propiedad no estará disponible en el archivo de enlace. Se deben agregar manualmente la propiedad de enlace y su valor en el archivo de enlace, si es necesario.  
  
 Creación de un puerto mediante un archivo de enlace de puerto siempre crea un envío bidireccional o los puertos de recepción. Si desea crear envío unidireccional o puertos de recepción, puede crearla manualmente siguiendo el procedimiento que se mencionan en [configurar manualmente un enlace de puerto físico para el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md). O bien, puede seguir las soluciones alternativas que se documentan en este tema para modificar el archivo de enlace de puerto para la creación de envío unidireccional o puertos de recepción.  
  
 Estos son algunos puntos clave que debe conocer en relación con el archivo de enlace generado por el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]:  
  
-   Los archivos se crean con una convención de nomenclatura específica. Si genera los metadatos para operaciones de salida, es decir enviar mensajes a la base de datos de Oracle, el nombre del archivo es WcfSendPort_OracleDBBinding_Custom.bindinginfo.xml.  
  
     Si genera los metadatos para operaciones de entrada, que se va a recibir los mensajes de la base de datos de Oracle, el nombre del archivo es WcfReceivePort_OracleDBBinding_Custom.bindinginfo.xml.  
  
-   El archivo contiene información sobre la configuración de enlace, el tipo de enlace, el URI del extremo y la acción de puerto basándose en las operaciones para el que se generan los metadatos. Al importar este archivo de enlace para crear un puerto, toda la información pertinente necesaria para configurar un puerto físico se establece automáticamente en el puerto.  
  
    > [!IMPORTANT]
    >  De forma predeterminada, se asigna la acción en el puerto de envío para el nombre de la operación para el que generar los metadatos. Por ejemplo, si genera los metadatos para una operación de selección en la tabla ACCOUNTACTIVITY, la acción en el puerto se establece en `<Operation Name="Select" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select" />`. Sin embargo, el nombre de la operación en el puerto de envío lógico que se crea en la orquestación de BizTalk no puede ser el mismo. Debe asegurarse de que el nombre de la operación en el puerto lógico (en la orquestación de BizTalk) y el puerto de envío físico (en la consola de administración de BizTalk Server) son los mismos. De lo contrario, recibirá un error al enviar mensajes a la base de datos de Oracle a través del puerto de envío.  
  
-   Solo deberá proporcionar las credenciales para el puerto para conectarse a la base de datos de Oracle. Mientras que el archivo de enlace conservan el nombre de usuario con la que se va a conectar, por motivos de seguridad del archivo de enlace no contiene la contraseña.  
  
## <a name="key-considerations-for-using-the-port-binding-file"></a>Consideraciones claves para usar el archivo de enlace de puerto  
  
-   Al importar el archivo de enlace, es posible que obtenga un mensaje de diálogo que le informa que el nombre de la aplicación de BizTalk en el archivo de enlace no coincide con el nombre de la aplicación a la que va a importar el archivo de enlace. Puede ignorar este mensaje y continuar.  
  
-   El archivo de enlace también contiene los nombres de los puertos y ubicaciones de recepción. Si la aplicación de BizTalk al que va a importar el archivo de enlace crea un puerto o una ubicación de recepción que tiene el mismo nombre que un puerto ya existente en la misma aplicación de BizTalk, obtendrá un error. Debe editar manualmente el archivo de enlaces para especificar un nombre único para los puertos o las ubicaciones de recepción.  
  
-   El archivo de enlace también contiene información sobre el URI de conexión. Si el archivo de enlace crea una ubicación de recepción que tiene el mismo URI de recepción como una ubicación de recepción ya existente en la misma aplicación de BizTalk, obtendrá un error. Debe editar manualmente el archivo de enlace para especificar un URI único. Puede especificar un URI único mediante la inclusión de un identificador de sondeo.  
  
-   De forma predeterminada, el archivo de enlace de puerto siempre contiene las definiciones para los puertos bidireccionales (envío o recepción). Al importar este archivo en una aplicación de BizTalk, crea un envío bidireccional o puerto de recepción. Sin embargo, es posible que dispone de una orquestación que tenga un envío unidireccional o puerto de recepción. Por lo tanto, al configurar una orquestación de este tipo y usar el puerto que se crea al importar el archivo de enlace, el puerto no está disponible en la lista. Esto sucede porque el puerto lógico que creó como parte de la orquestación es un puerto unidireccional, mientras que el puerto físico que creó en la orquestación es un puerto bidireccional. En tales casos, puede editar el archivo de enlaces para que los cambios siguientes:  
  
    |Para|Haga esto|  
    |--------------|-------------|  
    |Para editar el archivo de enlaces de puerto para configurar un puerto de envío unidireccional|-En el extracto siguiente, cambie el valor de **IsTwoWay** propiedad en false. Originalmente, esta opción está establecida en true.<br /><br /> `<SendPort Name="port_name" IsStatic="true" IsTwoWay="false" BindingOption="0">`<br /><br /> -Comentar los extractos siguientes:<br /><br /> `<ReceivePipeline Name="Microsoft.BizTalk.DefaultPipelines.XMLReceive"    FullyQualifiedName="Microsoft.BizTalk.DefaultPipelines.XMLReceive,    Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral,    PublicKeyToken=token" Type="1" TrackingOption="None" Description=""/>`<br /><br /> `<ReceivePipelineData xsi:nil="true" />`|  
    |Para editar el archivo de enlaces de puerto para configurar un puerto de recepción unidireccional|-En el extracto siguiente, cambie el valor de **IsTwoWay** propiedad en false. Originalmente, esta opción está establecida en true.<br /><br /> `<ReceivePort Name="port_name" IsTwoWay="false" BindingOption="1">`<br /><br /> -Comentar los extractos siguientes:<br /><br /> `<SendPipeline Name="Microsoft.BizTalk.DefaultPipelines.XMLTransmit"    FullyQualifiedName="Microsoft.BizTalk.DefaultPipelines.XMLTransmit,    Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral,    PublicKeyToken=token" Type="2" TrackingOption="None" Description="" />`<br /><br /> `<SendPipelineData xsi:nil="true" />`<br /><br /> `<SendPipelineData xsi:nil="true" />`|  
  
## <a name="configuring-a-wcf-oracledb-port-using-the-port-binding-file-generated-using-consume-adapter-service-add-in"></a>Configurar un puerto de WCF-OracleDB mediante el archivo de enlace de puerto generado mediante Consume Adapter Service complemento  
 El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] crea un archivo de enlace de puerto que se puede importar en la consola de administración de BizTalk Server. Puede usar el mismo archivo de enlace de puerto para crear también el puerto de WCF-OracleDB de BizTalk en la consola de administración de BizTalk Server. Sin embargo, antes de crear el puerto de WCF-OracleDB debe realizar las siguientes tareas para modificar el archivo de enlace de puerto.  
  
1. Abra el archivo de enlace de puerto en un editor de texto.  
  
2. Buscar y reemplazar "WCF-Custom" con el nombre con el que se ha agregado el adaptador de WCF-OracleDB [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Por ejemplo, si ha agregado el adaptador de WCF-OracleDB como "OracleDBAdapter", reemplace "WCF-Custom" con "OracleDBAdapter".  
  
3. Busque el atributo "ConfigurationClsid" y sustituya el valor existente del atributo "D7127586-E851-412e-8A8A-2428AEDDC219".  
  
4. Guarde y cierre el archivo de enlace.  
  
5. Importar el archivo de enlace en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener instrucciones sobre cómo importar el archivo de enlace, consulte [enlaces del adaptador de base de datos de Oracle reutilizar](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md).  
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para desarrollar aplicaciones de BizTalk con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)