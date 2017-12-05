---
title: Importar una PIP basado en XSD | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- PIPs, importing
- XSD-based PIPs
- PIPs, XSD-based PIPs
ms.assetid: d12441d4-79bf-4c24-9360-4b78c1da0d34
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d8865d7a75bdb06895b963b8269ed457cd5804f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="importing-an-xsd-based-pip"></a><span data-ttu-id="91c13-102">Importar un PIP basado en XSD</span><span class="sxs-lookup"><span data-stu-id="91c13-102">Importing an XSD-based PIP</span></span>
<span data-ttu-id="91c13-103">Aunque la mayoría de los PIP proporcionados por RosettaNet.org se basan en el DTD, algunos PIP más recientes están basados en XSD.</span><span class="sxs-lookup"><span data-stu-id="91c13-103">While the majority of PIPS provided by RosettaNet.org are DTD-based, newer PIPS are XSD-based.</span></span> <span data-ttu-id="91c13-104">En el siguiente procedimiento se describe cómo importar los PIP basados en XSD.</span><span class="sxs-lookup"><span data-stu-id="91c13-104">The following procedure describes how to import XSD-based PIPS.</span></span>  
  
### <a name="to-import-an-xsd-based-pip"></a><span data-ttu-id="91c13-105">Para importar un PIP basado en XSD</span><span class="sxs-lookup"><span data-stu-id="91c13-105">To import an XSD-based PIP</span></span>  
  
1.  <span data-ttu-id="91c13-106">Descargue el archivo .zip del PIP basado en XSD de RosettaNet.org en [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=33859) o de CIDX.org en [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=62361).</span><span class="sxs-lookup"><span data-stu-id="91c13-106">Download the XSD-based PIP .zip file from RosettaNet.org at [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=33859) or from CIDX.org at [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=62361).</span></span> <span data-ttu-id="91c13-107">Extraiga los archivos del archivo .zip.</span><span class="sxs-lookup"><span data-stu-id="91c13-107">Extract the files from the .zip file.</span></span> <span data-ttu-id="91c13-108">Los archivos que necesita estarán en las subcarpetas de la carpeta XML.</span><span class="sxs-lookup"><span data-stu-id="91c13-108">The files that you need will be in the subfolders of the XML folder.</span></span>  
  
2.  <span data-ttu-id="91c13-109">Abra Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="91c13-109">Open Visual Studio.</span></span> <span data-ttu-id="91c13-110">Cree un proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="91c13-110">Create a new BizTalk project.</span></span>  
  
3.  <span data-ttu-id="91c13-111">Abra el Explorador de Windows y desplácese a la carpeta XML extraída en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="91c13-111">Open Windows Explorer, and move to the XML folder extracted in step 1.</span></span> <span data-ttu-id="91c13-112">Seleccione la primera carpeta dentro de la carpeta XML, arrástrela al explorador de soluciones en Visual Studio y colóquela en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="91c13-112">Select the first folder under the XML folder, drag it to Solutions Explorer in Visual Studio, and drop it into your project.</span></span> <span data-ttu-id="91c13-113">Repita este paso con cada una de las subcarpetas incluidas en la carpeta XML, creando la misma estructura de carpetas en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="91c13-113">Repeat for each of the subfolders in the XML folder, creating the same folder structure in your project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="91c13-114">En el caso de un PIP PIP7c7, entre estas carpetas se incluyen las carpetas Domain, Interchange, System y Universal.</span><span class="sxs-lookup"><span data-stu-id="91c13-114">For a PIP7c7 PIP these folders would include the Domain, Interchange, System, and Universal folders.</span></span> <span data-ttu-id="91c13-115">En este PIP, el proyecto debería contener las carpetas Domain, Interchange, System y Universal y su contenido.</span><span class="sxs-lookup"><span data-stu-id="91c13-115">For this PIP, your project should contain Domain, Interchange, System, and Universal folders and their contents.</span></span>  
  
4.  <span data-ttu-id="91c13-116">Si hay un archivo .xsd en la carpeta System, selecciónelo en el Explorador de soluciones y cambie el espacio de nombres en la página de propiedades para que no contenga la cadena ".System".</span><span class="sxs-lookup"><span data-stu-id="91c13-116">If there is an .xsd file in the System folder, select it in Solution Explorer and change the namespace listed in the property page so that it does not contain the string ".System".</span></span> <span data-ttu-id="91c13-117">Por ejemplo, para el PIP PIP7c7, puede cambiar el espacio de nombres a "PIP7c7._System".</span><span class="sxs-lookup"><span data-stu-id="91c13-117">For example, for PIP7c7 PIP, you could change the namespace to be "PIP7c7._System".</span></span> <span data-ttu-id="91c13-118">Repita este paso con cada archivo .xsd de la carpeta System.</span><span class="sxs-lookup"><span data-stu-id="91c13-118">Repeat for each .xsd file in the System folder.</span></span> <span data-ttu-id="91c13-119">Si no se cambia el espacio de nombres, aparecerá el siguiente error o uno similar:</span><span class="sxs-lookup"><span data-stu-id="91c13-119">If you do not change the namespace, you will receive the following or a similar error:</span></span>  
  
    ```  
    The type or namespace name 'SerializableAttribute' does not exist in the class or namespace 'PIP7C7.System'.  
    ```  
  
5.  <span data-ttu-id="91c13-120">Revise todos los archivos .xsd para asegurarse de que el \<esquema\> TypeName y el nodo raíz TypeName no son idénticos.</span><span class="sxs-lookup"><span data-stu-id="91c13-120">Review all .xsd files to ensure that the \<schema\> TypeName and root node TypeName are not identical.</span></span> <span data-ttu-id="91c13-121">Por ejemplo, para un PIP PIP7C7 el archivo PartnerIdentification.xsd de la carpeta Universal tiene el TypeName 'Partneridentification' tanto para el \<esquema\> (cuando PartnerIdentification.xsd se selecciona en el Explorador de soluciones) y también el Nodo raíz PartnerIdentification.</span><span class="sxs-lookup"><span data-stu-id="91c13-121">For example, for a PIP7C7 PIP the PartnerIdentification.xsd in the Universal folder has the TypeName of 'PartnerIdentification' for both the \<schema\> (when PartnerIdentification.xsd is selected in Solution Explorer) and also the PartnerIdentification root node.</span></span> <span data-ttu-id="91c13-122">Para corregir este problema, seleccione PartnerIdentification.xsd en el Explorador de soluciones y, después, en la página de propiedades cambie la propiedad TypeName para que no contenga el mismo TypeName que el nodo raíz PartnerIdentification.</span><span class="sxs-lookup"><span data-stu-id="91c13-122">To correct this, select PartnerIdentification.xsd in Solution Explorer, and then in the property page change the TypeName property so that it does not contain the same TypeName as the PartnerIdentification root node.</span></span> <span data-ttu-id="91c13-123">Por ejemplo, cambie el TypeName por "_PartnerIdentification".</span><span class="sxs-lookup"><span data-stu-id="91c13-123">For example, change the TypeName to be "_PartnerIdentification".</span></span> <span data-ttu-id="91c13-124">Si no realiza este paso, aparecerá el siguiente error al intentar generar el proyecto:</span><span class="sxs-lookup"><span data-stu-id="91c13-124">If you do not take this step, you will receive the following error when you try to build the project:</span></span>  
  
    ```  
    Node "<Schema>" - This schema file has a TypeName that collides with the RootNode TypeName of one of its root Nodes. Make sure that they are different.  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="91c13-125">La columna Archivo en la lista de errores indicará qué archivos tienen este problema.</span><span class="sxs-lookup"><span data-stu-id="91c13-125">The File column in the error list will indicate which files have this problem.</span></span>  
  
6.  <span data-ttu-id="91c13-126">Genere e implemente el proyecto.</span><span class="sxs-lookup"><span data-stu-id="91c13-126">Build and then deploy the project.</span></span>