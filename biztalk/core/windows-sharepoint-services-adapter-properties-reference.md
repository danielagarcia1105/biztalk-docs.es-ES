---
title: Referencia de las propiedades de adaptador de servicios de Windows SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c64c43ac-05bb-427c-987a-71663ae8e43d
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5d3992f96f99e9c8164ab7c5190e289eb347cbb
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "50753068"
---
# <a name="windows-sharepoint-services-adapter-properties-reference"></a>Referencia a las propiedades del adaptador de Windows SharePoint Services
Las siguientes propiedades del adaptador de Windows SharePoint Services se promocionan en BizTalk Server o se utilizan para especificar opciones de configuración de puerto de envío para los mensajes salientes. Las propiedades pueden utilizarse para tener acceso a información de Windows SharePoint Services relativa al mensaje, o para proporcionar al adaptador de Windows SharePoint Services información procedente de una orquestación.  
  
## <a name="message-property-precedence"></a>Prioridad de las propiedades de mensaje  
 Hay una regla de prioridad que rige las propiedades de mensaje definidas en orquestaciones y puertos de envío.  
  
 Las reglas son las siguientes:  
  
1.  Propiedad definida en la orquestación, en PropertiesXML.  
  
2.  Propiedad definida en la orquestación.  
  
3.  Propiedad definida en el nivel del puerto de envío, en la colección Nombre de propiedad u Origen de propiedad.  
  
4.  Propiedad definida en el nivel de puerto de envío.  
  
## <a name="considerations-and-known-issues"></a>Consideraciones y problemas conocidos  
 A continuación se enumeran algunas consideraciones sobre las propiedades del adaptador de Windows SharePoint Services:  
  
-   La lista de propiedades de las orquestaciones se combina con las propiedades definidas por el puerto en función de la posición de la propiedad. En caso de conflicto, la propiedad de orquestación tendrá prioridad sobre la propiedad del puerto de envío.  
  
## <a name="property-types"></a>Tipos de propiedades  
  
|Tipo de propiedad|Descripción|  
|-------------------|-----------------|  
|**IN**|Las propiedades IN son propiedades de BizTalk Server que obtienen su valor de Windows SharePoint Services. **Nota:** no debe modificar estas propiedades en las orquestaciones.|  
|**CONFIGURACIÓN**|Las propiedades CONFIG son propiedades que obtienen su valor a partir de orquestaciones o canalizaciones personalizadas de BizTalk. Este valor lo utiliza el adaptador de Windows SharePoint Services al determinar el destino de los mensajes salientes. Las propiedades CONFIG permiten especificar el valor de algunas de las propiedades de una orquestación o canalización personalizada que, en otro caso, tendrían que definirse en el puerto de envío. Las propiedades que no empiezan por IN o CONFIG son al mismo tiempo IN y CONFIG, excepto en el caso de la propiedad URL.|  
|**PROMOCIONADA**|Las propiedades PROMOTED pueden utilizarse para el enrutamiento por contenidos (CBR). Las propiedades no marcadas como PROMOTED no pueden ser utilizadas por CBR. **Nota:** aunque todas las propiedades de adaptador aparecen en el editor de filtro CBR, sólo las propiedades promocionadas pueden usarse para CBR.|  
|**ESPECIAL**|N/D|  
  
> [!NOTE]
>  Todas las propiedades que existen en el `http://schemas.microsoft.com/BizTalk/2006/WindowsSharePointServices-properties` espacio de nombres y son accesibles desde un orquestación o puerto de envío de filtro mediante la `WSS.<WSS_Property_Name>` sintaxis.  
  
## <a name="property-list"></a>Lista de propiedades  
  
|Columna estándar de Windows SharePoint Services|Nombre y tipo de propiedad de Windows SharePoint Services|Tipo|Descripción|Tipo de propiedad|  
|-------------------------------------------------|--------------------------------------------------------|----------|-----------------|-------------------|  
|Nombre|Nombre de archivo|xs:string|Nombre de archivo con extensión de archivo de Windows SharePoint Services. Los nombres de archivo, incluidas las extensiones, son exclusivos en cada biblioteca de documentos.|IN/CONFIG/ PROMOTED|  
|N/D|Url|xs:string|URL del archivo.|IN/PROMOTED|  
|N/D|TransmittedFileLocation|N/D|Esta propiedad la utiliza Supervisión de la actividad económica (BAM) con fines de integración, y no está disponible en las orquestaciones.|SPECIAL|  
|N/D|InArchivedMsgUrl|xs:string|URL del archivo en la biblioteca de documentos de archivo. Esta propiedad no estará disponible si la ubicación de recepción no archiva el mensaje.|IN/PROMOTED|  
|Tipo|InIconUrl|xs:string|URL del icono de Windows SharePoint Services que se utiliza para representar el documento.|IN|  
|Title|InTitle|xs:string|Título del archivo de Windows SharePoint Service. El título es distinto del nombre de archivo. Los títulos no tienen que ser exclusivos para cada biblioteca de documentos.|IN/PROMOTED|  
|Modificado|InLastModified|xs:dateTime|Fecha de la última de modificación de Windows SharePoint Service.|IN/PROMOTED|  
|Modificado por|InLastModifiedBy|xs:string|Nombre del último usuario que modificó el archivo.|IN/PROMOTED|  
|Id.|InItemId|xs:int|El identificador del archivo. Se trata de un número entero, exclusivo para cada biblioteca de documentos, y que puede utilizarse para tener acceso al archivo.|IN|  
|Editar|InEditUrl|xs:string|URL a la que se puede tener acceso para editar las propiedades del archivo.|IN|  
|Creado|InCreated|xs:dateTime|Fecha en que se creó el archivo de Windows SharePoint Service.|IN/PROMOTED|  
|Creado por|InCreatedBy|xs:string|Usuario que creó el archivo.|IN/PROMOTED|  
|Tamaño de archivo|InFileSize|xs:int|Tamaño del archivo de Windows SharePoint Services.|IN|  
|N/D|InListName|xs:string|Nombre de la biblioteca de documentos donde se encuentra ubicado el archivo.|IN/PROMOTED|  
|N/D|InListUrl|xs:string|URL de la biblioteca de documentos, o carpeta de la biblioteca de documentos en la que se encuentra ubicado el archivo.|IN|  
|N/D|InPropertiesXml|xs:string|Documento XML sin formato que contiene todas las columnas estándar y definidas por el usuario de Windows SharePoint Services. Permite tener acceso a cualquier valor de columna de Windows SharePoint Services procedente de una orquestación, incluso a los valores de las columnas definidas por el usuario. **Nota:** no tiene la limitación de 16 columnas. **Nota:** ver el valor InPropertiesXml de ejemplo en la sección siguiente de este tema.|IN|  
|N/D|InOfficeIntegration|xs:string|Se basa en el valor de la ubicación de recepción. Esto es `yes`, `no` o `optional`.|IN|  
|N/D|ConfigOverwrite|xs:string|"Sí" sobrescribe los archivos ya existentes con el mismo nombre. "No" genera un error si existe un archivo con el mismo nombre. "Cambiar nombre" cambia el nombre de archivo por un nombre exclusivo, anexándole una secuencia exclusiva. **Nota:** esto es similar del campo 'Sobrescribir' para puertos de envío físicos. **Nota:** 'Orquestación' no es un valor válido para este campo.|CONFIG|  
|N/D|ConfigNamespaceAliases|xs:string|Definiciones de alias de los XPATH.|CONFIG|  
|N/D|ConfigOfficeIntegration|xs:string|Defínalo como 'Sí' si es necesario llamar a OfficeImporters. Defínalo como “No” para utilizar el mensaje tal como está. “Opcional” equivale a “Sí” cuando se encuentra la solución IP, y a “No” en caso contrario. **Nota:** esto es similar del campo 'Integración con Microsoft Office' para puertos de envío físicos. **Nota:** 'Orquestación' no es un valor válido para este campo.|CONFIG|  
|N/D|ConfigTemplatesDocLib|xs:string|Nombre de la biblioteca de documentos de reserva. Es la segunda ubicación de búsqueda. **Nota:** esto es similar del campo de la biblioteca de documentos de reserva de plantillas para puertos de envío físicos.|CONFIG|  
|N/D|ConfigTemplatesNamespaceCol|xs:string|Nombre de columna de espacio de nombres de la biblioteca de documentos de reserva. **Nota:** esto es similar del campo 'Columna Namespace de reserva de plantillas' para puertos de envío físicos.|CONFIG|  
|N/D|ConfigCustomTemplatesDocLib|xs:string|Nombre de la biblioteca de documentos principales. Es la primera ubicación de búsqueda. **Nota:** esto es similar al campo biblioteca de documentos de plantillas para puertos de envío físicos.|CONFIG|  
|N/D|ConfigCustomTemplatesNamespaceCol|xs:string|Nombre de columna de espacio de nombres de la biblioteca de documentos principales. **Nota:** esto es similar del campo de columna Namespace de plantillas para puertos de envío físicos.|CONFIG|  
|N/D|ConfigPropertiesXml|xs:string|Documento XML sin formato que contiene todos los nombres de columna de Windows SharePoint Services, así como los valores que van a actualizarse en Windows SharePoint Services. Permite a un programador de orquestaciones definir los valores de columnas de SharePoint del próximo mensaje que se cree en SharePoint. **Nota:** esto es similar a la funcionalidad disponible a través de la columna n y puertos de envío de campos de columna n valor para máquina física. **Nota:** tiene un límite de 16 columnas. **Nota:** ver el valor ConfigPropertiesXml de ejemplo más adelante en este tema.|CONFIG|  
|N/D|ConfigTimeout|xs:int|Tiempo de espera en milisegundos para llamadas a servicio Web.|CONFIG|  
|N/D|ConfigAdapterWSPort|xs:int|Puerto o sitio Web de IIS en el que se ha instalado y configurado el adaptador. **Nota:** un valor de configuración de puerto no válido en una orquestación suspenderá el mensaje incluso si el valor del puerto de envío físico invalida el valor de la orquestación definido.|CONFIG|  
  
## <a name="sample-inpropertiesxml"></a>InPropertiesXml de ejemplo  
 A continuación se muestra un XML de ejemplo para InPropertiesXml.  
  
```  
<InPropertiesXml>  
     <Property name="InItemId">2</Property>  
     <Property name="Created">12/14/2004 1:30:31 PM</Property>  
     <Property name="Author">3;#John Doe</Property>  
     <Property name="Modified">12/14/2004 1:30:31 PM</Property>  
     <Property name="Editor">3;#John Doe</Property>  
     <Property name="_ModerationStatus">0</Property>  
     <Property name="_ModerationComments" />  
     <Property name="FileRef">/sites/BASSite/SourceLibrary/PO1.xml</Property>  
     <Property name="FileDirRef">2;#sites/BASSite/SourceLibrary</Property>  
     <Property name="InLastModified">2004-12-14 13:30:31</Property>  
     <Property name="InCreated">2004-12-14 13:30:31</Property>  
     <Property name="InFileSize">7338</Property>  
     <Property name="FSObjType">0</Property>  
     <Property name="CheckedOutUserId">2;#3</Property>  
     <Property name="Filename">PO1.xml</Property>  
     <Property name="VirusStatus">2;#7338</Property>  
     <Property name="CheckedOutTitle">2;#John Doe</Property>  
     <Property name="LinkCheckedOutTitle">John Doe</Property>  
     <Property name="InLastModifiedBy">MyDomain\jdoe</Property>  
     <Property name="InCreatedBy">MyDomain\jdoe</Property>  
     <Property name="owshiddenversion">1</Property>  
     <Property name="File_x0020_Type">xml</Property>  
     <Property name="HTML_x0020_File_x0020_Type" />  
     <Property name="_SourceUrl" />  
     <Property name="_SharedFileIndex" />  
     <Property name="LinkFilenameNoMenu">PO1.xml</Property>  
     <Property name="LinkFilename">PO1.xml</Property>  
     <Property name="SelectTitle">2</Property>  
     <Property name="SelectFilename">2</Property>  
     <Property name="Edit">xml</Property>  
     <Property name="InIconUrl">/sites/BASSite/SourceLibrary/PO1.xml</Property>  
     <Property name="Url">http://localhost:80/sites/BASSite/SourceLibrary/PO1.xml</Property>  
     <Property name="EncodedAbsUrl">PO1</Property>  
     <Property name="BaseName">7338</Property>  
     <Property name="FileSizeDisplay" />  
     <Property name="InstanceID">200</Property>  
     <Property name="Order" />  
     <Property name="InTitle" />  
     <Property name="ColumnOne" />  
     <Property name="ColumnTwo" />  
     <Property name="ColumnThree" />  
     <Property name="ColumnFour" />  
     <Property name="InListName">SourceLibrary</Property>  
     <Property name="InListUrl">http://localhost:80/sites/BASSite/SourceLibrary</Property>  
     <Property name="InEditUrl">http://localhost:80/sites/BASSite/SourceLibrary/Forms/EditForm.aspx?ID=2</Property>  
     <Property name="InOfficeIntegration">yes</Property>  
</InPropertiesXml>  
```  
  
## <a name="sample-configpropertiesxml"></a>Ejemplo de ConfigPropertiesXml  
 A continuación se muestra un XML de ejemplo para ConfigPropertiesXml.  
  
```  
<ConfigPropertiesXml>  
     <PropertyName1>PO number</PropertyName1>  
     <PropertySource1>%XPATH=//orchns:PurchaseOrder/orchns:Header/orchns:ID%</PropertySource1>  
     <PropertyName2>Charge To</PropertyName2>  
     <PropertySource2>%XPATH=//orchns:PurchaseOrder/orchns:orderBody/orchns:chargeTo%</PropertySource2>  
     <PropertyName3>PO Priority</PropertyName3>  
     <PropertySource3>%XPATH=//orchns:PurchaseOrder/orchns:orderBody/orchns:priority%</PropertySource3>  
     <PropertyName4>Order Date</PropertyName4>  
     <PropertySource4>%XPATH=//orchns:PurchaseOrder/orchns:orderBody/orchns:dateOrdered%</PropertySource4>  
</ConfigPropertiesXml>  
```  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar Windows SharePoint Services ubicación de recepción](../core/how-to-configure-a-windows-sharepoint-services-receive-location.md)   
 [Cómo configurar un controlador de envío de Windows SharePoint Services](../core/how-to-configure-a-windows-sharepoint-services-send-handler.md)   
 [Cómo configurar un puerto de envío de Windows SharePoint Services](../core/how-to-configure-a-windows-sharepoint-services-send-port.md)   
 [Cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md)   
 [Expresiones del adaptador de Windows SharePoint Services](../core/windows-sharepoint-services-adapter-expressions.md)   
 [Tipos de columna admitidos de Windows SharePoint Services](../core/supported-windows-sharepoint-services-column-types.md)
