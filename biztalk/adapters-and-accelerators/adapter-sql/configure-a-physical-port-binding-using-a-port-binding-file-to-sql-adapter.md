---
title: Configurar un enlace de puerto físico mediante un archivo de enlace de puerto para usar el adaptador SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95b54357-b23d-4ed7-8e31-bd60ed3e625f
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 631914f72287b9fbd48a6695a4edf79e88d28182
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014205"
---
# <a name="configure-a-physical-port-binding-using-a-port-binding-file-to-use-the-sql-adapter"></a>Configurar un enlace de puerto físico mediante un archivo de enlace de puerto para usar el adaptador SQL
Cuando se usa el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para generar los metadatos de un artefacto de SQL Server, que no sean los archivos de esquema, el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] también genera un archivo de enlace de puerto. Puede importar este archivo de enlace en la aplicación de BizTalk para crear un envío físico o puerto de recepción. Para obtener instrucciones sobre cómo importar archivos de enlace, consulte [reutilizar los enlaces del adaptador](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md). Si importa este archivo de enlace, es necesario crear manualmente un envío físico o bien el puerto de recepción.  
  
> [!IMPORTANT]
>  Al usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], si no especifica un valor para una propiedad de enlace de tipo cadena y cuyo valor predeterminado es null, que enlaza la propiedad no estará disponible en el archivo de enlace. Se deben agregar manualmente la propiedad de enlace y su valor en el archivo de enlace, si es necesario.  
  
 Crear un puerto mediante el archivo de enlace de puerto siempre crea un puerto de envío bidireccional o puerto de recepción unidireccional. Si desea crear un puerto de envío unidireccional, puede crear manualmente mediante los pasos descritos en [configurar manualmente un enlace de puerto físico al adaptador de SQL](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md). O bien, puede seguir las soluciones alternativas que se documentan en este tema para modificar el archivo de enlace de puerto para crear puertos de envío unidireccional.  
  
> [!NOTE]
>  Para operaciones de entrada, el archivo de enlace de puerto siempre creará un puerto de recepción unidireccional. Esto es porque el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] solo admite unidireccional puerto de recepción para operaciones de entrada.  
> 
> [!IMPORTANT]
>  Mediante el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] no crea un archivo de enlace de puerto con el que puede crear un puerto de WCF-SQL. Sin embargo, se podrían realizar algunos cambios en el archivo de enlace de puerto generado por el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y usarlo para crear un puerto de WCF-SQL. Para obtener más información, consulte [configurar un puerto de WCF-SQL mediante el puerto de enlace archivo generado utilizando Consume Adapter Service complemento](#BKMK_Create_WCF_SQL).  
  
 A continuación se muestran algunos puntos clave que debe conocer en relación con el enlace de archivos que el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] genera:  
  
- Los archivos se crean con una convención de nomenclatura específica. Si ha generado los metadatos para las operaciones de salida, es decir, para enviar mensajes a SQL Server, el nombre del archivo es WcfSendPort_SqlAdapterBinding_Custom.bindinginfo.xml.  
  
   Si genera los metadatos para operaciones de entrada, es decir, para recibir mensajes de SQL Server, el nombre del archivo es WcfReceivePort_SqlAdapterBinding_Custom.bindinginfo.xml.  
  
- El archivo contiene información sobre la configuración de enlace, el tipo de enlace, el URI del extremo y la acción de puerto basándose en las operaciones para el que se generan los metadatos. Al importar este archivo de enlace en la aplicación de BizTalk para crear un puerto, toda la información pertinente necesaria para configurar un puerto físico se establece automáticamente en el puerto.  
  
  > [!IMPORTANT]
  >  De forma predeterminada, se asigna la acción en el puerto de envío para el nombre de la operación para el que genera los metadatos. Por ejemplo, si genera los metadatos de la operación de inserción en la tabla Customer, la acción en el puerto se establece en `<Operation Name="Insert" Action="TableOp/Insert/dbo/CustomerTable" />`. Sin embargo, el nombre de la operación en el puerto de envío lógico que se crea en la orquestación de BizTalk no puede ser el mismo. Debe asegurarse de que el nombre de operación en la lógica de envío puerto (en la orquestación de BizTalk) y puerto de envío físico (en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración) son los mismos. De lo contrario, recibirá un error al enviar mensajes a SQL Server a través del puerto de envío.  
  
- Solo deberá proporcionar las credenciales para el puerto para conectarse a SQL Server. Aunque el archivo de enlace conservar el nombre de usuario con la que se va a conectar, por motivos de seguridad del archivo de enlace no contiene la contraseña.  
  
## <a name="key-considerations-for-using-the-port-binding-file"></a>Consideraciones claves para usar el archivo de enlace de puerto  
  
- Al importar el archivo de enlace, es posible que obtenga un mensaje de diálogo que le informa que el nombre de la aplicación de BizTalk en el archivo de enlace no coincide con el nombre de la aplicación a la que va a importar el archivo de enlace. Puede ignorar este mensaje y continuar.  
  
- El archivo de enlace también contiene los nombres de los puertos y ubicaciones de recepción. Si la aplicación de BizTalk al que va a importar el archivo de enlace crea un puerto o una ubicación de recepción que tiene el mismo nombre que un puerto ya existente en la misma aplicación de BizTalk, obtendrá un error. Debe editar manualmente el archivo de enlace para especificar un nombre único para los puertos o las ubicaciones de recepción.  
  
- El archivo de enlace también contiene información sobre el URI de conexión. Si el archivo de enlace crea una ubicación de recepción que tiene el mismo URI de recepción como una ubicación de recepción ya existente en la misma aplicación de BizTalk, obtendrá un error. Debe editar manualmente el archivo de enlace para especificar un URI único.  
  
- De forma predeterminada, el archivo de enlace de puerto para las operaciones de salida siempre contiene definiciones para un puerto de envío bidireccional. Al importar este archivo en una aplicación de BizTalk, crea un puerto de envío bidireccional. Sin embargo, puede que tenga una orquestación que tiene un puerto de envío unidireccional. Por lo tanto, al configurar una orquestación de este tipo y usar el puerto que se crea al importar el archivo de enlace, el puerto no está disponible en la lista. Esto sucede porque el puerto lógico que creó como parte de la orquestación es un puerto unidireccional, mientras que el puerto físico que creó en la orquestación es un puerto bidireccional. En tales casos, puede editar el archivo de enlace para que los cambios siguientes:  
  
  |Para|Haga esto|  
  |--------------|-------------|  
  |Para editar el archivo de enlace de puerto para configurar un puerto de envío unidireccional|1.  En el extracto siguiente, cambie el valor de la **IsTwoWay** propiedad **false**. Originalmente, se establece en **true**.<br />     `<SendPort Name="port_name" IsStatic="true" IsTwoWay="false" BindingOption="0">`<br />2.  Comente los extractos siguientes:<br />     `<ReceivePipeline Name="Microsoft.BizTalk.DefaultPipelines.XMLReceive"    FullyQualifiedName="Microsoft.BizTalk.DefaultPipelines.XMLReceive,    Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral,    PublicKeyToken=token" Type="1" TrackingOption="None" Description=""/>`<br />     `<ReceivePipelineData xsi:nil="true" />`|  
  
  > [!IMPORTANT]
  >  Para operaciones de entrada, el archivo de enlace de puerto siempre creará un puerto de recepción unidireccional. Esto es porque el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] solo admite unidireccional puerto de recepción para operaciones de entrada.  
  
##  <a name="BKMK_Create_WCF_SQL"></a> Configurar un puerto de WCF-SQL mediante el archivo de enlace de puerto generado utilizando consumir servicio del adaptador de complemento  
 El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] también crea un archivo de enlace de puerto que se puede importar en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Puede usar el mismo archivo de enlace de puerto para crear también el puerto de BizTalk WCF-SQL en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Sin embargo, antes de crear el puerto WCF-SQL debe realizar las siguientes tareas para modificar el archivo de enlace de puerto.  
  
1. Abra el archivo de enlace de puerto en un editor de texto.  
  
2. Buscar y reemplazar "WCF-Custom" con el nombre con el que se ha agregado el adaptador de WCF-SQL [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Por ejemplo, si ha agregado el adaptador de WCF-SQL como "Adaptador de SQL", reemplace "WCF-Custom" con "Adaptador de SQL".  
  
3. Busque el atributo "ConfigurationClsid" y sustituya el valor existente del atributo "59B35D03-6A06-4734-A249-EF561254ECF7".  
  
4. Guarde y cierre el archivo de enlace.  
  
5. Importar el archivo de enlace en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener instrucciones sobre cómo importar el archivo de enlace, consulte [reutilizar los enlaces del adaptador](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md).
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para desarrollar aplicaciones de BizTalk con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)