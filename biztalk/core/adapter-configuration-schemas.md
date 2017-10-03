---
title: "Esquemas de configuración de adaptador | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc08fa71-c5f7-4365-9506-e02351b17567
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2afa0e2f06471d90326b0dd8e2b83b8d4c38a82b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-configuration-schemas"></a>Esquemas de configuración del adaptador
En la configuración en tiempo de diseño de un adaptador se emplean diferentes tipos de esquemas, que se usan y modifican en función de la visibilidad y del ámbito de los valores de las propiedades.  
  
## <a name="handler-schemas"></a>Esquemas de controlador  
 La configuración del adaptador que proviene de un controlador se aplica al adaptador y a todos sus clientes en un ámbito global. Un administrador estáticamente puede modificar la configuración del controlador en tiempo de diseño mediante la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración para expandir el adaptador de recepción o controlador de envío y mostrar las propiedades del host especificado.  
  
 El adaptador de archivo de ejemplo incluido en el SDK tiene un conjunto de archivos XSD que se usan para configurar la ubicación de recepción, el puerto de envío, el controlador de recepción y el controlador de envío. Modifique estos archivos XSD para que el adaptador personalizado reciba las propiedades de configuración necesarias. Los archivos incluidos en el adaptador de archivo de ejemplo que debe modificar son los archivos de esquema TransmitHandler.xsd y ReceiveHandler.xsd. Estos archivos configuran el controlador de envío y controlador de recepción, respectivamente, mediante el control de las páginas de propiedades que se usa para configurar los controladores de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
 Utilice los requisitos del adaptador para crear una lista de propiedades de configuración necesarias para cada uno de los extremos. Si todas las propiedades de configuración son globales, puede que solo tenga que modificar las configuraciones de los puertos de envío y de recepción. Si es necesario establecer las propiedades del adaptador para cada puerto de envío o cada ubicación de recepción, tendrá que modificar también los archivos de configuración de la ubicación de recepción y del puerto de envío.  
  
 El marco de trabajo de adaptadores proporciona extensiones de esquema y opciones avanzadas de configuración con el fin de admitir los requisitos de configuración comunes del adaptador. También proporciona extensiones que no se incluyen en el esquema que acompaña al adaptador de archivo de ejemplo. Para obtener más información acerca de las extensiones de esquema de marco de trabajo, consulte [extensiones de esquema de configuración de adaptador Framework](../core/adapter-framework-configuration-schema-extensions.md). Para obtener más información acerca de las opciones de configuración avanzada, como los editores desplegables personalizados y convertidores de tipos personalizados, vea [componentes avanzados de configuración de adaptadores](../core/advanced-configuration-components-for-adapters.md).  
  
 El código que se incluye al final de este tema proviene del archivo TransmitHandler.xsd y crea la siguiente página de propiedades.  
  
 ![](../core/media/ebiz-prog-custad-sh.gif "ebiz_prog_custad_sh")  
Página de propiedades del controlador de envío creada por el archivo TransmitHandler.xsd  
  
 Tenga en cuenta el uso de la \<Designer >, \<BAF: DisplayName >, y \<BAF: Description > etiquetas en el código de TransmitHandler.xsd que se muestra a continuación. Son decoraciones personalizadas proporcionadas por el marco de trabajo de adaptadores para acelerar la generación de estas páginas de propiedades.  
  
 Para obtener una lista de todas las decoraciones disponibles para su uso en el marco de trabajo, consulte [etiquetas de decoración de esquema de configuración de adaptador Framework](../core/adapter-framework-configuration-schema-decoration-tags.md).  
  
 Observe que el esquema solo tiene un elemento y que no contiene un elemento de URI.  
  
> [!IMPORTANT]
>  No almacene datos reservados de los clientes en el esquema de adaptador predeterminado. Por motivos de seguridad, configure la información de nombre de usuario y de contraseña una vez implementado un adaptador. De este modo se garantiza que la información quede almacenada en la base de datos de Inicio de sesión único (SSO) empresarial. Para obtener más información acerca de la base de datos SSO, vea [mediante SSO](../core/using-sso.md).  
  
```  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:baf="BiztalkAdapterFramework.xsd"   
xmlns:b="http://schemas.microsoft.com/BizTalk/2003"   
xmlns="http://tempuri.org/XMLSchema1.xsd"   
elementFormDefault="qualified" targetNamespace="http://tempuri.org/XMLSchema1.xsd"   
id="TransmitHandler" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="Config">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element default="50" name="sendBatchSize" type="xs:int" >  
      <xs:annotation>  
         <xs:appinfo>  
            <baf:designer>  
               <baf:displayname _locID="sendBatchSizeName">Batch Size</baf:displayname>  
               <baf:description _locID="sendBatchSizeDesc">Enter the   
maximum number of files to be transmitted per batch</baf:description>  
            </baf:designer>  
         </xs:appinfo>  
      </xs:annotation>  
   </xs:element>  
  
        <xs:element default="4096" name="bufferSize" type="xs:int" >  
      <xs:annotation>  
         <xs:appinfo>  
            <baf:designer>  
               <baf:displayname _locID="bufferSizeName">Write Buffer Size</baf:displayname>  
               <baf:description _locID="bufferSizeDesc">Enter the size of   
the buffer used to write the file</baf:description>  
            </baf:designer>  
         </xs:appinfo>  
      </xs:annotation>  
   </xs:element>  
  
        <xs:element default="1" name="threadsPerCPU" type="xs:int" >  
      <xs:annotation>  
         <xs:appinfo>  
            <baf:designer>  
               <baf:displayname _locID="threadsPerCPUName">Threads Per CPU</baf:displayname>  
               <baf:description _locID="threadsPerCPUDesc">Enter the   
number of threads per CPU to execute in the thread pool</baf:description>  
            </baf:designer>  
         </xs:appinfo>  
      </xs:annotation>  
   </xs:element>  
  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
## <a name="send-port-and-receive-location-schemas"></a>Esquemas de puerto de envío y de ubicación de recepción  
 Para establecer las propiedades específicas de los puertos del adaptador, modifique los esquemas de configuración de la ubicación de recepción y del puerto de envío. Los archivos de esquema TransmitLocation.xsd y ReceiveLocation.xsd configuran el puerto de envío y la ubicación de recepción respectivamente.  
  
 El marco de trabajo de adaptadores proporciona extensiones de esquema y opciones avanzadas de configuración con el fin de admitir los requisitos de configuración comunes del adaptador. Para obtener más información acerca de las extensiones de esquema de marco de trabajo, consulte [extensiones de esquema de configuración de adaptador Framework](../core/adapter-framework-configuration-schema-extensions.md). Para obtener más información acerca de las opciones de configuración avanzada, como los editores desplegables personalizados y convertidores de tipos personalizados, vea [componentes avanzados de configuración de adaptadores](../core/advanced-configuration-components-for-adapters.md).  
  
 El código que se incluye a continuación proviene del archivo TransmitLocation.xsd y crea la siguiente página de propiedades.  
  
 ![](../core/media/ebiz-prog-custad-sp.gif "ebiz_prog_custad_sp")  
Ilustra la página de propiedades del puerto de envío para el adaptador de archivo de ejemplo  
  
 Tenga en cuenta en el archivo TransmitLocation.xsd siguiente que contiene la configuración del puerto de envío el \<Designer >, \<BAF: DisplayName >, y \<BAF: Description > etiquetas, al igual que el controlador de envío, además de usar el \<Category > etiqueta. La etiqueta de categoría permite agrupar propiedades. Si tiene más de una categoría, la categoría se puede expandir y contraer y aparece en forma de encabezado de color gris encima de las propiedades de dicha categoría. Para obtener más información, consulte [extensiones de esquema de configuración de adaptador Framework](../core/adapter-framework-configuration-schema-extensions.md).  
  
 Este esquema también contiene un campo de URI, que se rellena en la página que aparece después de especificar toda la información del campo en la página de propiedades del puerto de envío durante el proceso de validación que realiza el adaptador.  
  
```  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:baf="BiztalkAdapterFramework.xsd" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" xmlns="http://tempuri.org/XMLSchema1.xsd" elementFormDefault="qualified" targetNamespace="http://tempuri.org/XMLSchema1.xsd" id="TransmitLocation" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="Config">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="directory" type="xs:string">  
      <xs:annotation>  
         <xs:appinfo>  
            <baf:designer xmlns:baf="BiztalkAdapterFramework.xsd">  
               <baf:displayname _locID="sendDirectoryName">Directory</baf:displayname>  
               <baf:description _locID="sendDirectoryDesc">Directory to write the file to</baf:description>  
                         <baf:category _locID="transmitLocationCategory">Transmit Location</baf:category>  
                    </baf:designer>  
         </xs:appinfo>  
      </xs:annotation>  
        </xs:element>  
  
        <xs:element default="%MessageID%.xml" name="fileName" type="xs:string">  
          <xs:annotation>  
            <xs:appinfo>  
              <baf:designer xmlns:baf="BiztalkAdapterFramework.xsd">  
                <baf:displayname _locID="fileNameName">File Name</baf:displayname>  
      <baf:description _locID="fileNameDesc">The name of the file that will be written</baf:description>  
                <baf:category _locID="transmitLocationCategory">Transmit Location</baf:category>  
              </baf:designer>  
            </xs:appinfo>  
          </xs:annotation>  
        </xs:element>  
  
        <xs:element default="2" name="fileCopyMode" type="CopyMode">  
          <xs:annotation>  
            <xs:appinfo>  
              <baf:designer xmlns:baf="BiztalkAdapterFramework.xsd">  
                <baf:displayname _locID="fileCopyModeName">File Mode</baf:displayname>  
                <baf:category _locID="transmitLocationCategory">Transmit Location</baf:category>  
              </baf:designer>  
            </xs:appinfo>  
          </xs:annotation>  
        </xs:element>  
  
        <xs:element name="uri" type="xs:string">  
          <xs:annotation>  
            <xs:appinfo>  
              <baf:designer xmlns:baf="BiztalkAdapterFramework.xsd">  
                <baf:browsable show="false" />  
              </baf:designer>  
            </xs:appinfo>  
          </xs:annotation>  
        </xs:element>  
  
   <!-- An example of how an SSO affiliate application would be configured for this endpoint: -->  
   <!--  
   <xs:element name="ssoAffiliateApplication" type="baf:SSOList">  
      <xs:annotation>  
         <xs:appinfo>  
            <baf:designer>  
               <baf:displayname _locID="ssoAffiliateApplicationName">SSO Affiliate</baf:displayname>  
               <baf:description _locID="ssoAffiliateApplicationDesc">The Single Sign On (SSO) Affiliate Application</baf:description>  
               <baf:category _locID="ftpCategory">FTP</baf:category>  
            </baf:designer>  
         </xs:appinfo>  
      </xs:annotation>  
   </xs:element>  
   -->  
  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
  
  <xs:simpleType name="CopyMode">  
    <xs:restriction base="xs:int">  
      <xs:enumeration value="0">  
        <xs:annotation>  
          <xs:appinfo>  
            <baf:designer xmlns:baf="BiztalkAdapterFramework.xsd">  
              <baf:displayname _locID="appendName">Append</baf:displayname>  
            </baf:designer>  
          </xs:appinfo>  
        </xs:annotation>  
      </xs:enumeration>  
      <xs:enumeration value="1">  
        <xs:annotation>  
          <xs:appinfo>  
            <baf:designer xmlns:baf="BiztalkAdapterFramework.xsd">  
              <baf:displayname _locID="createName">Create</baf:displayname>  
            </baf:designer>  
          </xs:appinfo>  
        </xs:annotation>  
      </xs:enumeration>  
      <xs:enumeration value="2">  
        <xs:annotation>  
          <xs:appinfo>  
            <baf:designer xmlns:baf="BiztalkAdapterFramework.xsd">  
              <baf:displayname _locID="createNewName">CreateNew</baf:displayname>  
            </baf:designer>  
          </xs:appinfo>  
        </xs:annotation>  
      </xs:enumeration>  
    </xs:restriction>  
  </xs:simpleType>  
</xs:schema>  
```