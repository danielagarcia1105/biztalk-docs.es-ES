---
title: Requisitos de PeopleSoft Enterprise | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- PeopleSoft Enterprise, requirements
- send handlers, PeopleSoft requirements
- CLASSPATH environment variable
- custom component interface object
- system requirements
- GET_CI_INFO.pc
ms.assetid: fabd808d-d9b6-43b0-a12a-727189f00a9d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45f267afce09e9c50d732d376fde43beaa1ef39a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="peoplesoft-enterprise-requirements"></a><span data-ttu-id="7215f-102">Requisitos de PeopleSoft Enterprise</span><span class="sxs-lookup"><span data-stu-id="7215f-102">PeopleSoft Enterprise Requirements</span></span>
## <a name="send-handler-peoplesoft-requirements"></a><span data-ttu-id="7215f-103">Requisitos del controlador de envío de PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="7215f-103">Send Handler PeopleSoft Requirements</span></span>  
 <span data-ttu-id="7215f-104">El adaptador de Microsoft BizTalk para PeopleSoft Enterprise contiene una interfaz de componente personalizado (CI) y proporciona acceso a ella a través de un API Java.</span><span class="sxs-lookup"><span data-stu-id="7215f-104">Microsoft BizTalk Adapter for PeopleSoft Enterprise contains a custom component interface (CI) and provides access to it through a Java API.</span></span> <span data-ttu-id="7215f-105">Un objeto CI personalizado, `GET_CI_INFO`, se implementa en el sistema PeopleSoft mediante las herramientas de PeopleSoft, para proporcionar informar de metadatos, necesaria para el adaptador de BizTalk para PeopleSoft Enterprise.</span><span class="sxs-lookup"><span data-stu-id="7215f-105">A custom CI object, `GET_CI_INFO`, is deployed in the PeopleSoft system using PeopleSoft Tools to provide metadata information that is required by BizTalk Adapter for PeopleSoft Enterprise.</span></span> <span data-ttu-id="7215f-106">Para obtener más información, consulte [preparación para usar PeopleSoft Enterprise](../core/preparing-to-use-peoplesoft-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="7215f-106">For more information, see [Preparing to Use PeopleSoft Enterprise](../core/preparing-to-use-peoplesoft-enterprise.md).</span></span>  
  
 <span data-ttu-id="7215f-107">La carga de la interfaz de componente personalizado es una única repetición.</span><span class="sxs-lookup"><span data-stu-id="7215f-107">Uploading the custom component interface is a one-time occurrence.</span></span> <span data-ttu-id="7215f-108">Este archivo, `GET_CI_INFO.pc`, se instala con el producto y debe instalarse antes de usar el adaptador para buscar CI.</span><span class="sxs-lookup"><span data-stu-id="7215f-108">This file, `GET_CI_INFO.pc`, installs with the product and must be installed before you can use the adapter to browse CIs.</span></span> <span data-ttu-id="7215f-109">Es necesario tener acceso a PeopleSoft Application Designer, pero la aplicación Application Designer no tiene que estar necesariamente en el equipo de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="7215f-109">You must have access to the PeopleSoft Application Designer, but the Application Designer application does not have to be on the BizTalk Server computer.</span></span> <span data-ttu-id="7215f-110">Use Application Designer para cargar el CI personalizado en el equipo de PeopleSoft en el que está buscando.</span><span class="sxs-lookup"><span data-stu-id="7215f-110">You use the Application Designer to upload the custom CI onto the PeopleSoft computer that you browse.</span></span>  
  
 <span data-ttu-id="7215f-111">Debe tener acceso al equipo de PeopleSoft porque debe establecer la variable de entorno CLASSPATH (o establecer la información en el **propiedades de transporte** pantalla) para que señale a de PeopleSoft `PSJOA/psjoa.jar` archivo.</span><span class="sxs-lookup"><span data-stu-id="7215f-111">You must have access to the PeopleSoft computer because you must set the environment variable CLASSPATH (or set the information in the **Transport Properties** screen) to point to PeopleSoft's `PSJOA/psjoa.jar` file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7215f-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="7215f-112">See Also</span></span>  
 <span data-ttu-id="7215f-113">[Introducción](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md) </span><span class="sxs-lookup"><span data-stu-id="7215f-113">[Getting Started](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md) </span></span>  
 [<span data-ttu-id="7215f-114">Planeamiento y arquitectura</span><span class="sxs-lookup"><span data-stu-id="7215f-114">Planning and Architecture</span></span>](../core/planning-and-architecture13.md)