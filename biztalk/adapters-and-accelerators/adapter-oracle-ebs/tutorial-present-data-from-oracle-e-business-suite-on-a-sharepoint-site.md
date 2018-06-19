---
title: 'Tutorial: Presentar los datos de Oracle E-Business Suite en un sitio de SharePoint | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1272b76c-29a1-4912-9c2d-8a4cf43df59d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6aa1b709c317438c9614e412496eedb318dea3a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215636"
---
# <a name="tutorial-present-data-from-oracle-e-business-suite-on-a-sharepoint-site"></a><span data-ttu-id="a8561-102">Tutorial: Presentar los datos de Oracle E-Business Suite en un sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="a8561-102">Tutorial: Present data from Oracle E-Business Suite on a SharePoint Site</span></span>
<span data-ttu-id="a8561-103">Este tutorial proporciona instrucciones detalladas sobre cómo utilizar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] con Microsoft Office SharePoint Server para presentar datos de Oracle E-Business Suite en un portal de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a8561-103">This tutorial provides detailed instructions on using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] with Microsoft Office SharePoint Server to present data from Oracle E-Business Suite on a SharePoint portal.</span></span> <span data-ttu-id="a8561-104">También muestra cómo configurar una aplicación de búsqueda en Microsoft Office SharePoint Server que permite realizar una búsqueda de texto completo de un portal de SharePoint en el artefacto de Oracle E-Business Suite configurado.</span><span class="sxs-lookup"><span data-stu-id="a8561-104">It also demonstrates how to configure a search application in the Microsoft Office SharePoint Server that allows you to do a full-text search from a SharePoint portal on the configured Oracle E-Business Suite artifact.</span></span>  
  
 <span data-ttu-id="a8561-105">Para demostrar cómo hacer esto, considere la posibilidad de una tabla de ejemplo de interfaz en Oracle E-Business Suite que almacena información acerca de los empleados.</span><span class="sxs-lookup"><span data-stu-id="a8561-105">To demonstrate how to do so, consider a sample interface table in Oracle E-Business Suite that stores information about employees.</span></span> <span data-ttu-id="a8561-106">En este tutorial, se crea una aplicación de Microsoft Office SharePoint Server que recuperar una lista de clientes de Oracle E-Business Suite en función de una cadena de búsqueda con:</span><span class="sxs-lookup"><span data-stu-id="a8561-106">In this tutorial, an application is created in Microsoft Office SharePoint Server that retrieve a list of customers from Oracle E-Business Suite based on a search string using:</span></span>  
  
-   <span data-ttu-id="a8561-107">Un elemento Web de lista de datos económicos de Microsoft Office SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="a8561-107">A Business Data List Web Part in Microsoft Office SharePoint Server</span></span>  
  
-   <span data-ttu-id="a8561-108">La característica de búsqueda en Microsoft Office SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="a8561-108">The search feature in Microsoft Office SharePoint Server</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8561-109">Antes de continuar con el tutorial, asegúrese de que ha instalado todos los requisitos previos para usar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] con Microsoft Office SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="a8561-109">Before proceeding with the tutorial, make sure you have installed all the prerequisites for using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] with Microsoft Office SharePoint Server.</span></span> <span data-ttu-id="a8561-110">Para obtener información sobre los requisitos previos, consulte la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] Guía de instalación, por lo general se instala en C:\Program Files\Microsoft BizTalk adaptador Pack\Documents.</span><span class="sxs-lookup"><span data-stu-id="a8561-110">For information about the prerequisites, see the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation guide, typically installed at C:\Program Files\Microsoft BizTalk Adapter Pack\Documents.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a8561-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a8561-111">In This Section</span></span>  
  
-   [<span data-ttu-id="a8561-112">Paso 1: Usar el adaptador de Oracle E-Business para crear y publicar un servicio WCF</span><span class="sxs-lookup"><span data-stu-id="a8561-112">Step 1: Use the Oracle E-Business Adapter to Create and Publish a WCF Service</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md)  
  
-   [<span data-ttu-id="a8561-113">Paso 2: Crear un archivo de definición de aplicación para los artefactos de Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="a8561-113">Step 2: Create an Application Definition File for the Oracle E-Business Suite Artifacts</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md)  
  
-   [<span data-ttu-id="a8561-114">Paso 3: Crear una aplicación de SharePoint para recuperar datos de Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="a8561-114">Step 3: Create a SharePoint Application to Retrieve Data from Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md)  
  
-   [<span data-ttu-id="a8561-115">Paso 4: Probar la aplicación de SharePoint</span><span class="sxs-lookup"><span data-stu-id="a8561-115">Step 4: Test Your SharePoint Application</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/step-4-test-your-sharepoint-application.md)