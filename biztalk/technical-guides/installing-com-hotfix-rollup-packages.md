---
title: "Instalación de paquetes acumulativos de revisiones de COM + | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 587ae3da-db65-4da8-9d3b-89effb91b197
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40610c649e00993323adedf0ea29330dd289a0e3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="installing-com-hotfix-rollup-packages"></a><span data-ttu-id="f5583-102">Instalación de paquetes acumulativos de revisiones de COM +</span><span class="sxs-lookup"><span data-stu-id="f5583-102">Installing COM+ Hotfix Rollup Packages</span></span>
> [!NOTE]  
>  <span data-ttu-id="f5583-103">En este tema sólo es aplicable para Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="f5583-103">This topic is applicable only for Windows Server 2003.</span></span>  
  
 <span data-ttu-id="f5583-104">Debe instalar la última versión del paquete de acumulativo de revisiones de COM + de Windows Server 2003 y la versión más reciente del paquete acumulativo de coordinador de transacciones distribuidas (DTC).</span><span class="sxs-lookup"><span data-stu-id="f5583-104">You should install the last version of the Windows Server 2003 COM+ hotfix rollup package and latest version of the Distributed Transaction Coordinator (DTC) rollup package.</span></span> <span data-ttu-id="f5583-105">Esto es porque los paquetes incluyen numerosas correcciones de rendimiento y estabilidad.</span><span class="sxs-lookup"><span data-stu-id="f5583-105">This is because the packages include many performance and stability fixes.</span></span>  
  
 <span data-ttu-id="f5583-106">Debe instalar estos paquetes acumulativos en todos los equipos que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y en todos los equipos que ejecuten SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f5583-106">You should install these rollups on all computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and on all computers running SQL Server.</span></span> <span data-ttu-id="f5583-107">Los paquetes acumulativos son especialmente importantes para la solución de BizTalk funcionar bien en escenarios de alto rendimiento.</span><span class="sxs-lookup"><span data-stu-id="f5583-107">The rollups are especially important for your BizTalk solution to perform well in high-throughput scenarios.</span></span>  
  
 <span data-ttu-id="f5583-108">Los problemas DTC en el que se han corregido son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="f5583-108">The DTC issues that have been fixed are as follows:</span></span>  
  
-   <span data-ttu-id="f5583-109">Cierre inesperado de DTC</span><span class="sxs-lookup"><span data-stu-id="f5583-109">Unexpected DTC shutdown</span></span>  
  
-   <span data-ttu-id="f5583-110">Problemas de fragmentación de memoria</span><span class="sxs-lookup"><span data-stu-id="f5583-110">Memory fragmentation issues</span></span>  
  
-   <span data-ttu-id="f5583-111">DTC podría dejar de responder con carga</span><span class="sxs-lookup"><span data-stu-id="f5583-111">DTC may stop responding under load</span></span>  
  
-   <span data-ttu-id="f5583-112">DTC puede perder memoria o deje de responder cuando se usa con[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5583-112">DTC may leak memory or stop responding when used with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="f5583-113">Se ha mejorado el rendimiento de DTC de la carga</span><span class="sxs-lookup"><span data-stu-id="f5583-113">Performance of DTC under load has been improved</span></span>  
  
## <a name="installing-the-com-rollup-package"></a><span data-ttu-id="f5583-114">Instalar el paquete de COM + paquete acumulativo de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="f5583-114">Installing the COM+ Rollup Package</span></span>  
 <span data-ttu-id="f5583-115">COM + ya no se está publicando paquetes acumulativos de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="f5583-115">COM+ is no longer releasing rollup packages.</span></span> <span data-ttu-id="f5583-116">Siga estas indicaciones para instalar el último paquete de COM +:</span><span class="sxs-lookup"><span data-stu-id="f5583-116">Follow this information to install the last COM+ package:</span></span>  
  
-   <span data-ttu-id="f5583-117">La versión final del resumen de COM + es el "Windows Server 2003 posteriores al Service Pack 2 COM + 1.5 revisión acumulación paquete 12".</span><span class="sxs-lookup"><span data-stu-id="f5583-117">The final version of the COM+ rollup is the “Windows Server 2003 Post-Service Pack 2 COM+ 1.5 Hotfix Rollup Package 12”.</span></span> <span data-ttu-id="f5583-118">Esta revisión se instalará en cualquier versión de Windows Server 2003, incluso aquellos sin un service pack instalado.</span><span class="sxs-lookup"><span data-stu-id="f5583-118">This hotfix will install on any version of Windows Server 2003, even those without a service pack installed.</span></span> <span data-ttu-id="f5583-119">Para obtener más información acerca de esta revisión puede encontrarse en el artículo de Microsoft Knowledge Base 934016, ["disponibilidad de Windows Server 2003 posteriores al Service Pack 2 COM + 1.5 revisión acumulación paquete 12"](http://go.microsoft.com/fwlink/?LinkId=158756) (http://go.microsoft.com/fwlink/?LinkId=158756).</span><span class="sxs-lookup"><span data-stu-id="f5583-119">More information about this hotfix can be found in Microsoft Knowledge Base article 934016, ["Availability of Windows Server 2003 Post-Service Pack 2 COM+ 1.5 Hotfix Rollup Package 12"](http://go.microsoft.com/fwlink/?LinkId=158756) (http://go.microsoft.com/fwlink/?LinkId=158756).</span></span>  
  
## <a name="installing-the-dtc-rollup-package"></a><span data-ttu-id="f5583-120">Instalar el paquete acumulativo DTC</span><span class="sxs-lookup"><span data-stu-id="f5583-120">Installing the DTC Rollup Package</span></span>  
 <span data-ttu-id="f5583-121">DTC lanzarán paquetes acumulativos de independiente de COM +.</span><span class="sxs-lookup"><span data-stu-id="f5583-121">DTC will be releasing rollup packages independent of COM+.</span></span> <span data-ttu-id="f5583-122">Siga estas indicaciones para instalar el paquete más reciente de DTC:</span><span class="sxs-lookup"><span data-stu-id="f5583-122">Follow this information to install the latest DTC package:</span></span>  
  
-   <span data-ttu-id="f5583-123">Cuando se redactó este documento, el último paquete acumulativo de revisiones DTC es "Paquete de 16".</span><span class="sxs-lookup"><span data-stu-id="f5583-123">As of this writing, the latest DTC hotfix rollup is “Package 16”.</span></span> <span data-ttu-id="f5583-124">Para obtener más información acerca de esta revisión puede encontrarse en el artículo de Microsoft Knowledge Base 958013, ["Lista de los problemas de MS DTC que se corrigieron en Windows Server 2003 MS DTC paquete acumulativo de revisiones 16"](http://support.microsoft.com/kb/979919) (http://support.microsoft.com/kb/979919) .</span><span class="sxs-lookup"><span data-stu-id="f5583-124">More information about this hotfix can be found in Microsoft Knowledge Base article 958013, ["List of the MS DTC issues that are fixed in Windows Server 2003 MS DTC Hotfix Rollup Package 16"](http://support.microsoft.com/kb/979919) (http://support.microsoft.com/kb/979919).</span></span>  
  
     <span data-ttu-id="f5583-125">El artículo de Knowledge Base sobre el paquete de paquete acumulativo de actualizaciones de revisión más reciente de DTC puede encontrarse mediante la búsqueda [http://support.microsoft.com](http://support.microsoft.com/) para la frase (incluidas las comillas):</span><span class="sxs-lookup"><span data-stu-id="f5583-125">The KB article about the latest DTC hotfix rollup package can be found by searching [http://support.microsoft.com](http://support.microsoft.com/) for the phrase (including the quotes):</span></span>  
  
    ```  
    "MS DTC Hotfix Rollup Package"  
    ```  
  
     <span data-ttu-id="f5583-126">La siguiente consulta realiza esta búsqueda para usted.</span><span class="sxs-lookup"><span data-stu-id="f5583-126">The following query does this search for you.</span></span> <span data-ttu-id="f5583-127">Elegir cuál es el más reciente:</span><span class="sxs-lookup"><span data-stu-id="f5583-127">Choose the latest one:</span></span>  
  
     [<span data-ttu-id="f5583-128">http://support.Microsoft.com/search/default.aspx?Query= "MS + DTC + + paquete acumulativo de revisiones +"</span><span class="sxs-lookup"><span data-stu-id="f5583-128">http://support.microsoft.com/search/default.aspx?query="MS+DTC+Hotfix+Rollup+Package"</span></span>](http://support.microsoft.com/search/default.aspx?query=%22MS+DTC+Hotfix+Rollup+Package%22)