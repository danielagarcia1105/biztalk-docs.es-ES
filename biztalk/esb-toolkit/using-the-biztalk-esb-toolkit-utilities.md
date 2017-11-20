---
title: Con las utilidades del Kit de herramientas de ESB de BizTalk | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2dc05ac-831a-44e1-bd44-e41398552ab1
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36902e2c5e90ce1b02f40f6994f150fa4c421c7f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-biztalk-esb-toolkit-utilities"></a><span data-ttu-id="a27f9-102">Con las utilidades del Kit de herramientas de ESB de BizTalk</span><span class="sxs-lookup"><span data-stu-id="a27f9-102">Using the BizTalk ESB Toolkit Utilities</span></span>
<span data-ttu-id="a27f9-103">Esta sección describen diversas utilidades incluidas como parte de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a27f9-103">This section describes various utilities included as part of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
 <span data-ttu-id="a27f9-104">**Utilidad de importación itinerarios de ESB**</span><span class="sxs-lookup"><span data-stu-id="a27f9-104">**ESB Itinerary Import Utility**</span></span>  
  
 <span data-ttu-id="a27f9-105">Esta utilidad se encuentra en el directorio \bin de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] y se denomina EsbImportUtil.exe.</span><span class="sxs-lookup"><span data-stu-id="a27f9-105">This utility is located under the \bin directory of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] and is named EsbImportUtil.exe.</span></span> <span data-ttu-id="a27f9-106">Esta utilidad se puede usar para publicar o implementar el itinerario XML en la base de datos de ESBItineraryDB.</span><span class="sxs-lookup"><span data-stu-id="a27f9-106">This utility can be used to publish or deploy the itinerary XML into the ESBItineraryDB database.</span></span>  
  
 <span data-ttu-id="a27f9-107">La sintaxis de la utilidad es como sigue:</span><span class="sxs-lookup"><span data-stu-id="a27f9-107">The syntax for the utility is as follows:</span></span>  
  
```  
>EsbImportUtil <Parameter1> <Value> <parameter2> <Value>...  
```  
  
 <span data-ttu-id="a27f9-108">Los distintos parámetros que pueda aceptar son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a27f9-108">The various parameters it can accept are the following:</span></span>  
  
 <span data-ttu-id="a27f9-109">/?: \<Mostrar los parámetros Ayuda ></span><span class="sxs-lookup"><span data-stu-id="a27f9-109">/?: \<Show the parameters help></span></span>  
  
 <span data-ttu-id="a27f9-110">/ f: \<ruta de acceso del archivo de xml de itinerario ></span><span class="sxs-lookup"><span data-stu-id="a27f9-110">/f: \<Itinerary xml file path></span></span>  
  
 <span data-ttu-id="a27f9-111">/ c: \<publicado &#124; implementado ></span><span class="sxs-lookup"><span data-stu-id="a27f9-111">/c: \<published &#124; deployed></span></span>  
  
 <span data-ttu-id="a27f9-112">/ n: \<nombre predeterminado itinerario ></span><span class="sxs-lookup"><span data-stu-id="a27f9-112">/n: \<Default Itinerary name></span></span>  
  
 <span data-ttu-id="a27f9-113">/ v: \<versión itinerario predeterminado (formato 'principal.secundaria') ></span><span class="sxs-lookup"><span data-stu-id="a27f9-113">/v: \<Default Itinerary version (format 'major.minor')></span></span>  
  
 <span data-ttu-id="a27f9-114">/ o: \<sobrescribir silenciosa ></span><span class="sxs-lookup"><span data-stu-id="a27f9-114">/o: \<Silent overwrite></span></span>  
  
 <span data-ttu-id="a27f9-115">Los siguientes son ejemplos de cómo usar esta utilidad.</span><span class="sxs-lookup"><span data-stu-id="a27f9-115">The following are examples of how to use this utility.</span></span>  
  
 <span data-ttu-id="a27f9-116">Para publicar en la base de datos de itinerario:</span><span class="sxs-lookup"><span data-stu-id="a27f9-116">To publish to the Itinerary database:</span></span>  
  
```  
>EsbImportUtil /f:myitinerary.xml /c:published  
```  
  
 <span data-ttu-id="a27f9-117">Para implementar en la base de datos de itinerario:</span><span class="sxs-lookup"><span data-stu-id="a27f9-117">To deploy to the Itinerary database:</span></span>  
  
```  
>EsbImportUtil  /f:myitinerary.xml /c:deployed  
```  
  
 <span data-ttu-id="a27f9-118">**Configuración de SSO conservar utilidad**</span><span class="sxs-lookup"><span data-stu-id="a27f9-118">**SSO Configuration Persist Utility**</span></span>  
  
 <span data-ttu-id="a27f9-119">Esta utilidad se encuentra en el directorio \bin de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] y se denomina Microsoft.Practices.ESB.PersistConfigurationTool.exe.</span><span class="sxs-lookup"><span data-stu-id="a27f9-119">This utility is located under the \bin directory of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] and is named Microsoft.Practices.ESB.PersistConfigurationTool.exe.</span></span> <span data-ttu-id="a27f9-120">Esta utilidad puede usarse para conservar la información de configuración de ESB en la base de datos de SSO de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a27f9-120">This utility can be used to persist the ESB configuration information into the BizTalk SSO database.</span></span> <span data-ttu-id="a27f9-121">También puede usarse para ver información de configuración y quitar la información de configuración de la base de datos SSO.</span><span class="sxs-lookup"><span data-stu-id="a27f9-121">This can also be used to view configuration information and remove the configuration information from the SSO database.</span></span>  
  
 <span data-ttu-id="a27f9-122">La sintaxis de la utilidad es como sigue:</span><span class="sxs-lookup"><span data-stu-id="a27f9-122">The syntax for the utility is as follows:</span></span>  
  
 <span data-ttu-id="a27f9-123">**Para agregar una sección de configuración:**</span><span class="sxs-lookup"><span data-stu-id="a27f9-123">**To add a configuration section:**</span></span>  
  
```  
>Microsoft.Practices.ESB.PersistConfigurationTool  /P /F:app.config /S:SectionName /A:ApplicationName  
```  
  
> [!NOTE]
>  <span data-ttu-id="a27f9-124">Si no se proporciona/s, se agregarán las siguientes secciones: connectionStrings, esb, esb.resolver y cachingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="a27f9-124">If /S is not provided, the following sections will be added: connectionStrings, esb, esb.resolver and cachingConfiguration.</span></span>  
  
 <span data-ttu-id="a27f9-125">**Para quitar una sección:**</span><span class="sxs-lookup"><span data-stu-id="a27f9-125">**To remove a section:**</span></span>  
  
```  
>Microsoft.Practices.ESB.PersistConfigurationTool  /R /S:SectionName  
```  
  
 <span data-ttu-id="a27f9-126">Para ver una sección existente, utilice los modificadores de la aplicación y la sección con el modificador/v.</span><span class="sxs-lookup"><span data-stu-id="a27f9-126">To view an existing section, use the application and section switches with the /V switch.</span></span>  
  
 <span data-ttu-id="a27f9-127">Para establecer al administrador de nombre de grupo, utilice el modificador AG:AdminGroupName.</span><span class="sxs-lookup"><span data-stu-id="a27f9-127">To set the administrator group name, use the AG:AdminGroupName switch.</span></span>  
  
 <span data-ttu-id="a27f9-128">Para establecer el nombre del grupo de usuario, use el modificador UG:UserGroupName.</span><span class="sxs-lookup"><span data-stu-id="a27f9-128">To set the user group name, use the UG:UserGroupName switch.</span></span>