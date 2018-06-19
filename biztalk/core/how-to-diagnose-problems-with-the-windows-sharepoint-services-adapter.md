---
title: Cómo diagnosticar problemas con Windows SharePoint Services adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55c29569-3814-43a7-93f8-a39c3464a831
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67aa43628e8db4384a411fd1cc4696b7955b3752
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249004"
---
# <a name="how-to-diagnose-problems-with-the-windows-sharepoint-services-adapter"></a><span data-ttu-id="0150d-102">Diagnóstico de problemas con el adaptador de Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="0150d-102">How to Diagnose Problems with the Windows SharePoint Services Adapter</span></span>
<span data-ttu-id="0150d-103">Esta sección contiene los pasos que pueden seguirse para ayudar al diagnóstico de problemas con el adaptador de Windows Sharepoint Services.</span><span class="sxs-lookup"><span data-stu-id="0150d-103">This section contains steps that can be followed to help diagnose problems with the Windows Sharepoint Services adapter.</span></span>  
  
### <a name="check-the-iis-and-httperr-log-files-of-the-iis-server-for-errors"></a><span data-ttu-id="0150d-104">Comprobar si existen errores detallados en los archivos de registro de IIS y HTTPERR del servidor IIS</span><span class="sxs-lookup"><span data-stu-id="0150d-104">Check the IIS and HTTPERR log files of the IIS Server for errors</span></span>  
  
-   <span data-ttu-id="0150d-105">Los archivos de registro del servidor IIS de origen o destino pueden contener información útil para la solución de problemas con el adaptador de Windows Sharepoint Services.</span><span class="sxs-lookup"><span data-stu-id="0150d-105">The source or target IIS server log files can contain information that is helpful for troubleshooting problems with the Windows Sharepoint Services adapter.</span></span> <span data-ttu-id="0150d-106">De forma predeterminada, en un equipo [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)], los archivos de registro de IIS se encuentran en el siguiente directorio:</span><span class="sxs-lookup"><span data-stu-id="0150d-106">By default the IIS log files on a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] computer are located in the following directory:</span></span>  
  
     <span data-ttu-id="0150d-107">*% WinDir %\\*system32\LogFiles\W3SVC1\\</span><span class="sxs-lookup"><span data-stu-id="0150d-107">*%WinDir%\\*system32\LogFiles\W3SVC1\\</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0150d-108">*% WinDir %* es un marcador de posición para la ubicación del directorio de Windows en el servidor IIS.</span><span class="sxs-lookup"><span data-stu-id="0150d-108">*%WinDir%* is a placeholder for the location of the Windows directory on the IIS server.</span></span>  
  
-   <span data-ttu-id="0150d-109">De forma predeterminada, en un equipo basado en [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] los archivos de registro de HTTPERR se ubican en el siguiente directorio:</span><span class="sxs-lookup"><span data-stu-id="0150d-109">By default the HTTPERR log files on a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] based computer are located in the following directory:</span></span>  
  
     <span data-ttu-id="0150d-110">*% WinDir %\\*system32\LogFiles\HTTPERR\\</span><span class="sxs-lookup"><span data-stu-id="0150d-110">*%WinDir%\\*system32\LogFiles\HTTPERR\\</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0150d-111">El archivo de registro de HTTPERR solo está disponible en equipos con [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0150d-111">The HTTPERR log file is only available on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] computers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0150d-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="0150d-112">See Also</span></span>  
 <span data-ttu-id="0150d-113">[Herramientas y utilidades que se utilizan para solucionar problemas](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="0150d-113">[Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span></span>  
 [<span data-ttu-id="0150d-114">Solucionar problemas del adaptador de Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="0150d-114">Troubleshooting the Windows SharePoint Services Adapter</span></span>](../core/troubleshooting-the-windows-sharepoint-services-adapter.md)