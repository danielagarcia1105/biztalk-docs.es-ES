---
title: Configurar un enlace de puerto físico mediante un archivo de enlace de puerto a Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- port binding file
- physical port binding, configuring by using a port binding file
ms.assetid: 1758e89c-d56c-4e67-919b-c0bbb22878bf
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36b5def2e4cca694e63040cfc8721be3a8819222
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966877"
---
# <a name="configure-a-physical-port-binding-using-a-port-binding-file-to-siebel"></a>Configurar un enlace de puerto físico mediante un archivo de enlace de puerto para Siebel
Cuando se usa el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para generar los metadatos de un artefacto de Siebel, que no sean los archivos de esquema, el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] también genera un archivo de enlace de puerto. Puede importar este archivo de enlace en la aplicación de BizTalk para crear un puerto de envío físicos. Consulte [reutilizar los enlaces del adaptador en el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md). Si importa este archivo de enlace, no es necesario crear manualmente un puerto de envío físicos.  
  
> [!IMPORTANT]
>  Al usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], si no especifica un valor para una propiedad de enlace de tipo cadena y cuyo valor predeterminado es null, que enlaza la propiedad no estará disponible en el archivo de enlace. Se deben agregar manualmente la propiedad de enlace y su valor en el archivo de enlace, si es necesario.  
  
 Creación de un puerto mediante el archivo de enlace de puerto siempre crea un puerto de envío bidireccional. Si desea crear un puerto unidireccional, puede crearla manualmente siguiendo los pasos descritos en [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md). O bien, puede seguir las soluciones alternativas que se documentan en este tema para modificar el archivo de enlace de puerto para crear puertos unidireccionales.  
  
> [!IMPORTANT]
>  Mediante el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] no crea un archivo de enlace de puerto con el que puede crear un puerto de WCF-Siebel. Sin embargo, se podrían realizar algunos cambios en el archivo de enlace de puerto generado por el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y usarlo para crear un puerto de WCF-Siebel. Para obtener más información, vea Configurar un puerto de WCF-Siebel mediante el complemento de puerto de enlace archivo generado utilizando Consume Adapter Service.  
  
 Estos son algunos puntos clave que debe conocer en relación con el archivo de enlace generado por el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]:  
  
-   Los archivos se crean con una convención de nomenclatura específica. Si genera los metadatos para operaciones de salida, es decir enviar mensajes al sistema Siebel, el nombre del archivo es WcfSendPort_SiebelBinding_Custom.bindinginfo.xml.  
  
-   El archivo contiene información sobre la configuración de enlace, el tipo de enlace, el URI del extremo y la acción de puerto basándose en las operaciones para el que se generan los metadatos. Al importar este archivo de enlace para crear un puerto, toda la información pertinente necesaria para configurar un puerto físico se establece automáticamente en el puerto.  
  
    > [!IMPORTANT]
    >  De forma predeterminada, se asigna la acción en el puerto de envío para el nombre de la operación para el que generar los metadatos. Por ejemplo, si genera los metadatos de la operación de inserción en el componente empresarial de la cuenta, la acción en el puerto se establece en `<Operation Name="Insert" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert " />`. Sin embargo, el nombre de la operación en el puerto de envío lógico que se crea en la orquestación de BizTalk no puede ser el mismo. Debe asegurarse de que el nombre de la operación en el puerto lógico (en la orquestación de BizTalk) y el puerto de envío físico (en la consola de administración de BizTalk Server) son los mismos. De lo contrario, recibirá un error al enviar mensajes al sistema Siebel a través del puerto de envío.  
  
-   Solo deberá proporcionar las credenciales para el puerto para conectarse al sistema Siebel. Mientras que el archivo de enlace conservan el nombre de usuario con la que se va a conectar, por motivos de seguridad del archivo de enlace no contiene la contraseña.  
  
## <a name="key-considerations-for-using-the-port-binding-file"></a>Consideraciones claves para usar el archivo de enlace de puerto  
  
-   Al importar el archivo de enlace, es posible que obtenga un mensaje de diálogo que le informa que el nombre de la aplicación de BizTalk en el archivo de enlace no coincide con el nombre de la aplicación a la que va a importar el archivo de enlace. Puede ignorar este mensaje y continuar.  
  
-   El archivo de enlace también contiene los nombres de los puertos y ubicaciones de recepción. Si la aplicación de BizTalk al que va a importar el archivo de enlace crea un puerto o una ubicación de recepción que tiene el mismo nombre que un puerto ya existente en la misma aplicación de BizTalk, obtendrá un error. Debe editar manualmente el archivo de enlaces para especificar un nombre único para los puertos o las ubicaciones de recepción.  
  
-   De forma predeterminada, el archivo de enlace de puerto siempre contiene definiciones para los puertos de envío bidireccional. Al importar este archivo en una aplicación de BizTalk, crea un puerto de envío bidireccional. Sin embargo, puede que tenga una orquestación que tiene un puerto de envío unidireccional. Por lo tanto, al configurar una orquestación de este tipo y usar el puerto que se crea al importar el archivo de enlace, el puerto no está disponible en la lista. Esto sucede porque el puerto lógico que creó como parte de la orquestación es un puerto unidireccional, mientras que el puerto físico que creó en la orquestación es un puerto bidireccional. En tales casos, puede editar el archivo de enlaces para que los cambios siguientes:  
  
    |Para|Haga esto|  
    |--------------|-------------|  
    |Para editar el archivo de enlaces de puerto para configurar un puerto de envío unidireccional|-En el extracto siguiente, cambie el valor de **IsTwoWay** propiedad **false**. Originalmente, se establece en **true**.<br /><br /> `<SendPort Name="port_name" IsStatic="true" IsTwoWay="false" BindingOption="0">`<br /><br /> -Comentar los extractos siguientes:<br /><br /> `<ReceivePipeline Name="Microsoft.BizTalk.DefaultPipelines.XMLReceive"    FullyQualifiedName="Microsoft.BizTalk.DefaultPipelines.XMLReceive,    Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral,    PublicKeyToken=token" Type="1" TrackingOption="None" Description=""/>`<br /><br /> `<ReceivePipelineData xsi:nil="true" />`|  
  
## <a name="configuring-a-wcf-siebel-port-using-the-port-binding-file-generated-using-consume-adapter-service-add-in"></a>Configurar un puerto de WCF-Siebel mediante el archivo de enlace de puerto generado mediante Consume Adapter Service complemento  
 El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] también crea un archivo de enlace de puerto que se puede importar en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Puede usar el mismo archivo de enlace de puerto para crear también el puerto de BizTalk WCF-Siebel en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Sin embargo, antes de crear el puerto de WCF-Siebel debe realizar las siguientes tareas para modificar el archivo de enlace de puerto.  
  
1. Abra el archivo de enlace de puerto en un editor de texto.  
  
2. Buscar y reemplazar "WCF-Custom" con el nombre con el que se ha agregado el adaptador de WCF-Siebel [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Por ejemplo, si ha agregado el adaptador de WCF-Siebel como "SiebelAdapter", reemplace "WCF-Custom" con "SiebelAdapter".  
  
3. Busque el atributo "ConfigurationClsid" y sustituya el valor existente del atributo "7971A78D-AE8F-42B4-834D-3A957FD945E9".  
  
4. Guarde y cierre el archivo de enlace.  
  
5. Importar el archivo de enlace en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Consulte [reutilizar los enlaces del adaptador en el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md). 
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para crear aplicaciones de BizTalk con el Siebel 

adaptador] (.. /.. / adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)