---
title: 'Tutorial 1: Presentar datos desde un sistema SAP en un sitio de SharePoint | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MOSS, creating an application in
- Microsoft Office SharePoint Server
- MOSS
- Microsoft Office SharePoint Server, creating an application in
ms.assetid: 6e31c365-446c-4fe1-8538-fa6c869eed63
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cdc3ea5e41600aebcef1fda933735c418dec78c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217428"
---
# <a name="tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site"></a><span data-ttu-id="43287-102">Tutorial 1: Presentar datos desde un sistema SAP en un sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="43287-102">Tutorial 1: Presenting Data from an SAP System on a SharePoint Site</span></span>
<span data-ttu-id="43287-103">Este tutorial proporciona instrucciones detalladas sobre cómo utilizar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] con Microsoft Office SharePoint Server para presentar datos de negocio de un sistema SAP en un portal de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="43287-103">This tutorial provides detailed instructions on using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with Microsoft Office SharePoint Server to present business data from an SAP system on a SharePoint portal.</span></span> <span data-ttu-id="43287-104">Para demostrar cómo usar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] con Office SharePoint Server, tenga en cuenta las dos entidades más comunes en las empresas: clientes y pedidos de venta.</span><span class="sxs-lookup"><span data-stu-id="43287-104">To demonstrate how to use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with Office SharePoint Server, consider the two most common entities in any business: customers and sales orders.</span></span> <span data-ttu-id="43287-105">En este ejemplo, se crea una aplicación de Office SharePoint Server, que utiliza el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="43287-105">In this example, an application is created in Office SharePoint Server, which uses the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to do the following:</span></span>  
  
-   <span data-ttu-id="43287-106">Recuperar una lista de clientes desde el sistema SAP basándose en una cadena de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="43287-106">Retrieve a list of customers from the SAP system based on a search string.</span></span>  
  
-   <span data-ttu-id="43287-107">Seleccione a un cliente en la lista y detalles presentes para el cliente.</span><span class="sxs-lookup"><span data-stu-id="43287-107">Select a customer from the list and present details for the customer.</span></span>  
  
-   <span data-ttu-id="43287-108">Recuperar los pedidos de venta para el cliente seleccionado.</span><span class="sxs-lookup"><span data-stu-id="43287-108">Retrieve the sales orders for the selected customer.</span></span>  
  
 <span data-ttu-id="43287-109">Para extraer datos de los clientes de un sistema SAP, el ejemplo utiliza la RFC SD_RFC_CUSTOMER_GET.</span><span class="sxs-lookup"><span data-stu-id="43287-109">To extract customer data from an SAP system, the example uses the SD_RFC_CUSTOMER_GET RFC.</span></span> <span data-ttu-id="43287-110">Para extraer información sobre los pedidos de ventas para un cliente específico, usa la RFC BAPI_SALESORDER_GETLIST.</span><span class="sxs-lookup"><span data-stu-id="43287-110">To extract information about sales orders for a specific customer, it uses the BAPI_SALESORDER_GETLIST RFC.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43287-111">Algunas versiones del sistema SAP exponen una solicitud de cambio de RFC_CUSTOMER_GET en lugar de SD_RFC_CUSTOMER_GET.</span><span class="sxs-lookup"><span data-stu-id="43287-111">Some versions of the SAP system expose an RFC_CUSTOMER_GET RFC instead of SD_RFC_CUSTOMER_GET.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43287-112">Antes de continuar con el tutorial, asegúrese de que ha instalado todos los requisitos previos para usar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] con Office SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="43287-112">Before proceeding with the tutorial, make sure you have installed all the prerequisites for using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with Office SharePoint Server.</span></span> <span data-ttu-id="43287-113">Para obtener más información sobre los requisitos previos, consulte la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] Guía de instalación, por lo general se instala en C:/programa archivos/Microsoft  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] /documentos.</span><span class="sxs-lookup"><span data-stu-id="43287-113">For more information about the prerequisites, see the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation guide, typically installed at C:/Program Files/Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]/Documents.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="43287-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="43287-114">In This Section</span></span>  
  
-   [<span data-ttu-id="43287-115">Paso 1: Publicar los artefactos SAP como un servicio WCF</span><span class="sxs-lookup"><span data-stu-id="43287-115">Step 1: Publish the SAP Artifacts as a WCF Service</span></span>](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)  
  
-   [<span data-ttu-id="43287-116">Paso 2: Crear un archivo de definición de aplicación para los artefactos SAP</span><span class="sxs-lookup"><span data-stu-id="43287-116">Step 2: Create an Application Definition File for the SAP Artifacts</span></span>](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)  
  
-   [<span data-ttu-id="43287-117">Paso 3: Crear una aplicación de SharePoint para recuperar datos de SAP</span><span class="sxs-lookup"><span data-stu-id="43287-117">Step 3: Create a SharePoint Application to Retrieve Data from SAP</span></span>](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md)  
  
-   [<span data-ttu-id="43287-118">Paso 4: Probar la aplicación de SharePoint</span><span class="sxs-lookup"><span data-stu-id="43287-118">Step 4: Test Your SharePoint Application</span></span>](../../adapters-and-accelerators/adapter-sap/step-4-test-your-sharepoint-application1.md)  
  
## <a name="see-also"></a><span data-ttu-id="43287-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="43287-119">See Also</span></span>  
 [<span data-ttu-id="43287-120">Tutoriales del adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="43287-120">SAP Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)