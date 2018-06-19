---
title: Propiedades de configuración para los adaptadores integrados de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, security
- adapters, passwords
- IReceiveLocation.CustomData property
- security, passwords
- ISendPort.CustomData property
- binding files, passwords
- adapters, properties
- binding files, security
ms.assetid: 4780a558-4322-428a-aa4a-0c32913faded
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 950f244c3a46af87164c4e276a50cd7a91fee14b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969962"
---
# <a name="configuration-properties-for-integrated-biztalk-adapters"></a><span data-ttu-id="c828c-102">Propiedades de configuración para adaptadores integrados de BizTalk</span><span class="sxs-lookup"><span data-stu-id="c828c-102">Configuration Properties for Integrated BizTalk Adapters</span></span>
<span data-ttu-id="c828c-103">El modelo de objetos del explorador de BizTalk expone la **IReceiveLocation.CustomData** y **ISendPort.CustomData** propiedades que contienen la bolsa de propiedades de configuración de adaptador en forma de un valor de nombre cadena XML de par.</span><span class="sxs-lookup"><span data-stu-id="c828c-103">The BizTalk Explorer object model exposes the **IReceiveLocation.CustomData** and **ISendPort.CustomData** properties that contain the adapter configuration property bag in the form of a name/value pair XML string.</span></span> <span data-ttu-id="c828c-104">Esta cadena XML de par nombre/valor se almacena en un \<CustomProps\> elemento dentro de un \<TransportTypeData\> elemento en un archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="c828c-104">This name/value pair XML string is stored in a \<CustomProps\> element within a \<TransportTypeData\> element in a binding file.</span></span> <span data-ttu-id="c828c-105">La mayoría de la información de la \<CustomProps\> elemento corresponde a la información que se pueden establecer para un adaptador en la interfaz de usuario de BizTalk Server (por ejemplo, la consola de administración de BizTalk o el Explorador de BizTalk).</span><span class="sxs-lookup"><span data-stu-id="c828c-105">Most of the information in the \<CustomProps\> element corresponds to information that can be set for an adapter in the BizTalk Server user interface (such as the BizTalk Administration Console or BizTalk Explorer).</span></span> <span data-ttu-id="c828c-106">Si estos valores se encuentran en un archivo de enlace, se aplicarán a la configuración del adaptador para las ubicaciones de recepción y los puertos de envío especificados cuando se importa el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="c828c-106">If these values are present in a binding file then they are applied to the adapter configuration for the specified receive locations and send ports when the binding file is imported.</span></span> <span data-ttu-id="c828c-107">La información de configuración de todos los adaptadores se almacena en la base de datos de Inicio de sesión único.</span><span class="sxs-lookup"><span data-stu-id="c828c-107">Configuration information for all adapters is stored in the Single Sign-On database.</span></span>  
  
 <span data-ttu-id="c828c-108">En esta sección se describen las propiedades de configuración que se pueden definir para cada adaptador integrado de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c828c-108">This section describes the configuration properties that can be set for each integrated BizTalk adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c828c-109">Información de contraseña que se almacena en la \<TransportTypeData\> elemento de un archivo de enlace está enmascarada de modo que los datos confidenciales no se guardan en texto no cifrado.</span><span class="sxs-lookup"><span data-stu-id="c828c-109">Password information that is stored in the \<TransportTypeData\> element of a binding file is masked so that sensitive data is not saved in clear text.</span></span> <span data-ttu-id="c828c-110">En función del transporte, la información de la contraseña se reemplaza con un valor nulo (NULL) o con asteriscos.</span><span class="sxs-lookup"><span data-stu-id="c828c-110">Depending on the transport, password information is either replaced with NULL or is replaced with asterisks.</span></span> <span data-ttu-id="c828c-111">Debe especificar manualmente esta información en el archivo de enlace para actualizar la configuración del adaptador antes de importar el archivo de enlace a la configuración del BizTalk Server de destino.</span><span class="sxs-lookup"><span data-stu-id="c828c-111">You must manually enter this information in the binding file to update the adapter configuration before importing the binding file into the target BizTalk Server configuration.</span></span>  
  
 <span data-ttu-id="c828c-112">Los datos de configuración para adaptadores generada mediante el marco de trabajo se almacenan en un \<AdapterConfig\> elemento.</span><span class="sxs-lookup"><span data-stu-id="c828c-112">The configuration data for adapters built using the Adapter Framework is stored in an \<AdapterConfig\> element.</span></span> <span data-ttu-id="c828c-113">Puesto que la \<AdapterConfig\> elemento especifica la VT_BSTR (vt = "8") tipo de datos, el  **\< \>**  caracteres contenidos en este elemento deben convertirse o se producirá un error cuando se intento de importar el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="c828c-113">Since the \<AdapterConfig\> element specifies the VT_BSTR (vt="8") data type, the **\< \>** characters contained in this element must be escaped or an error will occur when you attempt to import the binding file.</span></span> <span data-ttu-id="c828c-114">Esto causa que el texto de los datos de configuración sea menos legible para las personas que si estos caracteres no estuvieran acompañados de marcas de escape.</span><span class="sxs-lookup"><span data-stu-id="c828c-114">This causes the text for the configuration data to be less human readable than if these characters were not escaped.</span></span> <span data-ttu-id="c828c-115">En el ejemplo siguiente se muestra el efecto de las marcas de escape de estos caracteres desde los datos de configuración de ejemplo para un puerto de envío enlazado al adaptador de POP3.</span><span class="sxs-lookup"><span data-stu-id="c828c-115">The following example illustrates the effect of escaping these characters from sample configuration data for a send port bound to the POP3 adapter.</span></span>  
  
 <span data-ttu-id="c828c-116">**Los datos de configuración de TransportTypeData que no se convierte los caracteres de <> utilizados en el \<AdapterConfig\> elemento**</span><span class="sxs-lookup"><span data-stu-id="c828c-116">**TransportTypeData configuration data that does not escape the <> characters used in the \<AdapterConfig\> element**</span></span>  
  
 <span data-ttu-id="c828c-117">Estos datos de configuración no están válidos porque la \<AdapterConfig\> elemento especifica la VT_BSTR (vt = "8") tipo de datos y la \< \> caracteres contenidos en el \<AdapterConfig\> elemento sin escape:</span><span class="sxs-lookup"><span data-stu-id="c828c-117">This configuration data is invalid because the \<AdapterConfig\> element specifies the VT_BSTR (vt="8") data type and the \< \> characters contained in the \<AdapterConfig\> element are not escaped:</span></span>  
  
```  
<TransportTypeData>  
<CustomProps>  
<AdapterConfig vt="8">  
<Config xmlns:xsi=http://www.w3.org/2001/XMLSchema-instance xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
<mailServer>test.microsoft.com</mailServer>  
<serverPort>0</serverPort>  
<userName>testuser</userName>  
<password>******</password>  
<authenticationScheme>Basic</authenticationScheme>  
<sslRequired>false</sslRequired>  
<applyMIME>true</applyMIME>  
<bodyPartContentType>text/xml</bodyPartContentType>  
<bodyPartIndex>1</bodyPartIndex>  
<errorThreshold>10</errorThreshold>  
<pollingInterval>5</pollingInterval>  
<pollingUnitOfMeasure>Minutes</pollingUnitOfMeasure>   
<uri>POP3://test.microsoft.com#testuser</uri>  
</Config>  
</AdapterConfig>  
</CustomProps>  
</TransportTypeData>  
```  
  
 <span data-ttu-id="c828c-118">**Los datos de configuración de TransportTypeData que convierte los caracteres de <> utilizados en el \<AdapterConfig\> elemento**</span><span class="sxs-lookup"><span data-stu-id="c828c-118">**TransportTypeData configuration data that does escape the <> characters used in the \<AdapterConfig\> element**</span></span>  
  
 <span data-ttu-id="c828c-119">Puesto que la \<AdapterConfig\> elemento especifica la VT_BSTR (vt = "8") tipo de datos, el \< \> caracteres deben convertirse de la \<AdapterConfig\> elemento tal como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="c828c-119">Since the \<AdapterConfig\> element specifies the VT_BSTR (vt="8") data type, the \< \> characters must be escaped from the \<AdapterConfig\> element as seen below:</span></span>  
  
```  
<TransportTypeData>  
<CustomProps>  
<AdapterConfig vt="8">  
<Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
xmlns:xsd="http://www.w3.org/2001/XMLSchema"><mailServer>test  
microsoft.com</mailServer><serverPort>0</serverPort>&  
lt;userName>testuser</userName><password>******</pass  
word><authenticationScheme>Basic</authenticationScheme>&  
lt;sslRequired>false</sslRequired><applyMIME>true</ap  
plyMIME><bodyPartContentType>text/xml</bodyPartContentType&  
gt;<bodyPartIndex>1</bodyPartIndex><errorThreshold>10  
</errorThreshold><pollingInterval>5</pollingInterval>  
<pollingUnitOfMeasure>Minutes</pollingUnitOfMeasure><uri  
>POP3://test.microsoft.com#testuser</uri></Config>  
</AdapterConfig>  
</CustomProps>  
</TransportTypeData>  
```  
  
 <span data-ttu-id="c828c-120">Entre los adaptadores integrados que se han creado con el marco de trabajo de adaptadores se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="c828c-120">The integrated adapters that were created with the Adapter Framework include the following:</span></span>  
  
-   <span data-ttu-id="c828c-121">Adaptador de FTP</span><span class="sxs-lookup"><span data-stu-id="c828c-121">FTP Adapter</span></span>  
  
-   <span data-ttu-id="c828c-122">Adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="c828c-122">MQSeries Adapter</span></span>  
  
-   <span data-ttu-id="c828c-123">Adaptador de MSMQ</span><span class="sxs-lookup"><span data-stu-id="c828c-123">MSMQ Adapter</span></span>  
  
-   <span data-ttu-id="c828c-124">Adaptador de POP3</span><span class="sxs-lookup"><span data-stu-id="c828c-124">POP3 Adapter</span></span>  
  
-   <span data-ttu-id="c828c-125">Adaptador de Windows Sharepoint Services</span><span class="sxs-lookup"><span data-stu-id="c828c-125">Windows Sharepoint Services Adapter</span></span>  
  
 <span data-ttu-id="c828c-126">Para ver una cadena de ejemplo usada como los datos de configuración de TransportTypeData para cada adaptador integrado, consulte en esta sección el tema sobre propiedades de configuración asociado al adaptador que corresponda.</span><span class="sxs-lookup"><span data-stu-id="c828c-126">To view a sample string used as the TransportTypeData configuration data for each integrated adapter, please see the configuration properties topic that is associated with the adapter in this section.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c828c-127">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c828c-127">In This Section</span></span>  
 [<span data-ttu-id="c828c-128">Tipos de variables de las propiedades de configuración</span><span class="sxs-lookup"><span data-stu-id="c828c-128">Configuration Property Variable Types</span></span>](../core/configuration-property-variable-types.md)  
  
 [<span data-ttu-id="c828c-129">Propiedades de configuración del adaptador de archivo</span><span class="sxs-lookup"><span data-stu-id="c828c-129">File Adapter Configuration Properties</span></span>](../core/file-adapter-configuration-properties.md)  
  
 [<span data-ttu-id="c828c-130">Propiedades de configuración del adaptador de FTP</span><span class="sxs-lookup"><span data-stu-id="c828c-130">FTP Adapter Configuration Properties</span></span>](../core/ftp-adapter-configuration-properties.md)  
  
 [<span data-ttu-id="c828c-131">Propiedades de configuración del adaptador de HTTP</span><span class="sxs-lookup"><span data-stu-id="c828c-131">HTTP Adapter Configuration Properties</span></span>](../core/http-adapter-configuration-properties.md)  
  
 [<span data-ttu-id="c828c-132">Propiedades de configuración del adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="c828c-132">MQSeries Adapter Configuration Properties</span></span>](../core/mqseries-adapter-configuration-properties.md)  
  
 [<span data-ttu-id="c828c-133">Propiedades de configuración del adaptador de MSMQ</span><span class="sxs-lookup"><span data-stu-id="c828c-133">MSMQ Adapter Configuration Properties</span></span>](../core/msmq-adapter-configuration-properties.md)  
  
 [<span data-ttu-id="c828c-134">Propiedades de configuración del adaptador de POP3</span><span class="sxs-lookup"><span data-stu-id="c828c-134">POP3 Adapter Configuration Properties</span></span>](../core/pop3-adapter-configuration-properties.md)  
  
 [<span data-ttu-id="c828c-135">Propiedades de configuración del adaptador de SMTP</span><span class="sxs-lookup"><span data-stu-id="c828c-135">SMTP Adapter Configuration Properties</span></span>](../core/smtp-adapter-configuration-properties.md)  
  
 [<span data-ttu-id="c828c-136">Propiedades de configuración del adaptador de SOAP</span><span class="sxs-lookup"><span data-stu-id="c828c-136">SOAP Adapter Configuration Properties</span></span>](../core/soap-adapter-configuration-properties.md)  
  
 [<span data-ttu-id="c828c-137">Propiedades de configuración del adaptador de Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="c828c-137">Windows Sharepoint Services Adapter Configuration Properties</span></span>](../core/windows-sharepoint-services-adapter-configuration-properties.md)