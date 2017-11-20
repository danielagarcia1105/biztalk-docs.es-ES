---
title: "Cómo distribuir el paquete de instalación de Web | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, Web services
- Web services, distributing
- Web services, deploying
ms.assetid: 0db71fdf-80d9-4ad5-b0d4-730d0bb549d4
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed7e6277045593360cbdfe57848f7313054b60f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-distribute-the-web-setup-package"></a><span data-ttu-id="4253d-102">Cómo distribuir el paquete de instalación de Web</span><span class="sxs-lookup"><span data-stu-id="4253d-102">How to Distribute the Web Setup Package</span></span>
<span data-ttu-id="4253d-103">Después de crear el paquete de instalación, necesita crear una carpeta de distribución en la que el archivo MSI y el archivo BindingInfo.xml se copian para configurar el servicio Web.</span><span class="sxs-lookup"><span data-stu-id="4253d-103">After you create the installation package, you need to create a distribution folder where a MSI file and a BindingInfo.xml file are copied to set up the Web service.</span></span>  
  
### <a name="to-distribute-the-web-setup-package"></a><span data-ttu-id="4253d-104">Para distribuir el paquete de configuración Web</span><span class="sxs-lookup"><span data-stu-id="4253d-104">To distribute the Web setup package</span></span>  
  
1.  <span data-ttu-id="4253d-105">Cree una carpeta de distribución que contenga los archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="4253d-105">Create a distribution folder to contain your setup files.</span></span>  
  
2.  <span data-ttu-id="4253d-106">Copie el archivo .MSI de la carpeta saliente del proyecto de configuración Web a la carpeta de distribución.</span><span class="sxs-lookup"><span data-stu-id="4253d-106">Copy the .MSI file from the Web Setup project output folder to the distribution folder.</span></span>  
  
3.  <span data-ttu-id="4253d-107">Copie el archivo BindingInfo.xml de la carpeta temporal en la carpeta del proyecto de servicio Web ASP.NET a la carpeta de distribución.</span><span class="sxs-lookup"><span data-stu-id="4253d-107">Copy the BindingInfo.xml file from the temp folder in the ASP.NET Web Service project folder to the distribution folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4253d-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="4253d-108">See Also</span></span>  
 [<span data-ttu-id="4253d-109">Implementar servicios Web publicados en un equipo que no tenga Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4253d-109">Deploying Published Web Services on a Non-Visual Studio Computer</span></span>](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)