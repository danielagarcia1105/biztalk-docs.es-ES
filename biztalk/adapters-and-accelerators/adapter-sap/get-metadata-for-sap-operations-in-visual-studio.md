---
title: Obtener metadatos para operaciones de SAP en Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- metadata, retrieving for SAP operations in Visual Studio
ms.assetid: 1be5934a-a5d4-4734-8bea-fb8274f59c71
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c3eb2a0a0afe6126a622bad1d18bf3fcc198fb0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988261"
---
# <a name="get-metadata-for-sap-operations-in-visual-studio"></a><span data-ttu-id="4cc28-102">Obtener metadatos para operaciones de SAP en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4cc28-102">Get Metadata for SAP Operations in Visual Studio</span></span>
<span data-ttu-id="4cc28-103">El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] proporciona dos [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] componentes que puede usar para desarrollar soluciones mediante el adaptador, el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]y el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4cc28-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] provides two [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components that you can use to help you develop solutions using the adapter—the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="4cc28-104">Los clientes del adaptador deben usar estos componentes para conectarse a un sistema SAP y, a continuación, generar los metadatos para los artefactos SAP que desean invocar.</span><span class="sxs-lookup"><span data-stu-id="4cc28-104">Adapter clients must use these components to connect to an SAP system and then generate metadata for the SAP artifacts they want to invoke.</span></span>  
  
 <span data-ttu-id="4cc28-105">Todos estos [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] componentes simplifican el desarrollo mediante:</span><span class="sxs-lookup"><span data-stu-id="4cc28-105">All these [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components simplify development by:</span></span>  
  
- <span data-ttu-id="4cc28-106">Proporcionar una interfaz de Microsoft Windows a través del cual puede examinar y buscar para las operaciones que desea usar en la solución.</span><span class="sxs-lookup"><span data-stu-id="4cc28-106">Providing a Microsoft Windows interface through which you can browse and search for operations that you want to use in your solution.</span></span>  
  
- <span data-ttu-id="4cc28-107">Recuperar los metadatos expuestos por el adaptador para estas operaciones de destino.</span><span class="sxs-lookup"><span data-stu-id="4cc28-107">Retrieving metadata exposed by the adapter for these target operations.</span></span>  
  
- <span data-ttu-id="4cc28-108">Convertir los metadatos, que se expresa como un documento de lenguaje de descripción de servicios Web (WSDL) por el adaptador, en un formulario que puede usar en la solución (esquemas de mensaje XSD para los proyectos de BizTalk o una representación de objeto de .NET de un contrato de servicio de WCF modelo de servicio) y agregarlo al proyecto.</span><span class="sxs-lookup"><span data-stu-id="4cc28-108">Converting that metadata, which is expressed as a Web Services Description Language (WSDL) document by the adapter, into a form that you can use in your solution (XSD message schemas for BizTalk projects or a .NET object representation of a service contract for the WCF service model) and adding it to your project.</span></span>  
  
  <span data-ttu-id="4cc28-109">Esta sección proporciona instrucciones sobre cómo usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]y el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4cc28-109">This section provides instructions about how to use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="4cc28-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="4cc28-110">See Also</span></span>  
[<span data-ttu-id="4cc28-111">Desarrollar aplicaciones SAP</span><span class="sxs-lookup"><span data-stu-id="4cc28-111">Develop your SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)