---
title: Windows SharePoint Services 4.0 compatibilidad | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 84be7aa0-2ff2-4e40-9c39-5cb89549c636
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6920de947165f7f3065f190d077d55dcbef30c7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971037"
---
# <a name="windows-sharepoint-services-40-support"></a>Compatibilidad con Windows SharePoint Services 4.0
El adaptador de Windows SharePoint Services para BizTalk Server proporciona paridad de características y funcionalidades con el adaptador de Windows SharePoint Services para [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]. El adaptador de Windows SharePoint Services para BizTalk Server también admite la siguiente funcionalidad disponible con Windows SharePoint Services 4.0:  

- Enviar documentos a un sitio blog de Windows SharePoint Services 4.0.  

- Enviar mensajes a un sitio Wiki de Windows SharePoint Services 4.0 y recibirlos.  

  El adaptador de Windows SharePoint Services para BizTalk Server no proporciona soporte técnico para las siguientes características están disponibles en Windows SharePoint Services 4.0:  

- **Papelera de reciclaje**: adaptador The Windows SharePoint Services para el adaptador de BizTalk Server no admite la recepción o envío explícito de mensajes a la Papelera de reciclaje.  

- **Enumera las carpetas**: adaptador The Windows SharePoint Services para BizTalk Server puede enviar mensajes a listas pero no puede recibir mensajes de listas. Windows SharePoint Services 4.0 admite carpetas en listas pero el adaptador de Windows SharePoint Services para BizTalk Server no admite esta característica. Por lo tanto, el adaptador de Windows SharePoint Services para BizTalk Server no puede crear elementos de lista en una carpeta distinta de la carpeta raíz de la lista.  

- Las secciones siguientes describen con más detalle cómo usar el adaptador de Windows SharePoint Services para BizTalk Server para enviar mensajes a un sitio blog de Windows SharePoint Services 4.0 y cómo enviar y recibir mensajes de Windows SharePoint Services 4.0 el sitio Wiki de.  

## <a name="sending-to-a-windows-sharepoint-services-40-blog-site"></a>Enviar a un sitio blog de Windows SharePoint Services 4.0  
 En un sitio blog de Windows SharePoint Services 4.0, los envíos se almacenan en el **publicaciones** las categorías de lista y post se definen en el **categorías** lista.  

 Para enviar un mensaje a un sitio blog de Windows SharePoint Services 4.0, introduzca los siguientes valores en el adaptador **propiedades de transporte** cuadro de diálogo al configurar un puerto de envío que usa el adaptador de Windows SharePoint Services:  


|        Property        |                                                                                            Valor                                                                                            |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Dirección URL de carpeta de destino |                                            La URL de la carpeta de destino de la lista de envíos, relacionada con el sitio de SharePoint, por ejemplo, "Lists/Posts".                                            |
|  Dirección URL del sitio de SharePoint   | Dirección URL del sitio de blog de Windows SharePoint Services 4.0, por ejemplo, http://<em>\<servername\></em>/sitios/blog/donde *\<servername\>* es un marcador de posición para el nombre real del servidor Web. |

 A continuación, establezca los valores para el **categoría**, **publicada**, **título**, y **cuerpo** propiedades para el envío mediante la configuración correspondiente del blog valores de WSS. ConfigPropertiesXml la propiedad de contexto del mensaje. Esto puede hacerse con una canalización personalizada o en una orquestación. Por ejemplo, la siguiente expresión de una orquestación debería definir los valores de la propiedad de contexto WSS.ConfigPropertiesXml del mensaje Message_Out.  

```  
int_Category = 1;  
str_Published = Microsoft.SharePoint.Utilities.SPUtility.CreateISO8601DateTimeFromSystemDateTime(System.DateTime.Now);  
// requires a reference to Microsoft.SharePoint.dll  
str_Title = "This is the title of the post from the WSS adapter";  
str_Body = "This is the body of the post from the WSS adapter";  

Message_Out(WSS.ConfigPropertiesXml) = “<ConfigPropertiesXml>  
<PropertyName1>Category</PropertyName1>  
<PropertySource1>” + int_Category + “</PropertySource1>  
<PropertyName2>Published</PropertyName2>  
<PropertySource2>” + str_Published + “</PropertySource2>  
<PropertyName3>Title</PropertyName3>  
<PropertySource3>” + str_Title + “</PropertySource3>  
<PropertyName4>Body</PropertyName4>  
<PropertySource4>” + str_Body + “</PropertySource4>  
</ConfigPropertiesXml>”;  
```  

 Todas las variables de esta expresión deberían utilizar los siguientes tipos:  

|Nombre de variable|Tipo|  
|-------------------|----------|  
|int_Category|System.Int32|  
|str_Published|System.String|  
|str_Title|System.String|  
|str_Body|System.String|  

 Una publicación creada de esta manera se establecerá en un estado de **no aprobado**, lo que requerirá aprobación por parte del propietario del blog antes de que sea visible en el sitio.  

 Los tipos de columna admitidos de la lista pueden verse en la página de configuración de la lista. Para obtener más información sobre los tipos de columna de Windows SharePoint Services que son compatibles con el adaptador de Windows SharePoint Services, consulte [referencia de propiedades de adaptador de Windows SharePoint Services](../core/windows-sharepoint-services-adapter-properties-reference.md).  

## <a name="sending-to-and-receiving-from-a-windows-sharepoint-services-40-wiki-document-library"></a>Enviar y recibir desde una biblioteca de documentos Wiki de Windows SharePoint Services 4.0  
 En un sitio de Windows SharePoint Services 4.0, un sitio Wiki utiliza el **páginas Wiki** biblioteca de documentos. La biblioteca de documentos de páginas Wiki almacena el texto de la página Wiki en una **contenido Wiki** columna que utiliza un tipo de interfaz de usuario de **varias líneas de texto**. El **varias líneas de texto** el tipo de interfaz de usuario se correlaciona con la **SPFieldType.Note** tipo de modelo de objetos de SharePoint. Para obtener más información sobre los tipos de columna de Windows SharePoint Services que son compatibles con el adaptador de Windows SharePoint Services, consulte [referencia de propiedades de adaptador de Windows SharePoint Services](../core/windows-sharepoint-services-adapter-properties-reference.md).  

### <a name="sending-to-a-windows-sharepoint-services-40-wiki-document-library"></a>Enviar a una biblioteca de documentos Wiki de Windows SharePoint Services 4.0  
 Al enviar mensajes a un sitio Wiki de Windows SharePoint Services 4.0, el contenido de la página Wiki se almacena en la propiedad de contexto del adaptador de Windows SharePoint Services denominada **WSS. ConfigPropertiesXml**. Para publicar un mensaje en un sitio Wiki de Windows SharePoint Services 4.0, introduzca los siguientes valores en el adaptador **propiedades de transporte** cuadro de diálogo al configurar un puerto de envío que usa el adaptador de Windows SharePoint Services:  


|        Property        |                                                                                            Valor                                                                                            |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Dirección URL de carpeta de destino |                                                   Dirección URL de la página de inicio del sitio Wiki, relativa al sitio de SharePoint, por ejemplo, "wikiSP".                                                    |
|  Dirección URL del sitio de SharePoint   | Dirección URL del sitio Wiki de Windows SharePoint Services 4.0, por ejemplo http://<em>\<servername\></em>/sites/wiki/donde *\<servername\>* es un marcador de posición para el nombre real del servidor web. |

 A continuación, establezca el valor de la **contenido Wiki** propiedad de la página Wiki estableciendo el valor correspondiente en WSS. ConfigPropertiesXml la propiedad de contexto del mensaje. Esto puede hacerse con una canalización personalizada o en una orquestación. Por ejemplo, la siguiente expresión de una orquestación debería definir los valores de la propiedad de contexto WSS.ConfigPropertiesXml del mensaje Message_Out:  

```  
str_Wiki = "This is a sample Wiki page entry.";  
Message_Out(WSS.ConfigPropertiesXml) = “<ConfigPropertiesXml>  
<PropertyName1>Wiki Content</PropertyName1>  
<PropertySource1>” + str_Wiki + “</PropertySource1>  
</ConfigPropertiesXml>”;  
```  

 La variable str_Wiki de esta expresión usaría el **System.String** tipo de datos.  

> [!IMPORTANT]
>  La biblioteca de documentos Wiki de Windows SharePoint Services 4.0 admite versiones; sin embargo, el adaptador de Windows SharePoint Services para BizTalk Server 2010 no admite esta característica. Por lo tanto, las páginas Wiki que son actualizadas por el adaptador de Windows SharePoint Services para BizTalk Server perderá sus versiones anteriores. Debido a esta limitación, una página Wiki que es recibida por el adaptador de Windows SharePoint Services para BizTalk Server y archivada en una biblioteca de documentos Wiki distinta, conservará únicamente su última versión, con todas las demás versiones que se va a eliminar.  

### <a name="receiving-from-a-windows-sharepoint-services-40-wiki-document-library"></a>Recibir de una biblioteca de documentos Wiki de Windows SharePoint Services 4.0  
 Cuando se reciben mensajes desde un sitio Wiki de Windows SharePoint Services 4.0, el contenido de la página Wiki se almacena dentro de la propiedad de contexto del adaptador de Windows SharePoint Services denominada **WSS. InPropertiesXml**.  

 Para recibir un mensaje de una página Wiki de Windows SharePoint Services 4.0, introduzca los valores siguientes en el adaptador **propiedades de transporte** cuadro de diálogo al configurar una ubicación de recepción que usa el adaptador de Windows SharePoint Services:  

|Property|Valor|  
|--------------|-----------|  
|Dirección URL del sitio de SharePoint|Dirección URL de la página de inicio del sitio Wiki, relativa al sitio de SharePoint, por ejemplo, "wiki".|  
|Dirección URL de la biblioteca de documentos de origen|Dirección URL de la página de inicio del sitio Wiki, relativa al sitio de SharePoint, por ejemplo, "wikiRL".|  

 A continuación, recuperar el contenido de la página wiki desde el **contenido Wiki** nodo de la **WSS. InPropertiesXml** propiedad de contexto del mensaje recibido. Esto puede hacerse con una canalización personalizada o en una orquestación. Por ejemplo, en la siguiente expresión de orquestación, el **str_Wiki** variable se rellena con el valor de la **contenido Wiki** nodo desde el **WSS. InPropertiesXml** propiedad de contexto de la **Message_In** mensaje. A continuación, la **contenido Wiki** propiedad de la **WSS. ConfigPropertiesXml** propiedad de contexto de la **Message_Out** mensajes se establece en el valor de la **str_Wiki** variable:  

```  
str_PropertiesXml = Message_In(WSS.InPropertiesXml);  
doc = doc.LoadXml(str_PropertiesXml);  
node = doc.SelectSingleNode("InPropertiesXml/Property[@name='Wiki Content']);  
str_Wiki = node.InnerText;  
Message_Out(WSS.ConfigPropertiesXml) = “<ConfigPropertiesXml>  
<PropertyName1>Wiki Content</PropertyName1>  
<PropertySource1>” + str_Wiki + “</PropertySource1>  
</ConfigPropertiesXml>”;  
```  

 Todas las variables de esta expresión deberían utilizar los siguientes tipos:  

|Nombre de variable|Tipo|  
|-------------------|----------|  
|str_PropertiesXml|System.Xml.XmlDocument|  
|doc|System.Xml.XmlDocument|  
|Nodo|System.Xml.XmlNode|  
|str_Wiki|System.String|  

## <a name="see-also"></a>Vea también  
 [Adaptador de Windows SharePoint Services](../core/windows-sharepoint-services-adapter.md)