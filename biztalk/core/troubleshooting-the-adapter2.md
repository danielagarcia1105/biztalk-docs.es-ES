---
title: "Solución de problemas de la < adaptador 2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wildcard characters, in send port properties
- troubleshooting adapter
- Get.xml
- send ports, using wildcards in properties
ms.assetid: e9e0408f-5a12-4f05-83a6-37dc519ae4c5
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 991278813d2183795239d1a75c08e474b2f8159a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-the-adapter"></a><span data-ttu-id="d8ba0-102">Solucionar problemas del adaptador</span><span class="sxs-lookup"><span data-stu-id="d8ba0-102">Troubleshooting the Adapter</span></span>
<span data-ttu-id="d8ba0-103">Este tema contiene información para ayudarle a identificar y resolver los problemas que pueda tener mientras usa el adaptador de Microsoft BizTalk para PeopleSoft Enterprise.</span><span class="sxs-lookup"><span data-stu-id="d8ba0-103">This topic contains information to help you identify and resolve issues that you might experience while you are using Microsoft BizTalk Adapter for PeopleSoft Enterprise.</span></span>  
  
## <a name="cannot-use-wildcard-characters-in-send-port-properties"></a><span data-ttu-id="d8ba0-104">No se pueden usar caracteres comodín en las propiedades de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="d8ba0-104">Cannot use wildcard characters in send port properties</span></span>  
 <span data-ttu-id="d8ba0-105">El adaptador de BizTalk para PeopleSoft Enterprise no admite el uso de caracteres comodín en los siguientes campos de propiedades de puertos de envío:</span><span class="sxs-lookup"><span data-stu-id="d8ba0-105">BizTalk Adapter for PeopleSoft Enterprise does not support using wildcard characters in the following send port property fields:</span></span>  
  
-   <span data-ttu-id="d8ba0-106">Nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="d8ba0-106">Username</span></span>  
  
-   <span data-ttu-id="d8ba0-107">Ruta de acceso del servidor de aplicación</span><span class="sxs-lookup"><span data-stu-id="d8ba0-107">App Server Path</span></span>  
  
-   <span data-ttu-id="d8ba0-108">Java_Home</span><span class="sxs-lookup"><span data-stu-id="d8ba0-108">Java_Home</span></span>  
  
-   <span data-ttu-id="d8ba0-109">Archivos JAR de personas</span><span class="sxs-lookup"><span data-stu-id="d8ba0-109">People JAR Files</span></span>  
  
## <a name="getxml-data-assigns-0001-01-01-value-for-null-dates"></a><span data-ttu-id="d8ba0-110">Los datos Get.xml asignan el valor 0001-01-01 para fechas nulas</span><span class="sxs-lookup"><span data-stu-id="d8ba0-110">Get.xml data assigns 0001-01-01 value for null dates</span></span>  
 <span data-ttu-id="d8ba0-111">Get.xml asigna incorrectamente el valor 0001-01-01 para fechas nulas.</span><span class="sxs-lookup"><span data-stu-id="d8ba0-111">Get.xml incorrectly assigns 0001-01-01 value for null dates.</span></span> <span data-ttu-id="d8ba0-112">Debe usar la herramienta Asignador de BizTalk si desea reemplazar 0001-01-01 por un valor nulo.</span><span class="sxs-lookup"><span data-stu-id="d8ba0-112">You must use the BizTalk Mapper tool if you want to replace the 0001-01-01 with null.</span></span>  
  
## <a name="creating-and-updating-properties-with-collections-fails"></a><span data-ttu-id="d8ba0-113">Se produce un error al crear y actualizar propiedades con colecciones</span><span class="sxs-lookup"><span data-stu-id="d8ba0-113">Creating and updating properties with collections fails</span></span>  
 <span data-ttu-id="d8ba0-114">Al usar el adaptador con la versión 8.17.02 de PeopleSoft, el adaptador puede leer datos del servidor de PeopleSoft correctamente.</span><span class="sxs-lookup"><span data-stu-id="d8ba0-114">When using the Adapter with PeopleSoft version 8.17.02, the Adapter can read data from PeopleSoft server correctly.</span></span> <span data-ttu-id="d8ba0-115">Sin embargo, se produce un error al crear y actualizar propiedades con colecciones.</span><span class="sxs-lookup"><span data-stu-id="d8ba0-115">However, creating and updating fails for properties with collections.</span></span> <span data-ttu-id="d8ba0-116">Este un problema conocido de PeopleSoft que se corregirá en un futuro release de PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="d8ba0-116">This is a known PeopleSoft issue that may be fixed in a future release of PeopleSoft.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8ba0-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8ba0-117">See Also</span></span>  
 [<span data-ttu-id="d8ba0-118">Solución de problemas de PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="d8ba0-118">Troubleshooting PeopleSoft</span></span>](../core/troubleshooting-peoplesoft.md)