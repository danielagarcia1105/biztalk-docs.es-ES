---
title: "Configurar un enlace de puerto físico mediante un archivo de enlace de puerto a Oracle E-Business Suite | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c3c468e-815c-4611-879c-8da9111eeb3b
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a6f582733b6ff545e96c671d7c98f58c211e6ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-e-business-suite"></a>Configurar un enlace de puerto físico mediante un archivo de enlace de puerto a Oracle E-Business Suite
Cuando se usa el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para generar metadatos para los artefactos de Oracle E-Business Suite, distinto de los archivos de esquema, el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] también genera un archivo de enlace de puerto. Puede importar este archivo de enlace en la aplicación de BizTalk para crear un envío físico o puerto de recepción. Para obtener instrucciones sobre cómo importar archivos de enlace, consulte [reutilizar enlaces del adaptador con Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md). Si importa este archivo de enlace, no es necesario crear manualmente un envío físico, o puerto de recepción.  
  
> [!IMPORTANT]
>  Al usar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], si no especifica un valor para una propiedad de enlace de tipo cadena y cuyo valor predeterminado es null, a continuación, que enlaza la propiedad no estará disponible en el archivo de enlace. Debe agregar manualmente la propiedad de enlace y su valor en el archivo de enlace, si es necesario.  
  
 Crear un puerto mediante el archivo de enlace de puerto siempre crea un puerto de envío bidireccional o puerto de recepción de un sentido. Si desea crear un puerto de envío unidireccional, puede crearla manualmente siguiendo el procedimiento que se menciona en [configurar manualmente un puerto físico enlazado con el adaptador de Oracle E-Business](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md). O bien puede seguir las soluciones alternativas que se documentan en este tema para modificar el archivo de enlace de puerto para crear puertos de envío unidireccionales.  
  
> [!NOTE]
>  Para las operaciones de entrada, el archivo de enlace de puerto siempre creará un puerto de recepción unidireccional. Esto es porque el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] solo admite unidireccional puerto de recepción para las operaciones de entrada.  
  
> [!IMPORTANT]
>  Mediante el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] no crea un archivo de enlace de puerto con la que puede crear un puerto de WCF-OracleEBS. Sin embargo, podría realizar algunos cambios en el archivo de enlace de puerto generado por el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y usarlo para crear un puerto de WCF-OracleEBS. Para obtener más información, consulte [configurar un puerto de WCF-OracleEBS con el complemento de puerto de enlace archivo generado utilizando Consume Adapter Service](#BKMK_ModifyBinding).  
  
 Estos son algunos puntos clave que debe comprender en relación con el enlace de archivos que el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] genera:  
  
-   Los archivos se crean con una convención de nomenclatura específica. Si ha generado metadatos para las operaciones de salida, es decir, para enviar mensajes a Oracle E-Business Suite, el nombre del archivo WcfSendPort_OracleEBSBinding_Custom.bindinginfo.xml.  
  
     Si ha generado metadatos para operaciones de entrada, es decir, para recibir mensajes desde Oracle E-Business Suite, el nombre del archivo WcfReceivePort_OracleEBSBinding_Custom.bindinginfo.xml.  
  
-   El archivo contiene información sobre la configuración de enlace, el tipo de enlace, el URI del extremo y la acción de puerto basándose en las operaciones para el que se generan los metadatos. Al importar este archivo de enlace en la aplicación de BizTalk para crear un puerto, toda la información relevante necesaria para configurar un puerto físico se establece automáticamente en el puerto.  
  
    > [!IMPORTANT]
    >  De forma predeterminada, se asigna la acción en el puerto de envío para el nombre de la operación para el que generar metadatos. Por ejemplo, si genera metadatos para la operación de inserción en la tabla de interfaz (p. ej. FA_BOOKS), la acción en el puerto se establece en `<Operation Name="Insert" Action="InterfaceTables/Insert/OFA/FA/FA_BOOKS" />`. Sin embargo, el nombre de la operación en el puerto de envío lógico que se crea en la orquestación de BizTalk podría no ser el mismo. Debe asegurarse de que el nombre de la operación en la lógica de envío puerto (en la orquestación de BizTalk) y puerto de envío físico (en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración) son los mismos. De lo contrario, recibirá un error al enviar mensajes a Oracle E-Business Suite a través del puerto de envío.  
  
-   Basta con proporcionar las credenciales para el puerto para conectarse a Oracle E-Business Suite. Aunque el archivo de enlace conservar el nombre de usuario con el que se va a conectar, por motivos de seguridad del archivo de enlace no contiene la contraseña.  
  
## <a name="key-considerations-for-using-the-port-binding-file"></a>Consideraciones claves para utilizar el archivo de enlace de puerto  
  
-   Cuando se importa el archivo de enlace, podría obtener un mensaje de cuadro de diálogo en el que se indica que el nombre de la aplicación de BizTalk en el archivo de enlace no coincide con el nombre de la aplicación a la que va a importar el archivo de enlace. Puede omitir este mensaje y continuar.  
  
-   El archivo de enlace también contiene los nombres de puertos y ubicaciones de recepción. Si la aplicación de BizTalk al que va a importar el archivo de enlace crea un puerto o una ubicación de recepción que tiene el mismo nombre que un puerto ya existente en la misma aplicación de BizTalk, obtendrá un error. Debe editar manualmente el archivo de enlace para especificar un nombre único para los puertos o ubicaciones de recepción.  
  
-   El archivo de enlace también contiene información sobre el URI de conexión. Si el archivo de enlace crea una ubicación de recepción que tiene el mismo URI de recepción como una ubicación de recepción ya existente en la misma aplicación de BizTalk, obtendrá un error. Debe editar manualmente el archivo de enlace para especificar un URI único.  
  
-   De forma predeterminada, el archivo de enlace de puerto para las operaciones de salida siempre contiene definiciones para un puerto de envío bidireccional. Al importar este archivo en una aplicación de BizTalk, crea un puerto de envío bidireccional. Sin embargo, puede tener una orquestación que tiene un puerto de envío unidireccional. Por lo tanto, cuando una orquestación de este tipo de configurar y usar el puerto creado importando el archivo de enlace, el puerto no está disponible en la lista. Esto sucede porque el puerto lógico que creó como parte de la orquestación es un puerto unidireccional, mientras que el puerto físico que creó en la orquestación es un puerto bidireccional. En tales casos, puede editar el archivo de enlace para que los cambios siguientes:  
  
    |Para|Haga esto|  
    |--------------|-------------|  
    |Para editar el archivo de enlace de puerto para configurar un puerto de envío unidireccional|1.  En el extracto siguiente, cambie el valor de la **IsTwoWay** propiedad **false**. Originalmente, se establece en **true**.<br />     `<SendPort Name="port_name" IsStatic="true" IsTwoWay="false " BindingOption="0">`<br />2.  Comente los extractos de siguientes:<br />     `<ReceivePipeline Name="Microsoft.BizTalk.DefaultPipelines.XMLReceive"   FullyQualifiedName="Microsoft.BizTalk.DefaultPipelines.XMLReceive,   Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral,   PublicKeyToken= token" Type="1" TrackingOption="None" Description=""/>`<br />     `<ReceivePipelineData xsi:nil="true" />`|  
  
    > [!IMPORTANT]
    >  Para las operaciones de entrada, el archivo de enlace de puerto siempre creará un puerto de recepción unidireccional. Esto es porque el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] solo admite unidireccional puerto de recepción para las operaciones de entrada.  
  
##  <a name="BKMK_ModifyBinding"></a>Configurar un puerto de WCF-OracleEBS mediante el archivo de enlace de puerto generado mediante Consume Adapter Service complemento  
 El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] crea un archivo de enlace de puerto que se puede importar en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Puede usar el mismo archivo de enlace de puerto para crear el puerto de BizTalk WCF-OracleEBS en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Sin embargo, antes de crear el puerto de WCF-OracleEBS debe realizar las siguientes tareas para modificar el archivo de enlace de puerto.  
  
1.  Abra el archivo de enlace de puerto en un editor de texto.  
  
2.  Buscar y reemplazar "WCF-Custom" con el nombre con el que agregó el adaptador de WCF-OracleEBS [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Por ejemplo, si ha agregado el adaptador de WCF-OracleEBS como "OracleEBSAdapter", reemplace "WCF-Custom" con "OracleEBSAdapter".  
  
3.  Busque el atributo "ConfigurationClsid" y reemplace el valor existente del atributo con "F452BB15-7A0D-495d-9395-C630D3FD29CD".  
  
4.  Guarde y cierre el archivo de enlace.  
  
5.  Importar el archivo de enlace en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener instrucciones sobre cómo importar el archivo de enlace, consulte [reutilizar enlaces del adaptador con Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md).  
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para crear aplicaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)