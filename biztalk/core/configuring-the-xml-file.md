---
title: Configurar el archivo XML. | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52851901-8374-412f-9c29-83845d8d4861
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d791de9b6fe90ebb850874026e8d52e49732f32
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-the-xml-file"></a><span data-ttu-id="62be9-102">Configurar el archivo XML</span><span class="sxs-lookup"><span data-stu-id="62be9-102">Configuring the XML File</span></span>
<span data-ttu-id="62be9-103">Si se instala Inicio de sesión único empresarial (SSO), un archivo XML denominado ENTSSO.xml se instalará en el directorio de extensiones.</span><span class="sxs-lookup"><span data-stu-id="62be9-103">When you install Enterprise Single Sign-On (SSO), an XML file named ENTSSO.xml is installed in your Extensions directory.</span></span> <span data-ttu-id="62be9-104">Al editar el archivo, se define la configuración para todas las instancias del agente de administración de ENTSSO (MA).</span><span class="sxs-lookup"><span data-stu-id="62be9-104">By editing the file, you define the configuration for all instances of the ENTSSO Management Agent (MA).</span></span>  
  
 <span data-ttu-id="62be9-105">El archivo es similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="62be9-105">The file is similar to the following:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<sso>  
  
  <SourceMA name="RACFMA1" objectType="person" attribute="uid"/>  
  <SourceMA name="ACF2" objectType="person" attribute="uid"/>  
  
  <ENTSSOMA name ="ENTSSOMA1" adma="ADMA1" deleteAll="true">  
    <Application name="AppForRACF1A" sourceMA="RACFMA1" create="true" delete="true"/>  
    <Application name="AppForRACF1B" sourceMA="RACFMA1" create="true" delete="false"/>  
  </ENTSSOMA>  
  
  <ENTSSOMA name ="ENTSSOMA2" adma="ADMA1" deleteAll="true">  
    <Application name="AppForACF2" sourceMA="ACF2"/>  
  </ENTSSOMA>  
  
</sso>  
```  
  
## <a name="xml-elements-and-attributes"></a><span data-ttu-id="62be9-106">Elementos y atributos XML</span><span class="sxs-lookup"><span data-stu-id="62be9-106">XML Elements and Attributes</span></span>  
 <span data-ttu-id="62be9-107">La siguiente lista describe los elementos y atributos que se definen en el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="62be9-107">The following list describes the elements and attributes that you define in the XML file.</span></span> <span data-ttu-id="62be9-108">Tenga en cuenta que todos los nombres de elementos y atributos de ese archivo distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="62be9-108">Note that all element and attribute names in this file are case sensitive.</span></span>  
  
 <span data-ttu-id="62be9-109">**Elemento: ENTSSO** -define la configuración de una única instancia MA de ENTSSO.</span><span class="sxs-lookup"><span data-stu-id="62be9-109">**Element: ENTSSO** - Defines the configuration of a single ENTSSO MA instance.</span></span> <span data-ttu-id="62be9-110">Se permiten varios elementos ENTSSO.</span><span class="sxs-lookup"><span data-stu-id="62be9-110">Multiple ENTSSO elements are allowed.</span></span>  
  
 <span data-ttu-id="62be9-111">**Atributo: nombre** : define el nombre de instancia del agente de administración de ENTSSO y debe coincidir con el nombre de la instancia de agente de administración de ENTSSO en Microsoft Identity Integration Server (MIIS).</span><span class="sxs-lookup"><span data-stu-id="62be9-111">**Attribute: name** - Defines the instance name of the ENTSSO Management Agent, and must match the name of the ENTSSO Management Agent instance in Microsoft Identity Integration Server (MIIS).</span></span>  
  
 <span data-ttu-id="62be9-112">**Atributo: adma** -define el nombre de instancia del agente de administración de Active Directory que se usará en esta instancia de agente de administración de ENTSSO.</span><span class="sxs-lookup"><span data-stu-id="62be9-112">**Attribute: adma** - Defines the instance name of the Active Directory Management Agent that will be used by this ENTSSO Management Agent instance.</span></span> <span data-ttu-id="62be9-113">El agente de administración de Active Directory proporciona el nombre de dominio de Windows y el nombre de usuario de Windows para la asignación.</span><span class="sxs-lookup"><span data-stu-id="62be9-113">The Active Directory Management Agent provides the Windows domain name and Windows user name for the mapping.</span></span> <span data-ttu-id="62be9-114">Este nombre de instancia del agente de administración de Active Directory debe coincidir con el nombre de una instancia del agente de administración de Active Directory en MIIS.</span><span class="sxs-lookup"><span data-stu-id="62be9-114">This Active Directory Management Agent instance name must match the name of an Active Directory Management Agent instance in MIIS.</span></span>  
  
 <span data-ttu-id="62be9-115">**Atributo: deleteAll** - opcional; valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="62be9-115">**Attribute: deleteAll** - Optional; default is `true`.</span></span> <span data-ttu-id="62be9-116">Si se establece como `true` y se elimina una identidad de Windows, se eliminarán todas las asignaciones con dicha identidad de Windows de todas las aplicaciones ENTSSO.</span><span class="sxs-lookup"><span data-stu-id="62be9-116">If this is set to `true`, and a Windows identity is deleted, all mappings with that Windows identity are deleted from all ENTSSO applications.</span></span>  
  
 <span data-ttu-id="62be9-117">**Elemento: Aplicación** -define la relación entre una aplicación afiliada SSO y un agente de administración externo.</span><span class="sxs-lookup"><span data-stu-id="62be9-117">**Element: Application** - Defines the relationship between an SSO affiliate application and an external Management Agent.</span></span> <span data-ttu-id="62be9-118">Se permiten varios elementos `Application`.</span><span class="sxs-lookup"><span data-stu-id="62be9-118">Multiple `Application` elements are allowed.</span></span>  
  
 <span data-ttu-id="62be9-119">**Atributo: nombre** -define el nombre de la aplicación afiliada SSO.</span><span class="sxs-lookup"><span data-stu-id="62be9-119">**Attribute: name** - Defines the name of the SSO affiliate application.</span></span> <span data-ttu-id="62be9-120">Esta aplicación ya debe existir en el sistema ENTSSO.</span><span class="sxs-lookup"><span data-stu-id="62be9-120">This application must already exist within the ENTSSO system.</span></span>  
  
 <span data-ttu-id="62be9-121">**Atributo: sourceMA** -define el nombre de instancia para el origen (externo) agente de administración que se usará para proporcionar el UserId externo en la asignación para esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="62be9-121">**Attribute: sourceMA** - Defines the instance name for the source (external) Management Agent that will be used to provide the external UserId in the mapping for this application.</span></span> <span data-ttu-id="62be9-122">Este nombre de instancia del agente de administración externo debe coincidir con el nombre de una instancia de MA externa en MIIS.</span><span class="sxs-lookup"><span data-stu-id="62be9-122">This external Management Agent instance name must match the name of an external MA instance in MIIS.</span></span>  
  
 <span data-ttu-id="62be9-123">**Atributo: crear** - opcional; valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="62be9-123">**Attribute: create** - Optional; default is `true`.</span></span> <span data-ttu-id="62be9-124">Define si se deben crear asignaciones para esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="62be9-124">Defines whether mappings should be created for this application.</span></span>  
  
 <span data-ttu-id="62be9-125">**Atributo: eliminar** - opcional; valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="62be9-125">**Attribute: delete** - Optional; default is `true`.</span></span> <span data-ttu-id="62be9-126">Define si se deben eliminar asignaciones para esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="62be9-126">Defines whether mappings should be deleted for this application.</span></span>  
  
 <span data-ttu-id="62be9-127">**Elemento: SourceMA** : opcional.</span><span class="sxs-lookup"><span data-stu-id="62be9-127">**Element: SourceMA** - Optional.</span></span> <span data-ttu-id="62be9-128">Identifica el tipo de objeto y los nombres de atributo para una instancia del agente de administración de origen específico (externo).</span><span class="sxs-lookup"><span data-stu-id="62be9-128">Identifies the object type and attribute names for a specific source (external) Management Agent instance.</span></span> <span data-ttu-id="62be9-129">Si este elemento no está presente para un agente de administración específico, se consideran el tipo de objeto predeterminado (“person”) y los nombres de atributos (“uid”).</span><span class="sxs-lookup"><span data-stu-id="62be9-129">If this element is not present for a specific Management Agent, then the default object type (“person”) and attribute names (“uid”) are assumed.</span></span> <span data-ttu-id="62be9-130">Se permiten varios elementos `SourceMA`.</span><span class="sxs-lookup"><span data-stu-id="62be9-130">Multiple `SourceMA` elements are allowed.</span></span>  
  
 <span data-ttu-id="62be9-131">**Atributo: nombre** -el nombre del origen (externo) de agente de administración.</span><span class="sxs-lookup"><span data-stu-id="62be9-131">**Attribute: name** - The name of the source (external) Management Agent.</span></span> <span data-ttu-id="62be9-132">Este nombre debe coincidir como mínimo con uno de los `sourceMA` nombres de atributos de los elementos `Application`.</span><span class="sxs-lookup"><span data-stu-id="62be9-132">This name must match at least one of the `sourceMA` attribute names from the `Application` elements.</span></span>  
  
 <span data-ttu-id="62be9-133">**Atributo: objectType** - opcional; valor predeterminado es `person`.</span><span class="sxs-lookup"><span data-stu-id="62be9-133">**Attribute: objectType** - Optional; default is `person`.</span></span> <span data-ttu-id="62be9-134">Si el nombre del tipo de objeto que proporciona el UserId externo no es `person`, debe especificarse aquí.</span><span class="sxs-lookup"><span data-stu-id="62be9-134">If the object type name that provides the external UserId is not `person`, it should be specified here.</span></span>  
  
 <span data-ttu-id="62be9-135">**Atributo: atributo** - opcional; valor predeterminado es `uid`.</span><span class="sxs-lookup"><span data-stu-id="62be9-135">**Attribute: attribute** - Optional; default is `uid`.</span></span> <span data-ttu-id="62be9-136">Si el nombre del atributo que proporciona el UserId externo no es `uid`, puede especificarlo aquí.</span><span class="sxs-lookup"><span data-stu-id="62be9-136">If the attribute name that provides the external UserId is not `uid`, you can specify it here.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62be9-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="62be9-137">See Also</span></span>  
 [<span data-ttu-id="62be9-138">Cómo usar al agente de administración de ENTSSO</span><span class="sxs-lookup"><span data-stu-id="62be9-138">How to Use the ENTSSO Management Agent</span></span>](../core/how-to-use-the-entsso-management-agent.md)