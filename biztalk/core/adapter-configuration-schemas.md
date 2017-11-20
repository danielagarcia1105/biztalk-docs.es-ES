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
# <a name="adapter-configuration-schemas"></a><span data-ttu-id="64428-102">Esquemas de configuración del adaptador</span><span class="sxs-lookup"><span data-stu-id="64428-102">Adapter Configuration Schemas</span></span>
<span data-ttu-id="64428-103">En la configuración en tiempo de diseño de un adaptador se emplean diferentes tipos de esquemas,</span><span class="sxs-lookup"><span data-stu-id="64428-103">Different types of schemas are used in design-time configuration of an adapter.</span></span> <span data-ttu-id="64428-104">que se usan y modifican en función de la visibilidad y del ámbito de los valores de las propiedades.</span><span class="sxs-lookup"><span data-stu-id="64428-104">Depending upon the visibility and scope of property values, different schemas are modified and used.</span></span>  
  
## <a name="handler-schemas"></a><span data-ttu-id="64428-105">Esquemas de controlador</span><span class="sxs-lookup"><span data-stu-id="64428-105">Handler Schemas</span></span>  
 <span data-ttu-id="64428-106">La configuración del adaptador que proviene de un controlador se aplica al adaptador y a todos sus clientes en un ámbito global.</span><span class="sxs-lookup"><span data-stu-id="64428-106">Adapter configuration that comes from a handler applies to the adapter and all its consumers on a global scope.</span></span> <span data-ttu-id="64428-107">Un administrador estáticamente puede modificar la configuración del controlador en tiempo de diseño mediante la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración para expandir el adaptador de recepción o controlador de envío y mostrar las propiedades del host especificado.</span><span class="sxs-lookup"><span data-stu-id="64428-107">An administrator can statically alter handler configuration at design time by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to expand the adapter's receive or send handler and bring up the properties of the specified host.</span></span>  
  
 <span data-ttu-id="64428-108">El adaptador de archivo de ejemplo incluido en el SDK tiene un conjunto de archivos XSD que se usan para configurar la ubicación de recepción, el puerto de envío, el controlador de recepción y el controlador de envío.</span><span class="sxs-lookup"><span data-stu-id="64428-108">The sample file adapter included in the SDK has a set of XSD files used to configure its receive location, send port, receive handler, and send handler.</span></span> <span data-ttu-id="64428-109">Modifique estos archivos XSD para que el adaptador personalizado reciba las propiedades de configuración necesarias.</span><span class="sxs-lookup"><span data-stu-id="64428-109">Modify these XSD files so that your custom adapter receives the configuration properties it requires.</span></span> <span data-ttu-id="64428-110">Los archivos incluidos en el adaptador de archivo de ejemplo que debe modificar son los archivos de esquema TransmitHandler.xsd y ReceiveHandler.xsd.</span><span class="sxs-lookup"><span data-stu-id="64428-110">The files included with the sample file adapter that you need to modify are the TransmitHandler.xsd and ReceiveHandler.xsd schema files.</span></span> <span data-ttu-id="64428-111">Estos archivos configuran el controlador de envío y controlador de recepción, respectivamente, mediante el control de las páginas de propiedades que se usa para configurar los controladores de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="64428-111">These files configure the send handler and receive handler, respectively, by controlling the property pages used to configure the handlers in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="64428-112">Utilice los requisitos del adaptador para crear una lista de propiedades de configuración necesarias para cada uno de los extremos.</span><span class="sxs-lookup"><span data-stu-id="64428-112">Using your adapter requirements, create a list of configuration properties required for each of the endpoints.</span></span> <span data-ttu-id="64428-113">Si todas las propiedades de configuración son globales, puede que solo tenga que modificar las configuraciones de los puertos de envío y de recepción.</span><span class="sxs-lookup"><span data-stu-id="64428-113">If all of your configuration properties are global, you may only need to modify the send and receive port configurations.</span></span> <span data-ttu-id="64428-114">Si es necesario establecer las propiedades del adaptador para cada puerto de envío o cada ubicación de recepción, tendrá que modificar también los archivos de configuración de la ubicación de recepción y del puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="64428-114">If the adapter properties need to be set for each send port or receive location, you have to modify the receive location and send port configuration files as well.</span></span>  
  
 <span data-ttu-id="64428-115">El marco de trabajo de adaptadores proporciona extensiones de esquema y opciones avanzadas de configuración con el fin de admitir los requisitos de configuración comunes del adaptador.</span><span class="sxs-lookup"><span data-stu-id="64428-115">The Adapter Framework provides schema extensions and advanced configuration options to support common adapter configuration requirements.</span></span> <span data-ttu-id="64428-116">También proporciona extensiones que no se incluyen en el esquema que acompaña al adaptador de archivo de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="64428-116">It also provides extensions that are not in the schema included with the sample file adapter.</span></span> <span data-ttu-id="64428-117">Para obtener más información acerca de las extensiones de esquema de marco de trabajo, consulte [extensiones de esquema de configuración de adaptador Framework](../core/adapter-framework-configuration-schema-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="64428-117">For more information about the Adapter Framework schema extensions, see [Adapter Framework Configuration Schema Extensions](../core/adapter-framework-configuration-schema-extensions.md).</span></span> <span data-ttu-id="64428-118">Para obtener más información acerca de las opciones de configuración avanzada, como los editores desplegables personalizados y convertidores de tipos personalizados, vea [componentes avanzados de configuración de adaptadores](../core/advanced-configuration-components-for-adapters.md).</span><span class="sxs-lookup"><span data-stu-id="64428-118">For more information about advanced configuration options such as custom drop-down editors and custom type converters, see [Advanced Configuration Components for Adapters](../core/advanced-configuration-components-for-adapters.md).</span></span>  
  
 <span data-ttu-id="64428-119">El código que se incluye al final de este tema proviene del archivo TransmitHandler.xsd y crea la siguiente página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="64428-119">The code at the end of this topic is from the TransmitHandler.xsd file, and produces the following property page.</span></span>  
  
 ![](../core/media/ebiz-prog-custad-sh.gif "ebiz_prog_custad_sh")  
<span data-ttu-id="64428-120">Página de propiedades del controlador de envío creada por el archivo TransmitHandler.xsd</span><span class="sxs-lookup"><span data-stu-id="64428-120">Send handler property page created by the TransmitHandler.xsd file</span></span>  
  
 <span data-ttu-id="64428-121">Tenga en cuenta el uso de la \<Designer >, \<BAF: DisplayName >, y \<BAF: Description > etiquetas en el código de TransmitHandler.xsd que se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="64428-121">Note the use of the \<baf:designer>, \<baf:displayname>, and \<baf:description> tags in the TransmitHandler.xsd code that is shown below.</span></span> <span data-ttu-id="64428-122">Son decoraciones personalizadas proporcionadas por el marco de trabajo de adaptadores para acelerar la generación de estas páginas de propiedades.</span><span class="sxs-lookup"><span data-stu-id="64428-122">These are custom decorations provided by the Adapter Framework to make the generation of these property pages faster.</span></span>  
  
 <span data-ttu-id="64428-123">Para obtener una lista de todas las decoraciones disponibles para su uso en el marco de trabajo, consulte [etiquetas de decoración de esquema de configuración de adaptador Framework](../core/adapter-framework-configuration-schema-decoration-tags.md).</span><span class="sxs-lookup"><span data-stu-id="64428-123">For a list of all of the decorations available for use within the Adapter Framework, see [Adapter Framework Configuration Schema Decoration Tags](../core/adapter-framework-configuration-schema-decoration-tags.md).</span></span>  
  
 <span data-ttu-id="64428-124">Observe que el esquema solo tiene un elemento y que no contiene un elemento de URI.</span><span class="sxs-lookup"><span data-stu-id="64428-124">Note that the schema has only one element and does not contain a URI element.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="64428-125">No almacene datos reservados de los clientes en el esquema de adaptador predeterminado.</span><span class="sxs-lookup"><span data-stu-id="64428-125">Do not store sensitive customer data in the default adapter schema.</span></span> <span data-ttu-id="64428-126">Por motivos de seguridad, configure la información de nombre de usuario y de contraseña una vez implementado un adaptador.</span><span class="sxs-lookup"><span data-stu-id="64428-126">For security reasons, configure user name and password information only after you deploy an adapter.</span></span> <span data-ttu-id="64428-127">De este modo se garantiza que la información quede almacenada en la base de datos de Inicio de sesión único (SSO) empresarial.</span><span class="sxs-lookup"><span data-stu-id="64428-127">This ensures that the information gets stored in the Enterprise Single Sign-On (SSO) database.</span></span> <span data-ttu-id="64428-128">Para obtener más información acerca de la base de datos SSO, vea [mediante SSO](../core/using-sso.md).</span><span class="sxs-lookup"><span data-stu-id="64428-128">For more information about the SSO database, see [Using SSO](../core/using-sso.md).</span></span>  
  
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
  
## <a name="send-port-and-receive-location-schemas"></a><span data-ttu-id="64428-129">Esquemas de puerto de envío y de ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="64428-129">Send Port and Receive Location Schemas</span></span>  
 <span data-ttu-id="64428-130">Para establecer las propiedades específicas de los puertos del adaptador, modifique los esquemas de configuración de la ubicación de recepción y del puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="64428-130">To set port-specific properties for your adapter, modify the receive location and send port configuration schemas.</span></span> <span data-ttu-id="64428-131">Los archivos de esquema TransmitLocation.xsd y ReceiveLocation.xsd configuran el puerto de envío y la ubicación de recepción respectivamente.</span><span class="sxs-lookup"><span data-stu-id="64428-131">The TransmitLocation.xsd and ReceiveLocation.xsd schema files configure the send port and receive location, respectively.</span></span>  
  
 <span data-ttu-id="64428-132">El marco de trabajo de adaptadores proporciona extensiones de esquema y opciones avanzadas de configuración con el fin de admitir los requisitos de configuración comunes del adaptador.</span><span class="sxs-lookup"><span data-stu-id="64428-132">The Adapter Framework provides schema extensions and advanced configuration options to support common adapter configuration requirements.</span></span> <span data-ttu-id="64428-133">Para obtener más información acerca de las extensiones de esquema de marco de trabajo, consulte [extensiones de esquema de configuración de adaptador Framework](../core/adapter-framework-configuration-schema-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="64428-133">For more information about the Adapter Framework schema extensions, see [Adapter Framework Configuration Schema Extensions](../core/adapter-framework-configuration-schema-extensions.md).</span></span> <span data-ttu-id="64428-134">Para obtener más información acerca de las opciones de configuración avanzada, como los editores desplegables personalizados y convertidores de tipos personalizados, vea [componentes avanzados de configuración de adaptadores](../core/advanced-configuration-components-for-adapters.md).</span><span class="sxs-lookup"><span data-stu-id="64428-134">For more information about advanced configuration options such as custom drop-down editors and custom type converters, see [Advanced Configuration Components for Adapters](../core/advanced-configuration-components-for-adapters.md).</span></span>  
  
 <span data-ttu-id="64428-135">El código que se incluye a continuación proviene del archivo TransmitLocation.xsd y crea la siguiente página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="64428-135">The code that follows is from the TransmitLocation.xsd file, and produces the following property page.</span></span>  
  
 ![](../core/media/ebiz-prog-custad-sp.gif "ebiz_prog_custad_sp")  
<span data-ttu-id="64428-136">Ilustra la página de propiedades del puerto de envío para el adaptador de archivo de ejemplo</span><span class="sxs-lookup"><span data-stu-id="64428-136">Illustrates the send port property page for the sample file adapter</span></span>  
  
 <span data-ttu-id="64428-137">Tenga en cuenta en el archivo TransmitLocation.xsd siguiente que contiene la configuración del puerto de envío el \<Designer >, \<BAF: DisplayName >, y \<BAF: Description > etiquetas, al igual que el controlador de envío, además de usar el \<Category > etiqueta.</span><span class="sxs-lookup"><span data-stu-id="64428-137">Note in the TransmitLocation.xsd file below that the send port configuration contains the \<baf:designer>, \<baf:displayname>, and \<baf:description> tags, just like the send handler, and it also uses the \<baf:category> tag.</span></span> <span data-ttu-id="64428-138">La etiqueta de categoría permite agrupar propiedades.</span><span class="sxs-lookup"><span data-stu-id="64428-138">The category tag enables you to group properties together.</span></span> <span data-ttu-id="64428-139">Si tiene más de una categoría, la categoría se puede expandir y contraer y aparece en forma de encabezado de color gris encima de las propiedades de dicha categoría.</span><span class="sxs-lookup"><span data-stu-id="64428-139">If you have more than one category, the category is expandable and collapsible and appears in gray as a header above the properties in that category.</span></span> <span data-ttu-id="64428-140">Para obtener más información, consulte [extensiones de esquema de configuración de adaptador Framework](../core/adapter-framework-configuration-schema-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="64428-140">For more information, see [Adapter Framework Configuration Schema Extensions](../core/adapter-framework-configuration-schema-extensions.md).</span></span>  
  
 <span data-ttu-id="64428-141">Este esquema también contiene un campo de URI,</span><span class="sxs-lookup"><span data-stu-id="64428-141">This schema also contains a URI field.</span></span> <span data-ttu-id="64428-142">que se rellena en la página que aparece después de especificar toda la información del campo en la página de propiedades del puerto de envío durante el proceso de validación que realiza el adaptador.</span><span class="sxs-lookup"><span data-stu-id="64428-142">This is populated on the page that appears after you enter all of the field information on the send port property page during the validation processing by the adapter.</span></span>  
  
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