---
title: Configurar un enlace de puerto físico mediante un archivo de enlace de puerto para Siebel | Documentos de Microsoft
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
ms.openlocfilehash: 05bfa8539c223078fd29c5d99cfac50217bbaa36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222612"
---
# <a name="configure-a-physical-port-binding-using-a-port-binding-file-to-siebel"></a>Configurar un enlace de puerto físico mediante un archivo de enlace de puerto para Siebel
Cuando se usa el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para generar metadatos para un artefacto de Siebel, distinto de los archivos de esquema, el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] también genera un archivo de enlace de puerto. Puede importar este archivo de enlace en la aplicación de BizTalk para crear un puerto de envío físico. Vea [reutilizar enlaces del adaptador en el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md). Si importa este archivo de enlace, no es necesario crear manualmente un puerto de envío físico.  
  
> [!IMPORTANT]
>  Al usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], si no especifica un valor para una propiedad de enlace de tipo cadena y cuyo valor predeterminado es null, a continuación, que enlaza la propiedad no estará disponible en el archivo de enlace. Debe agregar manualmente la propiedad de enlace y su valor en el archivo de enlace, si es necesario.  
  
 Crear un puerto mediante el archivo de enlace de puerto siempre crea un puerto de envío bidireccional. Si desea crear un puerto unidireccional, puede crearla manualmente siguiendo los pasos descritos en [configurar un enlace de puerto físico mediante un archivo de enlace de puerto para Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md). O bien, puede seguir las soluciones alternativas que se documentan en este tema para modificar el archivo de enlace de puerto para crear puertos unidireccionales.  
  
> [!IMPORTANT]
>  Mediante el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] no crea un archivo de enlace de puerto con la que puede crear un puerto de WCF-Siebel. Sin embargo, podría realizar algunos cambios en el archivo de enlace de puerto generado por el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y usarlo para crear un puerto de WCF-Siebel. Para obtener más información, vea Configurar un puerto de WCF-Siebel mediante el complemento de puerto de enlace archivo generado utilizando Consume Adapter Service.  
  
 Siguientes son algunos puntos clave que debe conocer en relación con el archivo de enlace generado por el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]:  
  
-   Los archivos se crean con una convención de nomenclatura específica. Si genera metadatos para las operaciones de salida, es decir enviar mensajes al sistema Siebel, el nombre del archivo es WcfSendPort_SiebelBinding_Custom.bindinginfo.xml.  
  
-   El archivo contiene información sobre la configuración de enlace, el tipo de enlace, el URI del extremo y la acción de puerto basándose en las operaciones para el que se generan los metadatos. Al importar este archivo de enlace para crear un puerto, toda la información relevante necesaria para configurar un puerto físico se establece automáticamente en el puerto.  
  
    > [!IMPORTANT]
    >  De forma predeterminada, se asigna la acción en el puerto de envío para el nombre de la operación para la que generar los metadatos. Por ejemplo, si genera metadatos para la operación de inserción en el componente empresarial de cuenta, la acción en el puerto se establece en `<Operation Name="Insert" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert " />`. Sin embargo, el nombre de la operación en el puerto de envío lógico que se crea en la orquestación de BizTalk podría no ser el mismo. Debe asegurarse de que el nombre de la operación en el puerto lógico (en la orquestación de BizTalk) y el puerto de envío físico (en la consola de administración de BizTalk Server) son los mismos. De lo contrario, recibirá un error al enviar mensajes al sistema Siebel a través del puerto de envío.  
  
-   Basta con proporcionar las credenciales para el puerto para conectarse al sistema Siebel. Mientras que el archivo de enlace conservan el nombre de usuario con el que se va a conectar, por motivos de seguridad del archivo de enlace no contiene la contraseña.  
  
## <a name="key-considerations-for-using-the-port-binding-file"></a>Consideraciones claves para utilizar el archivo de enlace de puerto  
  
-   Cuando se importa el archivo de enlace, podría obtener un mensaje de cuadro de diálogo en el que se indica que el nombre de la aplicación de BizTalk en el archivo de enlace no coincide con el nombre de la aplicación a la que va a importar el archivo de enlace. Puede omitir este mensaje y continuar.  
  
-   El archivo de enlace también contiene los nombres de puertos y ubicaciones de recepción. Si la aplicación de BizTalk al que va a importar el archivo de enlace crea un puerto o una ubicación de recepción que tiene el mismo nombre que un puerto ya existente en la misma aplicación de BizTalk, obtendrá un error. Debe editar manualmente el archivo de enlaces para especificar un nombre único para los puertos o ubicaciones de recepción.  
  
-   De forma predeterminada, el archivo de enlace de puerto siempre contiene definiciones para puertos de envío bidireccionales. Al importar este archivo en una aplicación de BizTalk, crea un puerto de envío bidireccional. Sin embargo, puede tener una orquestación que tiene un puerto de envío unidireccional. Por lo tanto, cuando una orquestación de este tipo de configurar y usar el puerto creado importando el archivo de enlace, el puerto no está disponible en la lista. Esto sucede porque el puerto lógico que creó como parte de la orquestación es un puerto unidireccional, mientras que el puerto físico que creó en la orquestación es un puerto bidireccional. En tales casos, puede editar el archivo de enlaces para realizar los siguientes cambios:  
  
    |Para|Haga esto|  
    |--------------|-------------|  
    |Para editar el archivo de enlaces de puerto para configurar un puerto de envío unidireccional|-En el extracto siguiente, cambie el valor de **IsTwoWay** propiedad **false**. Originalmente, se establece en **true**.<br /><br /> `<SendPort Name="port_name" IsStatic="true" IsTwoWay="false" BindingOption="0">`<br /><br /> -Comente los extractos de siguientes:<br /><br /> `<ReceivePipeline Name="Microsoft.BizTalk.DefaultPipelines.XMLReceive"    FullyQualifiedName="Microsoft.BizTalk.DefaultPipelines.XMLReceive,    Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral,    PublicKeyToken=token" Type="1" TrackingOption="None" Description=""/>`<br /><br /> `<ReceivePipelineData xsi:nil="true" />`|  
  
## <a name="configuring-a-wcf-siebel-port-using-the-port-binding-file-generated-using-consume-adapter-service-add-in"></a>Configurar un puerto de WCF-Siebel mediante el archivo de enlace de puerto generado mediante Consume Adapter Service complemento  
 El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] también crea un archivo de enlace de puerto que se puede importar en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Puede usar el mismo archivo de enlace de puerto para crear el puerto de BizTalk WCF-Siebel en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Sin embargo, antes de crear el puerto de WCF-Siebel debe realizar las siguientes tareas para modificar el archivo de enlace de puerto.  
  
1.  Abra el archivo de enlace de puerto en un editor de texto.  
  
2.  Buscar y reemplazar "WCF-Custom" con el nombre con el que agregó el adaptador de WCF-Siebel [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Por ejemplo, si ha agregado el adaptador de WCF-Siebel como "SiebelAdapter", reemplace "WCF-Custom" con "SiebelAdapter".  
  
3.  Busque el atributo "ConfigurationClsid" y reemplace el valor existente del atributo con "7971A78D-AE8F-42B4-834D-3A957FD945E9".  
  
4.  Guarde y cierre el archivo de enlace.  
  
5.  Importar el archivo de enlace en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Vea [reutilizar enlaces del adaptador en el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md). 
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para crear aplicaciones de BizTalk con el Siebel 

adaptador] (.. /.. / adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)